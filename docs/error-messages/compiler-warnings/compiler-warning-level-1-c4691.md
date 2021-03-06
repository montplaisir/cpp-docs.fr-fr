---
title: Compilateur avertissement (niveau 1) C4691 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4691
dev_langs:
- C++
helpviewer_keywords:
- C4691
ms.assetid: 722133d9-87f6-46c1-9e86-9825453d6999
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9dccce2468c83dd7d14596c1c26e19bd13ad1a70
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282595"
---
# <a name="compiler-warning-level-1-c4691"></a>Avertissement du compilateur (niveau 1) C4691
'type' : type référencé était attendu dans l’assembly non référencé 'fichier', type défini dans l’unité de traduction actuelle utilisée à la place  
  
 Le fichier de métadonnées contenant la définition du type d’origine n’est pas référencé, et le compilateur utilise une définition de type local.  
  
 Dans le cas où vous reconstruisez *fichier*, C4691 peut être ignorée ou désactivée avec le pragma [avertissement](../../preprocessor/warning.md).  Autrement dit, si le fichier que vous créez est la même que le fichier où le compilateur s’attend à trouver la définition de type, vous pouvez ignorer C4691.  
  
 Toutefois, un comportement inattendu peut se produire si le compilateur utilise une définition qui n’est pas dans le même assembly est référencé dans les métadonnées ; Types CLR sont typés non seulement par le nom du type, mais également par l’assembly.  Autrement dit, un type Z provenant du fichier z.dll d’assembly est différent d’un type Z à partir du fichier y.dll d’assembly.  
  
## <a name="example"></a>Exemple  
 Cet exemple contient la définition du type d’origine.  
  
```  
// C4691_a.cpp  
// compile with: /clr /LD /W1  
public ref class Original_Type {};  
```  
  
## <a name="example"></a>Exemple  
 Cet exemple fait référence au fichier C4691_a.dll et déclare un champ de type Original_Type.  
  
```  
// C4691_b.cpp  
// compile with: /clr /LD  
#using "C4691_a.dll"  
public ref class Client {  
public:  
   Original_Type^ ot;  
};  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C4691.  Notez que cet exemple contient une définition pour Original_Type et ne fait pas référence à C4691a.dll.  
  
 Pour résoudre, référencez le fichier de métadonnées qui contient la définition du type d’origine et supprimez la déclaration locale et la définition.  
  
```  
// C4691_c.cpp  
// compile with: /clr /LD /W1  
// C4691 expected  
  
// Uncomment the following line to resolve.  
// #using "C4691_a.dll"  
#using "C4691_b.dll"  
  
// Delete the following line to resolve.  
ref class Original_Type;  
  
public ref class MyClass : Client {};  
```