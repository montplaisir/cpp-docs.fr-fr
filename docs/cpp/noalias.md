---
title: noalias | Microsoft Docs
ms.custom: ''
ms.date: 02/09/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- noalias_cpp
dev_langs:
- C++
helpviewer_keywords:
- noalias __declspec keyword
- __declspec keyword [C++], noalias
ms.assetid: efafa8b0-7f39-4edc-a81e-d287ae882c9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 56ee12f65ff9efe9f3b048d061b80aef691eb0f2
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404393"
---
# <a name="noalias"></a>noalias

**Section spécifique à Microsoft**

**noalias** signifie qu’un appel de fonction ne pas modifier ou faire référence à un état global visible et modifie uniquement la mémoire pointée *directement* par les paramètres de pointeur (indirections de premier niveau).

Si une fonction est annotée en tant que **noalias**, l’optimiseur peut supposer que, outre les paramètres eux-mêmes, indirections de premier niveau uniquement des paramètres de pointeur sont référencées ou modifiées à l’intérieur de la fonction. L'état global visible est l'ensemble de toutes les données qui ne sont pas définies ou référencées en dehors de la portée de compilation, et leur adresse n'est pas prise. La portée de compilation est tous les fichiers sources ([/LTCG (Link-time Code Generation)](../build/reference/ltcg-link-time-code-generation.md) génère) ou un fichier source unique (non -**/LTCG** build).

Le **noalias** annotation s’applique uniquement dans le corps de la fonction annoté. Marquage d’une fonction en tant que **__declspec (noalias)** n’affecte pas les alias des pointeurs retournés par la fonction.

Pour une autre annotation qui peut affecter les alias, consultez [__declspec (Restrict)](../cpp/restrict.md).

## <a name="example"></a>Exemple

L’exemple suivant illustre l’utilisation de **__declspec (noalias)**.

Lorsque la fonction `multiply` que les accès mémoire est annoté **__declspec (noalias)**, il indique au compilateur que cette fonction ne modifie pas l’état global, à l’exception à travers les pointeurs dans sa liste de paramètres.

```C
// declspec_noalias.c
#include <stdio.h>
#include <stdlib.h>

#define M 800
#define N 600
#define P 700

float * mempool, * memptr;

float * ma(int size)
{
    float * retval;
    retval = memptr;
    memptr += size;
    return retval;
}

float * init(int m, int n)
{
    float * a;
    int i, j;
    int k=1;

    a = ma(m * n);
    if (!a) exit(1);
    for (i=0; i<m; i++)
        for (j=0; j<n; j++)
            a[i*n+j] = 0.1/k++;
    return a;
}

__declspec(noalias) void multiply(float * a, float * b, float * c)
{
    int i, j, k;

    for (j=0; j<P; j++)
        for (i=0; i<M; i++)
            for (k=0; k<N; k++)
                c[i * P + j] =
                          a[i * N + k] *
                          b[k * P + j];
}

int main()
{
    float * a, * b, * c;

    mempool = (float *) malloc(sizeof(float) * (M*N + N*P + M*P));

    if (!mempool)
    {
        puts("ERROR: Malloc returned null");
        exit(1);
    }

    memptr = mempool;
    a = init(M, N);
    b = init(N, P);
    c = init(M, P);
 
    multiply(a, b, c);
}
```

## <a name="see-also"></a>Voir aussi
 [__declspec](../cpp/declspec.md)  
 [Mots clés](../cpp/keywords-cpp.md)  
 [__declspec(restrict)](../cpp/restrict.md)  
