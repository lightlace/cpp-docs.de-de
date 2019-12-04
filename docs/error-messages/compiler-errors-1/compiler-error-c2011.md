---
title: Compilerfehler C2011
ms.date: 11/04/2016
f1_keywords:
- C2011
helpviewer_keywords:
- C2011
ms.assetid: 992c9d51-e850-4d53-b86b-02e73b38249c
ms.openlocfilehash: dc13829a267deea1f412eb2d8f86057f01dc0e1c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752417"
---
# <a name="compiler-error-c2011"></a>Compilerfehler C2011

"Bezeichner": "Typ" Typneudefinition

Der Bezeichner wurde bereits als `type` definiert. Überprüfen Sie, ob Neudefinitionen des Bezeichners vorliegen.

Beim Import tritt möglicherweise auch der Fehler C2011 auf, wenn Sie eine Headerdatei oder Typbibliothek mehrfach in dieselbe Datei importieren. Verwenden Sie include-Wächter oder eine `#pragma`[Once](../../preprocessor/once.md) -Direktive in der Header Datei, um zu verhindern, dass mehrere Einschlüsse der in einer Header Datei definierten Typen enthalten sind.

Wenn Sie die anfängliche Deklaration des neu definierten Typs suchen müssen, können Sie das [/P](../../build/reference/p-preprocess-to-a-file.md) -Compilerflag verwenden, um die vorverarbeitete Ausgabe zu generieren, die an den Compiler übermittelt wird. Mit Textsuchtools können Sie nach Instanzen der neu definierten Bezeichner in der Ausgabedatei suchen.

Im folgenden Beispiel wird C2011 generiert und eine Möglichkeit gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C2011.cpp
// compile with: /c
struct S;
union S;   // C2011
union S2;   // OK
```
