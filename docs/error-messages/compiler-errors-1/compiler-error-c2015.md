---
title: Compilerfehler C2015
ms.date: 11/04/2016
f1_keywords:
- C2015
helpviewer_keywords:
- C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
ms.openlocfilehash: 83b78336d74037b9f9f52da8327479f506db1ffc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751068"
---
# <a name="compiler-error-c2015"></a>Compilerfehler C2015

zu viele Zeichen in der Konstante

Eine Zeichen Konstante enthält mehr als zwei Zeichen. Das Limit ist ein Zeichen für Standard Zeichen Konstanten und zwei Zeichen für Long-Zeichen Konstanten.

Eine Escapesequenz, z. b. \t, wird in ein einzelnes Zeichen konvertiert.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2015 generiert:

```cpp
// C2015.cpp
// compile with: /c

char test1 = 'error';   // C2015
char test2 = 'e';   // OK
```

## <a name="example"></a>Beispiel

C2015 kann auch auftreten, wenn eine Microsoft-Erweiterung, Zeichen Konstanten, die in ganze Zahlen konvertiert werden, verwendet wird.  Im folgenden Beispiel wird C2015 generiert:

```cpp
// C2015b.cpp
#include <stdio.h>

int main()
{
    int a = 'abcde';   // C2015

    int b = 'a';   // 'a' = ascii 0x61
    printf_s("%x\n", b);
}
```
