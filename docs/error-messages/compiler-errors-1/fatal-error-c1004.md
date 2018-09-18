---
title: Schwerwiegender Fehler C1004 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1004
dev_langs:
- C++
helpviewer_keywords:
- C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a284de510fde49602a06fb9282c0ddd59eeb0ac1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020279"
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