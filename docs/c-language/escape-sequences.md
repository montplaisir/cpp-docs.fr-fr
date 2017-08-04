---
title: "S&#233;quences d&#39;&#233;chappement | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "guillemet simple (')"
  - "? (symbole)"
  - "? (symbole), Caractère de séquence d'échappement"
  - "\ dans les séquences d'échappement"
  - "\a (séquence d'échappement)"
  - "\f (séquence d'échappement)"
  - "\n (séquence d'échappement)"
  - "\r (séquence d'échappement)"
  - "\t (séquence d'échappement)"
  - "\v (séquence d'échappement)"
  - "retour arrière (séquence d'échappement)"
  - "caractère de cloche \a (séquence d'échappement)"
  - "retours chariot"
  - "séquences d'échappement de caractère de contrôle"
  - "double barre oblique inverse"
  - "caractères d'échappement"
  - "séquences d'échappement"
  - "saut de page \f (séquence d'échappement)"
  - "séquence d'échappement hexadécimale"
  - "tabulation horizontale \t (séquence d'échappement)"
  - "caractère de saut de ligne \n (séquence d'échappement)"
  - "caractères de contrôle non graphiques"
  - "séquence d'échappement octale"
  - "point d'interrogation, de littéral"
  - "guillemets, unique"
  - "tabulation \t (séquence d'échappement)"
  - "tabulation verticale \v (séquence d'échappement)"
ms.assetid: 5aef377f-a76c-4d5c-aa04-8308758ad6a8
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# S&#233;quences d&#39;&#233;chappement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les combinaisons de caractères composées d'une barre oblique inverse \(**\\**\) suivie d'une lettre ou d'une combinaison de chiffres sont appelées "séquences d'échappement". Pour représenter un caractère de saut de ligne, un guillemet simple ou certains autres caractères dans une constante caractère, vous devez utiliser des séquences d'échappement.  Une séquence d'échappement est considérée comme un caractère unique et est donc valide en tant que constante caractère.  
  
 Les séquences d'échappement sont généralement utilisées pour spécifier des actions telles que les retours chariot et les tabulations sur les terminaux et les imprimantes.  Elles sont également utilisées pour fournir des représentations littérales des caractères non imprimables et des caractères qui ont généralement des significations spéciales, par exemple les guillemets doubles \(**"**\).  Le tableau suivant répertorie les séquences d'échappement ANSI et leur représentation.  
  
 Notez que le point d'interrogation précédé d'une barre oblique inverse \(**\\?**\) spécifie un point d'interrogation littéral dans les cas où la séquence de caractères est interprétée à tort comme un trigraphe.  Pour plus d'informations, consultez [Trigraphes](../c-language/trigraphs.md).  
  
### Séquences d'échappement  
  
|Séquence d'échappement|Représente|  
|----------------------------|----------------|  
|**\\a**|Sonnerie \(alerte\)|  
|**\\b**|Ret. arr|  
|**\\f**|Saut de page|  
|**\\n**|Nouvelle ligne|  
|**\\r**|Retour chariot|  
|**\\t**|Tabulation horizontale|  
|**\\v**|Tabulation verticale|  
|**\\'**|Guillemet simple|  
|**\\"**|Guillemets doubles|  
|**\\\\**|Barre oblique inverse|  
|**\\?**|Point d'interrogation littéral|  
|**\\** *ooo*|Caractère ASCII en notation octale|  
|**\\x** *hh*|Caractère ASCII en notation hexadécimale|  
|**\\x** *hhhh*|Caractère Unicode en notation hexadécimale si cette séquence d'échappement est utilisée dans une constante à caractères larges ou un littéral de chaîne Unicode.<br /><br /> Par exemple, `WCHAR f = L'\x4e00'` ou `WCHAR b[] = L"The Chinese character for one is \x4e00"`.|  
  
 **Section spécifique à Microsoft**  
  
 Si une barre oblique inverse précède un caractère qui n'apparaît pas dans le tableau, le compilateur traite le caractère non défini comme le caractère lui\-même.  Par exemple, `\c` est traité comme `c`.  
  
 **FIN de la section spécifique à Microsoft**  
  
 Les séquences d'échappement vous permettent d'envoyer des caractères de contrôle non graphiques à un périphérique d'affichage.  Par exemple, le caractère ESC \(**\\033**\) est souvent utilisé comme le premier caractère d'une commande de contrôle pour un terminal ou une imprimante.  Certaines séquences d'échappement sont spécifiques au périphérique.  Par exemple, les séquences d'échappement de tabulation verticale et de saut de page \(**\\v** et **\\f**\) n'affectent pas la sortie sur l'écran, mais elles exécutent des opérations d'imprimante appropriées.  
  
 Vous pouvez également utiliser la barre oblique inverse \(**\\**\) comme caractère de continuation.  Lorsqu'un caractère de saut de ligne \(équivalent à une pression sur la touche RETOUR\) suit immédiatement la barre oblique inverse, le compilateur ignore la barre oblique inverse et le caractère de saut de ligne et traite la ligne suivante dans le cadre de la ligne précédente.  Cela est surtout utile pour les définitions de préprocesseur plus longues qu'une ligne.  Exemple :  
  
```  
#define assert(exp) \  
( (exp) ? (void) 0:_assert( #exp, __FILE__, __LINE__ ) )  
```  
  
## Voir aussi  
 [Constantes caractère C](../c-language/c-character-constants.md)