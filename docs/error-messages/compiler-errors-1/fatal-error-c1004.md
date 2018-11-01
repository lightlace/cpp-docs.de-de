---
title: Schwerwiegender Fehler C1004
ms.date: 11/04/2016
f1_keywords:
- C1004
helpviewer_keywords:
- C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
ms.openlocfilehash: 13fb8963b33569facf62ccedfe9ce8b7bbbbfdc3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428118"
---
# <a name="fatal-error-c1004"></a>Schwerwiegender Fehler C1004

Unerwartetes Dateiende gefunden.

Der Compiler hat das Ende einer Quelldatei erreicht, ohne ein Konstrukt aufzulösen. Der Code möglicherweise eines der folgenden Elemente ist nicht vorhanden:

- Eine schließende geschweifte Klammer

- Eine schließende Klammer

- Ein schließendes Kommentarzeichen (* /)

- Ein Semikolon

Um diesen Fehler zu beheben, überprüfen Sie Folgendes:

- Das Standard-Laufwerk hat nicht genügend Speicherplatz für temporäre Dateien, die über doppelt so viel Speicherplatz wie die Quelldatei erforderlich sind.

- Ein `#if` Richtlinie, der ergibt "false" fehlt ein schließendes `#endif` Richtlinie.

- Eine Quelldatei endet nicht mit einem Wagenrücklauf und Zeilenvorschub.

Im folgende Beispiel wird die C1004 generiert:

```
// C1004.cpp
#if TEST
int main() {}
// C1004
```

Mögliche Lösung:

```
// C1004b.cpp
#if TEST
#endif

int main() {}
```