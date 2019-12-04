---
title: Schwerwiegender Fehler C1004
ms.date: 11/04/2016
f1_keywords:
- C1004
helpviewer_keywords:
- C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
ms.openlocfilehash: 82a1a3e410505be53d4356e46d5521aebb72763c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756967"
---
# <a name="fatal-error-c1004"></a>Schwerwiegender Fehler C1004

Unerwartetes Dateiende gefunden.

Der Compiler hat das Ende einer Quelldatei erreicht, ohne ein Konstrukt aufzulösen. Im Code fehlt möglicherweise eines der folgenden Elemente:

- Eine schließende geschweifte Klammer

- Eine schließende Klammer

- Ein Schließ ender Kommentar Marker (*/)

- Ein Semikolon

Um diesen Fehler zu beheben, überprüfen Sie Folgendes:

- Das Standard Datenträger verfügt nicht über genügend Speicherplatz für temporäre Dateien, die ungefähr doppelt so viel Speicherplatz wie die Quelldatei erfordern.

- Bei einer `#if`-Anweisung, die zu false ausgewertet wird, fehlt eine schließende `#endif` Direktive

- Eine Quelldatei endet nicht mit einem Wagen Rücklauf-und Zeilenvorschub.

Im folgenden Beispiel wird C1004 generiert:

```cpp
// C1004.cpp
#if TEST
int main() {}
// C1004
```

Mögliche Lösung:

```cpp
// C1004b.cpp
#if TEST
#endif

int main() {}
```
