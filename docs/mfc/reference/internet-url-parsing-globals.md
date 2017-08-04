---
title: "Objet Globals d’analyse des URL Internet et les programmes d’assistance | Documents Microsoft"
ms.custom: 
ms.date: 04/03/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.isapi
dev_langs:
- C++
helpviewer_keywords:
- parsing, URLs
- URLs, parsing
ms.assetid: 46c6384f-e4a6-4dbd-9196-219c19040ec5
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: b943ef8dd652df061965fe81ecc9c08115636141
ms.openlocfilehash: 947ef992d58895e4638d9ffe77fca973cea8eada
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="internet-url-parsing-globals-and-helpers"></a>Programmes d’assistance et objet Globals d’analyse des URL Internet
Lorsqu’un client envoie une requête au serveur Internet, vous pouvez utiliser une des URL de l’objet globals d’analyse pour extraire des informations sur le client. Les fonctions d’assistance fournissent d’autres fonctionnalités internet.
  
## <a name="internet-url-parsing-globals"></a>Objet Globals d'analyse des URL Internet  
  
|||  
|-|-|  
|[AfxParseURL](#afxparseurl)|Analyse une chaîne URL et retourne le type de service et ses composants.|  
|[AfxParseURLEx](#afxparseurlex)|Analyse une chaîne URL et retourne le type de service et ses composants, ainsi en fournissant le nom d’utilisateur et un mot de passe.|  

## <a name="other-internet-helpers"></a>Autres programmes d’assistance pour Internet
|||
|-|-|
|[AfxThrowInternetException](#afxthrowinternetexception)|Lève une exception liée à la connexion internet.|
|[AfxGetInternetHandleType](#afxgetinternethandletype)|Détermine le type d’un handle d’Internet.|
  
##  <a name="afxparseurl"></a>AfxParseURL  
 Ce global est utilisé dans [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
```   
BOOL AFXAPI AfxParseURL(
    LPCTSTR pstrURL,  
    DWORD& dwServiceType,  
    CString& strServer,  
    CString& strObject,  
    INTERNET_PORT& nPort); 
```  
  
### <a name="parameters"></a>Paramètres  
 *pstrURL*  
 Un pointeur vers une chaîne contenant l’URL à analyser.  
  
 `dwServiceType`  
 Indique le type de service Internet. Les valeurs possibles sont les suivantes :  
  
-   AFX_INET_SERVICE_FTP  
  
-   AFX_INET_SERVICE_HTTP  
  
-   AFX_INET_SERVICE_HTTPS  
  
-   AFX_INET_SERVICE_GOPHER  
  
-   AFX_INET_SERVICE_FILE  
  
-   AFX_INET_SERVICE_MAILTO  
  
-   AFX_INET_SERVICE_NEWS  
  
-   AFX_INET_SERVICE_NNTP  
  
-   AFX_INET_SERVICE_TELNET  
  
-   AFX_INET_SERVICE_WAIS  
  
-   AFX_INET_SERVICE_MID  
  
-   AFX_INET_SERVICE_CID  
  
-   AFX_INET_SERVICE_PROSPERO  
  
-   AFX_INET_SERVICE_AFS  
  
-   AFX_INET_SERVICE_UNK  
  
 `strServer`  
 Le premier segment de l’URL qui suit le type de service.  
  
 `strObject`  
 Un objet qui désigne l’URL (peut être vide).  
  
 `nPort`  
 Déterminé à partir du serveur ou l’objet des portions de l’URL, si elles existent.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’URL a été analysée avec succès ; Sinon, 0 si elle est vide ou ne contient pas un type de service Internet connu.  
  
### <a name="remarks"></a>Remarques  
 Il analyse une chaîne URL et retourne le type de service et ses composants.  
  
 Par exemple, `AfxParseURL` analyse les URL de la forme **service://server/dir/dir/object.ext:port** et retourne ses composants, comme suits :  
  
 `strServer`== « server »  
  
 `strObject`== « / dir/dir/object/object.ext »  
  
 `nPort`== #port  
  
 `dwServiceType`== #service  
  
> [!NOTE]
>  Pour appeler cette fonction, votre projet doit inclure AFXINET. H.  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxinet.h  
  
##  <a name="afxparseurlex"></a>AfxParseURLEx  
 Cette fonction globale est la version étendue du [AfxParseURL](#afxparseurl) et est utilisée dans [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
```   
BOOL AFXAPI AfxParseURLEx(
    LPCTSTR pstrURL,  
    DWORD& dwServiceType,  
    CString& strServer,  
    CString& strObject,  
    INTERNET_PORT& nPort,  
    CString& strUsername,  
    CString& strPassword,  
    DWORD dwFlags = 0); 
```  
  
### <a name="parameters"></a>Paramètres  
 *pstrURL*  
 Un pointeur vers une chaîne contenant l’URL à analyser.  
  
 `dwServiceType`  
 Indique le type de service Internet. Les valeurs possibles sont les suivantes :  
  
-   AFX_INET_SERVICE_FTP  
  
-   AFX_INET_SERVICE_HTTP  
  
-   AFX_INET_SERVICE_HTTPS  
  
-   AFX_INET_SERVICE_GOPHER  
  
-   AFX_INET_SERVICE_FILE  
  
-   AFX_INET_SERVICE_MAILTO  
  
-   AFX_INET_SERVICE_NEWS  
  
-   AFX_INET_SERVICE_NNTP  
  
-   AFX_INET_SERVICE_TELNET  
  
-   AFX_INET_SERVICE_WAIS  
  
-   AFX_INET_SERVICE_MID  
  
-   AFX_INET_SERVICE_CID  
  
-   AFX_INET_SERVICE_PROSPERO  
  
-   AFX_INET_SERVICE_AFS  
  
-   AFX_INET_SERVICE_UNK  
  
 `strServer`  
 Le premier segment de l’URL qui suit le type de service.  
  
 `strObject`  
 Un objet qui désigne l’URL (peut être vide).  
  
 `nPort`  
 Déterminé à partir du serveur ou l’objet des portions de l’URL, si elles existent.  
  
 *strUsername*  
 Une référence à un `CString` objet contenant le nom de l’utilisateur.  
  
 `strPassword`  
 Une référence à un `CString` objet contenant le mot de passe de l’utilisateur.  
  
 `dwFlags`  
 Les indicateurs de contrôle de l’analyse de l’URL. Peut être une combinaison des valeurs suivantes :  
  
|Valeur|Signification|  
|-----------|-------------|  
|**ICU_DECODE**|Convertir les séquences d’échappement % XX en caractères.|  
|**ICU_NO_ENCODE**|Pas de conversion des caractères non sécurisés pour la séquence d’échappement.|  
|**ICU_NO_META**|Ne supprimez pas les séquences de métadonnées (par exemple, « \ ». et « \ »..) à partir de l’URL.|  
|**ICU_ENCODE_SPACES_ONLY**|Encoder des espaces uniquement.|  
|**ICU_BROWSER_MODE**|Ne pas encoder ou décoder les caractères après « # » ou « » et ne supprimez pas l’espace blanc de fin après ''. Si cette valeur n’est pas spécifiée, l’URL entière est encodée et espace blanc de fin est supprimé.|  
  
 Si vous utilisez la valeur par défaut MFC, c'est-à-dire aucun indicateur, la fonction convertit tous les caractères non sécurisés et les séquences de métadonnées (tel que \\., \.., et \\...) pour échapper les séquences.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’URL a été analysée avec succès ; Sinon, 0 si elle est vide ou ne contient pas un type de service Internet connu.  
  
### <a name="remarks"></a>Remarques  
 Il analyse une chaîne URL et retourne le type de service et ses composants, ainsi en fournissant le nom et mot de passe de l’utilisateur. Les indicateurs indiquent comment unsafe caractères sont gérées.  
  
> [!NOTE]
>  Pour appeler cette fonction, votre projet doit inclure AFXINET. H.  

### <a name="requirements"></a>Spécifications  
  **En-tête** afxinet.h  
    
## <a name="see-also"></a>Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)
 
## <a name="afxgetinternethandletype"></a>AfxGetInternetHandleType
Utilisez cette fonction globale pour déterminer le type d’un handle d’Internet.  
   
### <a name="syntax"></a>Syntaxe  
  ```
DWORD AFXAPI AfxGetInternetHandleType(  HINTERNET hQuery );  
```
### <a name="parameters"></a>Paramètres  
 `hQuery`  
 Un handle à une requête Internet.  
   
### <a name="return-value"></a>Valeur de retour  
 Les types de service Internet définis par WININET. H. Consultez la section Notes pour obtenir la liste de ces services Internet. Si le handle est NULL ou n’est pas reconnu, la fonction retourne AFX_INET_SERVICE_UNK.  
   
### <a name="remarks"></a>Remarques  
 La liste suivante inclut les types possibles Internet retournés par `AfxGetInternetHandleType`.  
  
-   INTERNET_HANDLE_TYPE_INTERNET  
  
-   INTERNET_HANDLE_TYPE_CONNECT_FTP  
  
-   INTERNET_HANDLE_TYPE_CONNECT_GOPHER  
  
-   INTERNET_HANDLE_TYPE_CONNECT_HTTP  
  
-   INTERNET_HANDLE_TYPE_FTP_FIND  
  
-   INTERNET_HANDLE_TYPE_FTP_FIND_HTML  
  
-   INTERNET_HANDLE_TYPE_FTP_FILE  
  
-   INTERNET_HANDLE_TYPE_FTP_FILE_HTML  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FIND  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FIND_HTML  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FILE  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FILE_HTML  
  
-   INTERNET_HANDLE_TYPE_HTTP_REQUEST  
  
> [!NOTE]
>  Pour pouvoir appeler cette fonction, votre projet doit inclure AFXINET. H.  
   
### <a name="requirements"></a>Spécifications  
 **En-tête :** afxinet.h  
   
### <a name="see-also"></a>Voir aussi  
 [Macros et objet Globals](mfc-macros-and-globals.md)   
 [AfxParseURL](internet-url-parsing-globals.md#afxparseurl)
 
## <a name="afxthrowinternetexception"></a>AfxThrowInternetException
Lève une exception d’Internet.  
   
### <a name="syntax"></a>Syntaxe    
```
   void AFXAPI AfxThrowInternetException(  DWORD dwContext,  DWORD dwError = 0 );  
```
### <a name="parameters"></a>Paramètres  
 `dwContext`  
 L’identificateur de contexte pour l’opération qui a provoqué l’erreur. La valeur par défaut `dwContext` est spécifié à l’origine dans [CInternetSession](cinternetsession-class.md) et est transmis à [CInternetConnection](cinternetconnection-class.md)- et [CInternetFile](cinternetfile-class.md)-classes dérivées. Pour les opérations effectuées sur une connexion ou un fichier spécifiques, vous substituez généralement la valeur par défaut avec un `dwContext` de votre choix. Cette valeur est ensuite renvoyée au [CInternetSession::OnStatusCallback](cinternetsession-class.md#onstatuscallback) pour identifier l’état de l’opération spécifique. 
  
 `dwError`  
 L’erreur qui a provoqué l’exception.  
   
### <a name="remarks"></a>Notes  
 Vous êtes responsable de la détermination de la cause en fonction du code d’erreur du système d’exploitation.  
  
> [!NOTE]
>  Pour appeler cette fonction, votre projet doit inclure AFXINET. H.  
   
### <a name="requirements"></a>Spécifications  
 **En-tête :** afxinet.h  
   
### <a name="see-also"></a>Voir aussi  
 [Macros et objet Globals](mfc-macros-and-globals.md)   
 [Classe de CInternetException](cinternetexception-class.md)   
 [THROW](#throw)
 

