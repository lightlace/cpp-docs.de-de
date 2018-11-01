---
title: Compilerfehler C2383
ms.date: 11/04/2016
f1_keywords:
- C2383
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
ms.openlocfilehash: 06d4c19208bd242169e1cd07a71e8a568f46f7b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466091"
---
# <a name="compiler-error-c2383"></a>Compilerfehler C2383

"*Symbol*': Standardargumente dürfen nicht auf dieses Symbol

Der C++-Compiler lässt die Standardargumente für Zeiger auf Funktionen nicht.

Dieser Code wurde vom Visual C++-Compiler in Versionen vor Visual Studio 2005 akzeptiert, jetzt jedoch einen Fehler. Weisen Sie für Code, der in allen Versionen von Visual C++ funktioniert einen Standardwert nicht auf ein Zeiger auf Funktion-Argument.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C2383 generiert und gezeigt, eine mögliche Lösung:

```cpp
// C2383.cpp
// compile with: /c
void (*pf)(int = 0);   // C2383
void (*pf)(int);   // OK
```