---
title: "CDataSource::OpenWithPromptFileName | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDataSource.OpenWithPromptFileName"
  - "OpenWithPromptFileName"
  - "ATL::CDataSource::OpenWithPromptFileName"
  - "ATL.CDataSource.OpenWithPromptFileName"
  - "CDataSource::OpenWithPromptFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OpenWithPromptFileName (méthode)"
ms.assetid: 89460504-1aaf-4412-aa7b-fa5a4b39ada3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CDataSource::OpenWithPromptFileName
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette méthode présente une invite à l'utilisateur sous la forme d'une boîte de dialogue, puis ouvre une source de données correspondant au fichier spécifié par l'utilisateur.  
  
## Syntaxe  
  
```  
  
        HRESULT OpenWithPromptFileName(   
   HWND hWnd = GetActiveWindow(   
   ),   
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_NONE,   
   LPCOLESTR szInitialDirectory = NULL    
) throw( );  
```  
  
#### Paramètres  
 `hWnd`  
 \[in\] Handle de fenêtre devant être le parent de la boîte de dialogue.  
  
 `dwPromptOptions`  
 \[in\] Détermine le style de la boîte de dialogue de recherche à afficher.  Consultez Msdasc.h pour connaître les valeurs possibles.  
  
 *szInitialDirectory*  
 \[in\] Répertoire initial à afficher dans la boîte de dialogue de recherche.  
  
## Valeur de retour  
 `HRESULT` standard.  
  
## Notes  
 Cette méthode ouvre un objet source de données à l'aide des composants de service d'oledb32.dll ; cette DLL contient l'implémentation des fonctionnalités Composants de service, telles que la mise en pool de ressources, l'inscription de transaction automatique, etc.  Pour plus d'informations, consultez « Services OLE DB » dans le Guide de référence du programmeur OLE DB à l'adresse [http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/oledb\/htm\/oledbole\_db\_services.asp?frame\=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDataSource, classe](../../data/oledb/cdatasource-class.md)