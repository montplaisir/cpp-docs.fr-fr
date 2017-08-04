---
title: "D&#233;clarations d&#39;&#233;num&#233;ration C | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "#define (directive), alternative à"
  - "déclarations, énumérations"
  - "déclarer des énumérations"
  - "directive define (#define), alternative à"
  - "énumérateurs, déclarer"
  - "constantes nommées, déclarations d'énumération"
ms.assetid: bd18f673-4dda-4bc1-92fd-d1ce10074910
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# D&#233;clarations d&#39;&#233;num&#233;ration C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une énumération se compose d'un ensemble de constantes entières nommées.  Une déclaration de type énumération indique le nom de la balise d'énumération \(facultative\) et définit l'ensemble des identificateurs d'entiers nommés \(appelés « ensemble d'énumération », « constantes d'énumérateur », « énumérateurs » ou « membres »\).  Une variable avec type énumération stocke une des valeurs de l'ensemble d'énumération défini par ce type.  
  
 Les variables de type `enum` peuvent être utilisées dans des expressions d'indexation et comme opérandes de tous les opérateurs arithmétiques et relationnels.  Les énumérations offrent une alternative à la directive de préprocesseur `#define` et présentent l'avantage suivant : les valeurs peuvent être générées pour vous et se conformer aux règles normales de portée.  
  
 En C ANSI, les expressions qui définissent la valeur d'une constante d'énumérateur ont toujours le type `int` ; par conséquent, le stockage associé à une variable d'énumération est celui requis pour une seule valeur `int` unique.  Une constante d'énumération ou une valeur de type énuméré peut être utilisée partout où le langage C autorise une expression d'entier.  
  
## Syntaxe  
 *enum\-specifier* :  
 **enum**  *identifier*  opt **{** *enumerator\-list* **}**  
  
 **enum**  *identifier*  
  
 L'élément facultatif *identifier* désigne le type énumération défini par *enumerator\-list*.  Cet identificateur est souvent appelé « balise » de l'énumération spécifiée par la liste.  Un spécificateur de type de la forme  
  
```  
  
enum identifier { enumerator-list }  
```  
  
 déclare l'élément *identifier* comme devant être la balise de l'énumération spécifiée par l'élément non terminal *enumerator\-list*.  L'élément *enumerator\-list* définit le « contenu d'énumérateur ». L'élément *enumerator\-list* est décrit en détail ci\-dessous.  
  
 Si la déclaration d'une balise est visible, les déclarations suivantes qui utilisent la balise mais omettent l'élément *enumerator\-list* spécifient le type énuméré déclaré précédemment.  La balise doit faire référence à un type énumération défini, et ce type énumération doit se trouver dans la portée actuelle.  Étant donné que le type énumération est défini ailleurs, l'élément *enumerator\-list* n'apparaît pas dans cette déclaration.  Les déclarations des types dérivés à partir des énumérations et les déclarations de `typedef` pour les types énumération peuvent utiliser la balise d'énumération avant que le type énumération ne soit défini.  
  
## Syntaxe  
 *enumerator\-list* :  
 *enumerator*  
  
 *enumerator\-list* **,**  `enumerator`  
  
 `enumerator`:  
 *enumeration\-constant*  
  
 *enumeration\-constant*  **\=**  *constant\-expression*  
  
 *enumeration\-constant* :  
 *identifier*  
  
 Chaque élément *enumeration\-constant* d'un élément *enumeration\-list* désigne une valeur de l'ensemble d'énumération.  Par défaut, le premier élément *enumeration\-constant* est associé à la valeur 0.  L'élément *enumeration\-constant* suivant dans la liste est associé à la valeur de \(*constant\-expression* \+ 1\), sauf si vous l'associez explicitement à une autre valeur.  Le nom d'un élément *enumeration\-constant* est équivalent à sa valeur.  
  
 Vous pouvez utiliser *enumeration\-constant \= constant\-expression* pour remplacer la séquence de valeurs par défaut.  Par conséquent, si *enumeration\-constant \= constant\-expression* apparaît dans l'élément *enumerator\-list*, l'élément *enumeration\-constant* est associé à la valeur indiquée par *constant\-expression*.  L'élément *constant\-expression* doit avoir le type `int` et peut être négatif.  
  
 Les règles suivantes s'appliquent aux membres d'un ensemble d'énumération :  
  
-   Un ensemble d'énumération peut contenir des valeurs de constante en double.  Par exemple, vous pouvez associer la valeur 0 à deux identificateurs différents, peut\-être nommés `null` et `zero`, dans le même ensemble.  
  
-   Les identificateurs dans la liste d'énumérations doivent être distincts des autres identificateurs dans la même portée ayant la même visibilité, y compris des noms de variable ordinaire et des identificateurs dans les autres listes d'énumération.  
  
-   Les balises d'énumération obéissent aux règles normales de portée.  Elles doivent être distinctes des autres balises d'énumération, de structure et d'union ayant la même visibilité.  
  
## Exemples  
 Les exemples suivants illustrent des déclarations d'énumération :  
  
```  
enum DAY            /* Defines an enumeration type    */  
{  
    saturday,       /* Names day and declares a       */  
    sunday = 0,     /* variable named workday with    */   
    monday,         /* that type                      */  
    tuesday,  
    wednesday,      /* wednesday is associated with 3 */  
    thursday,  
    friday  
} workday;  
```  
  
 La valeur 0 est associée à `saturday` par défaut.  L'identificateur `sunday` est explicitement défini à 0.  Les autres identificateurs sont définis avec les valeurs 1 à 5 par défaut.  
  
 Dans cet exemple, une valeur de l'ensemble `DAY` est assignée à la variable `today`.  
  
```  
enum DAY today = wednesday;  
```  
  
 Notez que le nom de la constante d'énumération est utilisé pour assigner la valeur.  Étant donné que le type énumération `DAY` a été déclaré précédemment, seule la balise d'énumération `DAY` est nécessaire.  
  
 Pour assigner explicitement une valeur d'entier à une variable d'un type de données énuméré, utilisez un cast de type :  
  
```  
workday = ( enum DAY ) ( day_value - 1 );  
```  
  
 Ce cast est recommandé mais C n'est pas requis.  
  
```  
enum BOOLEAN  /* Declares an enumeration data type called BOOLEAN */  
{  
    false,     /* false = 0, true = 1 */  
    true   
};   
  
enum BOOLEAN end_flag, match_flag; /* Two variables of type BOOLEAN */  
```  
  
 Cette déclaration peut également être spécifiée sous la forme  
  
```  
enum BOOLEAN { false, true } end_flag, match_flag;\  
```  
  
 ou sous la forme  
  
```  
enum BOOLEAN { false, true } end_flag;  
enum BOOLEAN match_flag;  
```  
  
 Voici un exemple qui utilise ces variables :  
  
```  
if ( match_flag == false )  
    {  
     .  
     .   /* statement */   
     .  
    }  
    end_flag = true;  
```  
  
 Les types de données d'énumérateur sans nom peuvent également être déclarés.  Le nom du type de données est omis, mais les variables peuvent être déclarées.  La variable `response` est une variable du type défini :  
  
```  
enum { yes, no } response;  
```  
  
## Voir aussi  
 [Énumérations](../cpp/enumerations-cpp.md)