---
title: importer | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.import
dev_langs:
- C++
helpviewer_keywords:
- import attribute
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b371cd1094a49f8a629cb6f8e880fd1210670f91
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877265"
---
# <a name="import"></a>d'importation
Spécifie un autre fichier .idl, .odl ou en-tête contenant des définitions à référencer à partir de votre fichier IDL principal.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      [ import(  
   idl_file  
) ];  
```  
  
#### <a name="parameters"></a>Paramètres  
 `idl_file`  
 Le nom d’un fichier .idl que vous souhaitez importer dans la bibliothèque de types du projet actuel.  
  
## <a name="remarks"></a>Notes  
 Le **importer** C++ attribut entraîne une `#import` instruction doit être placé sous le `import "docobj.idl"` instruction dans le fichier .idl généré. Le **importer** attribut a les mêmes fonctionnalités que le [importer](http://msdn.microsoft.com/library/windows/desktop/aa367047) attribut MIDL.  
  
 Le **importer** attribut place uniquement le fichier spécifié dans le fichier .idl qui sera généré par votre projet ; le **importer** attribut ne permet pas d’appeler des constructions dans le fichier spécifié à partir de code source dans votre projet.  Pour appeler les constructions dans le fichier spécifié à partir de code source dans votre projet, soit utiliser [#import](../preprocessor/hash-import-directive-cpp.md) et `embedded_idl` attribut ou inclure le fichier .h pour la `idl_file`, s’il existe un fichier .h.  
  
## <a name="example"></a>Exemple  
 L'exemple de code suivant :  
  
```  
// cpp_attr_ref_import.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[import(import.idl)];  
```  
  
 génère le code suivant dans le fichier .idl généré :  
  
```  
import "docobj.idl";  
import "import.idl";  
  
[ uuid(EED3644C-8488-3ECD-BA97-147DB3CDB499), version(1.0) ]  
library MyLib {  
   importlib("stdole2.tlb");  
   importlib("olepro32.dll");  
...  
```  
  
## <a name="requirements"></a>Spécifications  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|N'importe où|  
|**Renouvelable**|Non|  
|**Attributs requis**|Aucun|  
|**Attributs non valides**|Aucun|  
  
 Pour plus d'informations, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
 [Attributs autonomes](../windows/stand-alone-attributes.md)   
 [importidl](../windows/importidl.md)   
 [importlib](../windows/importlib.md)   
 [Inclure](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
