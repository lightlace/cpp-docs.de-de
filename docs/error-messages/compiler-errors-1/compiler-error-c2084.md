---
title: Compilerfehler C2084
ms.date: 11/04/2016
f1_keywords:
- C2084
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
ms.openlocfilehash: 9aaf3a88e63234dfb842e4b48afd6e55595e96ca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391919"
---
# <a name="compiler-error-c2084"></a>Compilerfehler C2084

Funktion "*Funktion*" hat bereits einen Funktionsrumpf

Die Funktion wurde bereits definiert.

In Versionen von Visual C++ vor Visual Studio 2002

- Der Compiler akzeptiert mehrere vorlagenspezialisierungen, die in den gleichen tatsächlichen Typ aufgelöst, obwohl die zusätzlichen Definitionen nicht zur Verfügung stehen würden. Der Compiler erkennt jetzt diese Definitionen.

- `__int32` und `int` als separate Typen behandelt wurden. Der Compiler jetzt behandelt `__int32` als Synonym für `int`. Dies bedeutet, dass der Compiler mehrere Definitionen erkennt, wenn eine Funktion, auf beiden überladen ist `__int32` und `int` und gibt einen Fehler aus.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2084 generiert:

```cpp
// C2084.cpp
void Func(int);
void Func(int) {}   // define function
void Func(int) {}   // C2084 second definition
```

Um diesen Fehler zu beheben, entfernen Sie die doppelte Definition:

```
// C2084b.cpp
// compile with: /c
void Func(int);
void Func(int) {}
```