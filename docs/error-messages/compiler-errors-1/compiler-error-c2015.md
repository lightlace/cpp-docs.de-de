---
title: Compilerfehler C2015 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2015
dev_langs:
- C++
helpviewer_keywords:
- C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5fb9c3ba86224906f749088b96e5daae364d99e2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076046"
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