---
title: Compilerfehler C2084 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2084
dev_langs:
- C++
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 09ce703b6908257e37c2b7ff1b2714f1426f941f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052106"
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