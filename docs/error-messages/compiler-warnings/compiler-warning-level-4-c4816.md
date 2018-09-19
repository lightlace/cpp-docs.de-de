---
title: Compilerwarnung (Stufe 4) C4816 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4816
dev_langs:
- C++
helpviewer_keywords:
- C4816
ms.assetid: 60f730ae-d942-4db9-ab97-41d4a874d8da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c0d70204e61f1e37157b9e1b23664cf1f5d24b2c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096001"
---
# <a name="compiler-warning-level-4-c4816"></a>Compilerwarnung (Stufe 4) C4816

'Param': Parameter hat ein Array der Größe 0, das abgeschnitten wird (sofern das Objekt nicht als Verweis übergeben wird).

Ein Parameter für ein Objekt mit einem Array der Größe 0 wurde nicht als Verweis übergeben. Das Array wird bei der Übergabe des Objekts nicht kopiert.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4816 generiert.

```
// C4816.cpp
// compile with: /W4
#include <stdio.h>

extern "C" int printf_s(const char *, ...);

#pragma warning(disable : 4200)

struct S1
{
    int i;
    char cArr[];
};

void TestErr(S1 s1)   // C4816 param with zero-array
                      // not passed by reference
{
    printf_s("%d %c %c\n", s1.i, s1.cArr[0], s1.cArr[1]);
}

void TestOk(S1 &s1)
{
    printf_s("%d %c %c\n", s1.i, s1.cArr[0], s1.cArr[1]);
}

int main()
{
    S1 myS_1 = { 6, 'a', 'b', 'c' };
    TestErr(myS_1);
    TestOk(myS_1);
}
```