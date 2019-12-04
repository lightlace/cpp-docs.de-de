---
title: Compilerfehler C2381
ms.date: 11/04/2016
f1_keywords:
- C2381
helpviewer_keywords:
- C2381
ms.assetid: cc765f67-64ac-406f-93ef-ae7d548d58d7
ms.openlocfilehash: 834b9939a99c694c702bb268b928575b4beb8856
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745394"
---
# <a name="compiler-error-c2381"></a>Compilerfehler C2381

"Function": Neudefinition; __declspec (noreturn) unterscheidet sich

Eine Funktion wurde deklariert und dann definiert, aber die Definition hat den [noreturn](../../cpp/noreturn.md) -`__declspec` Modifizierer verwendet. Die Verwendung von `noreturn` stellt eine Neudefinition der Funktion dar. bei der Deklaration und Definition muss die Verwendung von `noreturn`zugestimmt werden.

Im folgenden Beispiel wird C2381 generiert:

```cpp
// C2381.cpp
// compile with: /c
void f1();
void __declspec(noreturn) f1() {}   // C2381
void __declspec(noreturn) f2() {}   // OK
```
