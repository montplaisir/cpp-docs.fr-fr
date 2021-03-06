---
title: Erreurs du compilateur C2300 Through C2399 | Documents Microsoft
ms.custom: ''
ms.date: 11/17/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2303
- C2304
- C2305
- C2306
- C2314
- C2321
- C2323
- C2328
- C2329
- C2330
- C2331
- C2335
- C2336
- C2339
- C2340
- C2342
- C2343
- C2347
- C2354
- C2358
- C2359
- C2363
- C2366
- C2367
- C2398
- C2399
helpviewer_keywords:
- C2303
- C2304
- C2305
- C2306
- C2314
- C2321
- C2323
- C2328
- C2329
- C2330
- C2331
- C2335
- C2336
- C2339
- C2340
- C2342
- C2343
- C2347
- C2354
- C2358
- C2359
- C2363
- C2366
- C2367
- C2398
- C2399
dev_langs:
- C++
ms.assetid: 07ca45b5-b2f0-4049-837b-40a7a3caed88
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d8b758ce26897d5c2ad8baa176c8a83b2c9954df
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33237529"
---
# <a name="compiler-errors-c2300-through-c2399"></a>Erreur du compilateurs C2300 Through C2399

Les articles de cette section de la documentation expliquent un sous-ensemble des messages d’erreur générés par le compilateur.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>Messages d’erreur

|Error|Message|
|-----------|-------------|
|[Erreur du compilateur C2300](compiler-error-c2300.md)|'*classe*' : classe n’a pas de destructeur appelé ' ~*classe*'|
|[Erreur du compilateur C2301](compiler-error-c2301.md)|gauche de ' -> ~*identificateur*' doit pointer vers la classe/struct/union|
|[Erreur du compilateur C2302](compiler-error-c2302.md)|gauche de '. ~*identificateur*' doit avoir de type class/struct/union|
|C2303 d’erreur du compilateur|Gestion structurée des exceptions ne peut pas être utilisée dans une coroutine|
|C2304 d’erreur du compilateur|'*mot clé*' ne peut pas être utilisé à l’intérieur d’un bloc catch|
|C2305 d’erreur du compilateur|'*fichier*' ne contient pas les informations de débogage pour ce module|
|C2306 d’erreur du compilateur|'*fichier*' ne contient pas les dernières informations de débogage pour ce module|
|[Erreur du compilateur C2307](compiler-error-c2307.md)|pragma *directive* doit être déplacé en dehors de la fonction si la compilation incrémentielle est activée.|
|[Erreur du compilateur C2308](compiler-error-c2308.md)|concaténation de chaînes incompatibles|
|[Erreur du compilateur C2309](compiler-error-c2309.md)|une déclaration d’exception entre parenthèses attendue par le Gestionnaire de catch|
|[Erreur du compilateur C2310](compiler-error-c2310.md)|gestionnaires catch doivent spécifier un type|
|[Erreur du compilateur C2311](compiler-error-c2311.md)|'*type*' : intercepté par '...' à la ligne *nombre*|
|[Erreur du compilateur C2312](compiler-error-c2312.md)|'*type1*' : intercepté par '*type2*' sur la ligne *nombre*|
|[Erreur du compilateur C2313](compiler-error-c2313.md)|'*type1*' : intercepté par la référence ('*type2*») sur la ligne *nombre*|
|C2314 d’erreur du compilateur|mot clé '*mot_clé1*' est déconseillée : utilisez '*mot Clé2*' à la place|
|[Erreur du compilateur C2315](compiler-error-c2315.md)|'*type1*' : référence interceptée par '*type2*' sur la ligne *nombre*|
|[Erreur du compilateur C2316](compiler-error-c2316.md)|'*type*' : ne peut pas être intercepté que destructeur et/ou le constructeur de copie est inaccessible ou supprimé|
|[Erreur du compilateur C2317](compiler-error-c2317.md)|'try' commençant ligne de bloc '*nombre*' n’a aucuns gestionnaires catch|
|[Erreur du compilateur C2318](compiler-error-c2318.md)|aucun bloc try associé à ce gestionnaire catch|
|[Erreur du compilateur C2319](compiler-error-c2319.md)|'try/catch' doit être suivi(e) d’une instruction composée. Accolade '{' manquante|
|[Erreur du compilateur C2320](compiler-error-c2320.md)|attendu ' :' après le spécificateur d’accès '*spécificateur*'|
|C2321 d’erreur du compilateur|'*identificateur*' est un mot clé et ne peut pas être utilisé dans ce contexte|
|[Erreur du compilateur C2322](compiler-error-c2322.md)|'*identificateur*' : adresse de dllimport '*identificateur*' n’est pas statique|
|C2323 d’erreur du compilateur|'*identificateur*' : opérateur non membre new ou delete fonctions ne peuvent pas être déclarées static ou dans un espace de noms autre que l’espace de noms global|
|[Erreur du compilateur C2324](compiler-error-c2324.md)|'*identificateur*' : inattendu à droite de ' :: ~'|
|[Erreur du compilateur C2325](compiler-error-c2325.md)|'*type1*' : type inattendu à droite de ' -> ~': attendu '*type2*'|
|[Erreur du compilateur C2326](compiler-error-c2326.md)|'*déclarateur*' : fonction ne peut pas accéder à '*identificateur*'|
|[Erreur du compilateur C2327](compiler-error-c2327.md)|'*identificateur*' : n’est pas un nom de type, statique ou énumérateur|
|C2328 d’erreur du compilateur|'*mot clé*' : mot clé n’est pas encore pris en charge|
|C2329 d’erreur du compilateur|'*identificateur*' : __ptr64 non disponible pour les pointeurs vers des fonctions|
|C2330 d’erreur du compilateur|'implementation_key ()' est valide uniquement dans une région délimitée par #pragma start_map_region/stop_map_region|
|C2331 d’erreur du compilateur|l’accès à '*identificateur*'défini maintenant comme'*accessibility1*«, précédemment, il a été défini à »*accessibility2*'|
|[Erreur du compilateur C2332](compiler-error-c2332.md)|'*typedef*' : nom de balise manquant|
|[Erreur du compilateur C2333](compiler-error-c2333.md)|'*fonction*' : erreur dans la déclaration de fonction ; corps de la fonction ignoré|
|[Erreur du compilateur C2334](compiler-error-c2334.md)|jetons inattendus avant '*jeton*' ; les corps apparent de la fonction ignoré|
|C2335 d’erreur du compilateur|'*identificateur*' : un type ne peut pas être introduit dans une liste de paramètres de fonction|
|C2336 d’erreur du compilateur|'*type*' : type non conforme|
|[Erreur du compilateur C2337](compiler-error-c2337.md)|'*attribut*' : attribut introuvable|
|[Erreur du compilateur C2338](compiler-error-c2338.md)|*(message d’erreur du fournisseur externe)*|
|C2339 d’erreur du compilateur|'*identificateur*' : type non conforme dans un IDL incorporé|
|C2340 d’erreur du compilateur|'*identificateur*' : 'static' peut uniquement être utilisé dans une définition de classe|
|[Erreur du compilateur C2341](compiler-error-c2341.md)|'*section*' : segment doit être défini à l’aide de #pragma data_seg, code_seg ou section avant d’utiliser|
|C2342 d’erreur du compilateur|Erreur de syntaxe : les qualificateurs de type en conflit|
|C2343 d’erreur du compilateur|'*section*' : attributs en conflit de la section|
|[Erreur du compilateur C2344](compiler-error-c2344.md)|align (*nombre*) : alignement doit être une puissance de deux|
|[Erreur du compilateur C2345](compiler-error-c2345.md)|align (*nombre*) : valeur d’alignement non conforme|
|[Erreur du compilateur C2346](compiler-error-c2346.md)|'*fonction*' ne peuvent pas être compilées en natif : '*explication*'|
|Erreur du compilateur C2347|Obsolète.|
|[Erreur du compilateur C2348](compiler-error-c2348.md)|'*type*' : n’est pas un agrégat de style C, ne peut pas être exporté dans un IDL incorporé|
|[Erreur du compilateur C2349](compiler-error-c2349.md)|'*fonction*' ne peut pas être compilé comme code managé : '*explication*' ; utilisez #pragma unmanaged|
|[Erreur du compilateur C2350](compiler-error-c2350.md)|'*identificateur*' n’est pas un membre statique|
|[Erreur du compilateur C2351](compiler-error-c2351.md)|syntaxe obsolète d’initialisation constructeur C++|
|[Erreur du compilateur C2352](compiler-error-c2352.md)|'*identificateur*' : appel non conforme d’une fonction membre non statique|
|[Erreur du compilateur C2353](compiler-error-c2353.md)|spécification d’exception n’est pas autorisée.|
|C2354 d’erreur du compilateur|Obsolète.|
|[Erreur du compilateur C2355](compiler-error-c2355.md)|'this' : ne peut être référencée à l’intérieur de fonctions membres non static ou d’initialiseurs de membres de données non statiques|
|[Erreur du compilateur C2356](compiler-error-c2356.md)|un segment d’initialisation ne doit pas changer au cours de l’unité de traduction|
|[Erreur du compilateur C2357](compiler-error-c2357.md)|'*identificateur*' : doit être une fonction de type '*type*'|
|C2358 d’erreur du compilateur|'*identificateur*' : une propriété statique ne peut pas être définie en dehors d’une définition de classe|
|C2359 d’erreur du compilateur|Obsolète.|
|[Erreur du compilateur C2360](compiler-error-c2360.md)|l’initialisation de '*identificateur*' est ignorée par l’étiquette 'case'|
|[Erreur du compilateur C2361](compiler-error-c2361.md)|l’initialisation de '*identificateur*' est ignorée par l’étiquette 'default'|
|[Erreur du compilateur C2362](compiler-error-c2362.md)|l’initialisation de '*identificateur*' est ignorée par ' goto *étiquette*'|
|Erreur C2363 erreur de compilateur|fonction de limite numérique intrinsèque du compilateur nécessite un argument de littéral de chaîne|
|[Erreur du compilateur C2364](compiler-error-c2364.md)|'*type*' : type d’attribut personnalisé non conforme|
|[Erreur du compilateur C2365](compiler-error-c2365.md)|'*member1*' : redéfinition ; la précédente définition était '*membre2*'|
|C2366 d’erreur du compilateur|'*identificateur*' : redéfinition ; spécificateurs implementation_key différents|
|C2367 d’erreur du compilateur|Obsolète.|
|[Erreur du compilateur C2368](compiler-error-c2368.md)|'*identificateur*' : redéfinition ; spécificateurs d’allocation différents|
|[Erreur du compilateur C2369](compiler-error-c2369.md)|'*identificateur*' : redéfinition ; indices différents|
|[Erreur du compilateur C2370](compiler-error-c2370.md)|'*identificateur*' : redéfinition ; classe de stockage différente|
|[Erreur du compilateur C2371](compiler-error-c2371.md)|'*identificateur*' : redéfinition ; types de base différents|
|[Erreur du compilateur C2372](compiler-error-c2372.md)|'*identificateur*' : redéfinition ; types d’indirection différents|
|[Erreur du compilateur C2373](compiler-error-c2373.md)|'*identificateur*' : redéfinition ; modificateurs de type différents|
|[Erreur du compilateur C2374](compiler-error-c2374.md)|'*identificateur*' : redéfinition ; initialisation multiple|
|[Erreur du compilateur C2375](compiler-error-c2375.md)|'*identificateur*' : redéfinition ; liaison différente|
|[Erreur du compilateur C2376](compiler-error-c2376.md)|'*identificateur*' : redéfinition ; allocation de base différente|
|[Erreur du compilateur C2377](compiler-error-c2377.md)|'*identificateur*' : redéfinition ; typedef ne peut pas être surchargé avec un autre symbole|
|[Erreur du compilateur C2378](compiler-error-c2378.md)|'*identificateur*' : redéfinition ; symbole ne peut pas être surchargé avec un typedef|
|[Erreur du compilateur C2379](compiler-error-c2379.md)|paramètre formel *nombre* a un type différent lors de sa promotion|
|[Erreur du compilateur C2380](compiler-error-c2380.md)|type (s) précédant '*identificateur*' (constructeur avec type de retour ou redéfinition non conforme du nom de classe actif ?)|
|[Erreur du compilateur C2381](compiler-error-c2381.md)|'*identificateur*' : redéfinition ; diffère de '__declspec (noreturn)' ou '[[noreturn]]'|
|[Erreur du compilateur C2382](compiler-error-c2382.md)|'*identificateur*' : redéfinition ; spécifications des exceptions différentes|
|[Erreur du compilateur C2383](compiler-error-c2383.md)|'*identificateur*' : les arguments par défaut ne sont pas autorisés sur ce symbole|
|[Erreur du compilateur C2384](compiler-error-c2384.md)|'*membre*' : Impossible d’appliquer thread_local ou __declspec (thread) à un membre d’une classe gérée/WinRT|
|[Erreur du compilateur C2385](compiler-error-c2385.md)|accès ambigu de '*membre*'|
|[Erreur du compilateur C2386](compiler-error-c2386.md)|'*identificateur*' : un symbole avec ce nom existe déjà dans la portée actuelle|
|[Erreur du compilateur C2387](compiler-error-c2387.md)|'*identificateur*' : classe de base ambiguë|
|[Erreur du compilateur C2388](compiler-error-c2388.md)|'*identificateur*' : un symbole ne peut pas être déclaré avec __declspec (Process) et __declspec(appdomain)|
|[Erreur du compilateur C2389](compiler-error-c2389.md)|'*opérateur*' : opérande 'nullptr' non conforme|
|[Erreur du compilateur C2390](compiler-error-c2390.md)|'*identificateur*' : classe de stockage incorrecte*spécificateur*'|
|[Erreur du compilateur C2391](compiler-error-c2391.md)|'*identificateur*' : 'friend' ne peut pas être utilisé lors de la définition de type|
|[Erreur du compilateur C2392](compiler-error-c2392.md)|'*member1*' : types ne sont pas pris en charge dans les types de managed/WinRT, dans le cas contraire de retour covariants '*membre2*' est substitué|
|[Erreur du compilateur C2393](compiler-error-c2393.md)|'*symbole*' : symbole par appdomain ne peut pas être alloué dans le segment '*segment*'|
|[Erreur du compilateur C2394](compiler-error-c2394.md)|'*type*:: opérateur *opérateur*' : opérateur CLR/WinRT non valide. Au moins un paramètre doit être des types suivants : ' t ^', ' t ^ %', ' t ^ &', où T = '*type*'|
|[Erreur du compilateur C2395](compiler-error-c2395.md)|'*type*:: opérateur *opérateur*' : opérateur CLR/WinRT non valide. Au moins un paramètre doit être des types suivants : ' t ', ' t %', ' t &', ' t ^', ' t ^ %', ' t ^ &', où T = '*type*'|
|[Erreur du compilateur C2396](compiler-error-c2396.md)|'*type1*:: opérateur *type2*' : fonction de conversion définie par l’utilisateur CLR/WinRT non valide. Doit soit opérée depuis ou vers : ' t ^', ' t ^ %', ' t ^ &', où T = '*type1*'|
|[Erreur du compilateur C2397](compiler-error-c2397.md)|la conversion de '*type1*'à'*type2*' requiert une conversion restrictive|
|C2398 d’erreur du compilateur|Élément '*nombre*' : conversion de '*type1*'à'*type2*' requiert une conversion restrictive|
|C2399 d’erreur du compilateur|Obsolète.|
