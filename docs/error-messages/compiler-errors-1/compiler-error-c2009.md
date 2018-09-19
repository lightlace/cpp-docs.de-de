---
title: Compilerfehler C2009 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2009
dev_langs:
- C++
helpviewer_keywords:
- C2009
ms.assetid: fe9d94ed-20a5-4d83-b9c4-60ee69d2f30a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2a6baaed5ed0569f5bc7e71314f8b27d8f6de6b0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016394"
---
# <a name="compiler-error-c2009"></a>Compilerfehler C2009

Mehrfachverwendung des formalen Makroparameters "identifier"

Die Liste der formalen Parameter einer Makrodefinition wird den Bezeichner mehrfach verwendet. Bezeichner in der Parameterliste des Makros müssen eindeutig sein.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2009 generiert:

```
// C2009.cpp
#include <stdio.h>

#define macro1(a,a) (a*a)   // C2009

int main()
{
    printf_s("%d\n", macro1(2));
}
```

## <a name="example"></a>Beispiel

Mögliche Lösung:

```
// C2009b.cpp
#include <stdio.h>

#define macro2(a)   (a*a)
#define macro3(a,b) (a*b)

int main()
{
    printf_s("%d\n", macro2(2));
    printf_s("%d\n", macro3(2,4));
}
```