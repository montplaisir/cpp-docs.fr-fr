---
title: "Comment&#160;: marshaler des cha&#238;nes BSTR pour ADO.NET (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ADO.NET (C++), marshaler des chaînes BSTR"
  - "BSTR, chaînes"
  - "chaînes (C++), marshaler des chaînes BSTR"
ms.assetid: 5daf4d9e-6ae8-4604-908f-855e37c8d636
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: marshaler des cha&#238;nes BSTR pour ADO.NET (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Montre comment ajouter une chaîne COM \(`BSTR`\) à une base de données et comment marshaler une <xref:System.String?displayProperty=fullName> d'une base de données vers un `BSTR`.  
  
## Exemple  
 Dans cet exemple, la classe DatabaseClass est créée pour interagir avec un objet <xref:System.Data.DataTable> ADO.NET.  Notez que cette classe est une `class` C\+\+ native \(comparée à une `ref class` ou `value class`\).  Cela est nécessaire, car nous souhaitons utiliser cette classe à partir de code natif et il est impossible d'utiliser des types managés en code natif.  Cette classe sera compilée pour cibler le CLR, comme indiqué par la directive `#pragma managed` précédant la déclaration de classe.  Pour plus d'informations sur cette directive, consultez [managé, non managé](../preprocessor/managed-unmanaged.md).  
  
 Notez le membre privé de la classe DatabaseClass : `gcroot<DataTable ^> table`.  Les types natifs ne pouvant pas contenir de types managés, le mot clé `gcroot` est nécessaire.  Pour plus d'informations sur `gcroot`, consultez [Comment : déclarer des handles dans les types natifs](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Le reste du code dans cet exemple est du code C\+\+ natif, comme indiqué par la directive `#pragma unmanaged` précédant `main`.  Dans cet exemple, nous créons une nouvelle instance de DatabaseClass et appelons ses méthodes pour créer une table et remplir quelques lignes dans la table.  Notez que les chaînes COM sont passées en tant que valeurs pour la colonne de base de données StringCol.  Au sein de DatabaseClass, ces chaînes sont marshalées vers des chaînes managées à l'aide des fonctionnalités de marshaling trouvées dans l'espace de noms <xref:System.Runtime.InteropServices?displayProperty=fullName>.  En particulier, la méthode <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> est utilisée pour marshaler un `BSTR` vers une <xref:System.String> et la méthode <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> est utilisée pour marshaler une <xref:System.String> vers un `BSTR`.  
  
> [!NOTE]
>  La mémoire allouée par <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> doit être libérée en appelant <xref:System.Runtime.InteropServices.Marshal.FreeBSTR%2A> ou `SysFreeString`.  
  
```  
// adonet_marshal_string_bstr.cpp  
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll  
#include <comdef.h>  
#include <gcroot.h>  
#include <iostream>  
using namespace std;  
  
#using <System.Data.dll>  
using namespace System;  
using namespace System::Data;  
using namespace System::Runtime::InteropServices;  
  
#define MAXCOLS 100  
  
#pragma managed  
class DatabaseClass  
{  
public:  
    DatabaseClass() : table(nullptr) { }  
  
    void AddRow(BSTR stringColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        row["StringCol"] = Marshal::PtrToStringBSTR(  
            (IntPtr)stringColValue);  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("StringCol",  
            Type::GetType("System.String"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(BSTR dataColumn, BSTR *values,  
        int valuesLength)  
    {  
        // Marshal the name of the column to a managed  
        // String.  
        String ^columnStr = Marshal::PtrToStringBSTR(  
                (IntPtr)dataColumn);  
  
        // Get all rows in the table.  
        array<DataRow ^> ^rows = table->Select();  
        int len = rows->Length;  
        len = (len > valuesLength) ? valuesLength : len;  
        for (int i = 0; i < len; i++)  
        {  
            // Marshal each column value from a managed string  
            // to a BSTR.  
            values[i] = (BSTR)Marshal::StringToBSTR(  
                (String ^)rows[i][columnStr]).ToPointer();  
        }  
  
        return len;  
    }  
  
private:  
    // Using gcroot, you can use a managed type in  
    // a native class.  
    gcroot<DataTable ^> table;  
};  
  
#pragma unmanaged  
int main()  
{  
    // Create a table and add a few rows to it.  
    DatabaseClass *db = new DatabaseClass();  
    db->CreateAndPopulateTable();  
  
    BSTR str1 = SysAllocString(L"This is string 1.");  
    db->AddRow(str1);  
  
    BSTR str2 = SysAllocString(L"This is string 2.");  
    db->AddRow(str2);  
  
    // Now retrieve the rows and display their contents.  
    BSTR values[MAXCOLS];  
    BSTR str3 = SysAllocString(L"StringCol");  
    int len = db->GetValuesForColumn(  
        str3, values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        wcout << "StringCol: " << values[i] << endl;  
  
        // Deallocate the memory allocated using  
        // Marshal::StringToBSTR.  
        SysFreeString(values[i]);  
    }  
  
    SysFreeString(str1);  
    SysFreeString(str2);  
    SysFreeString(str3);  
    delete db;  
  
    return 0;  
}  
```  
  
  **StringCol: This is string 1.**  
**StringCol: This is string 2.**   
## Compilation du code  
  
-   Pour compiler le code depuis la ligne de commande, enregistrez l'exemple de code dans un fichier nommé adonet\_marshal\_string\_native.cpp et saisissez l'instruction suivante :  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp  
    ```  
  
## Sécurité .NET Framework  
 Pour plus d'informations sur les problèmes de sécurité impliquant ADO.NET, consultez [Sécurisation des applications ADO.NET](../Topic/Securing%20ADO.NET%20Applications.md).  
  
## Voir aussi  
 <xref:System.Runtime.InteropServices>   
 [Accès aux données](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](../Topic/ADO.NET.md)   
 [Interoperability](http://msdn.microsoft.com/fr-fr/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [Interopérabilité native et .NET](../dotnet/native-and-dotnet-interoperability.md)