---
title: Compilerfehler C2381
ms.date: 11/04/2016
f1_keywords:
- C2381
helpviewer_keywords:
- C2381
ms.assetid: cc765f67-64ac-406f-93ef-ae7d548d58d7
ms.openlocfilehash: b29f7dac6c6d71e12eb0f003cdfc151dd2c349a7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663187"
---
# <a name="compiler-error-c2381"></a>Compilerfehler C2381

'Funktion': Neudefinition; __declspec(noreturn) unterscheidet sich

Eine Funktion wurde deklariert, und klicken Sie dann definiert, aber die Definition verwendet die [Noreturn](../../cpp/noreturn.md) `__declspec` Modifizierer. Die Verwendung von `noreturn` Neudefinition der Funktion, die Deklaration und Definition müssen bei der Verwendung von einigen `noreturn`.

Im folgende Beispiel wird die C2381 generiert:

```
// C2381.cpp
// compile with: /c
void f1();
void __declspec(noreturn) f1() {}   // C2381
void __declspec(noreturn) f2() {}   // OK
```