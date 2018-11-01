---
title: Compilerfehler C2015
ms.date: 11/04/2016
f1_keywords:
- C2015
helpviewer_keywords:
- C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
ms.openlocfilehash: d761dfde26cce9c99ccd4c3e6fd86ae1d6e16ddc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573275"
---
# <a name="compiler-error-c2015"></a>Compilerfehler C2015

zu viele Zeichen in Konstante.

Eine Zeichenkonstante enthält mehr als zwei Zeichen. Der Grenzwert ist ein Zeichen für standard-Zeichenkonstanten und zwei Zeichen lange Zeichenkonstanten.

Eine Escapesequenz, z. B. \t, wird in ein einzelnes Zeichen konvertiert.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2015 generiert:

```
// C2015.cpp
// compile with: /c

char test1 = 'error';   // C2015
char test2 = 'e';   // OK
```

## <a name="example"></a>Beispiel

C2015 kann auch auftreten, wenn eine Microsoft-Erweiterung, Zeichenkonstanten, die zu einer ganzen Zahl konvertiert.  Im folgende Beispiel wird die C2015 generiert:

```
// C2015b.cpp
#include <stdio.h>

int main()
{
    int a = 'abcde';   // C2015

    int b = 'a';   // 'a' = ascii 0x61
    printf_s("%x\n", b);
}
```