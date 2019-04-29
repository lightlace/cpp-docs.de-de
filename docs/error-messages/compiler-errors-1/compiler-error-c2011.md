---
title: Compilerfehler C2011
ms.date: 11/04/2016
f1_keywords:
- C2011
helpviewer_keywords:
- C2011
ms.assetid: 992c9d51-e850-4d53-b86b-02e73b38249c
ms.openlocfilehash: 14969c9cdf4b00844d2001bf4817ea7ffc9bfba6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62361554"
---
# <a name="compiler-error-c2011"></a>Compilerfehler C2011

"Bezeichner": "Typ" Typneudefinition

Der Bezeichner wurde bereits als `type` definiert. Überprüfen Sie, ob Neudefinitionen des Bezeichners vorliegen.

Beim Import tritt möglicherweise auch der Fehler C2011 auf, wenn Sie eine Headerdatei oder Typbibliothek mehrfach in dieselbe Datei importieren. #Include-Schutz um mehrfache einbindungen von in einer Headerdatei definierten Typen zu verhindern, verwenden oder ein `#pragma` [nach](../../preprocessor/once.md) -Direktive in der Headerdatei.

Wenn Sie die ursprüngliche Deklaration eines neu definierten Typs suchen müssen, können Sie mithilfe der [/p](../../build/reference/p-preprocess-to-a-file.md) Compilerflag die vorverarbeitete Ausgabe zu generieren, die an den Compiler übergeben. Mit Textsuchtools können Sie nach Instanzen der neu definierten Bezeichner in der Ausgabedatei suchen.

Im folgenden Beispiel wird C2011 generiert und eine Möglichkeit gezeigt, wie Sie diesen Fehler beheben:

```
// C2011.cpp
// compile with: /c
struct S;
union S;   // C2011
union S2;   // OK
```