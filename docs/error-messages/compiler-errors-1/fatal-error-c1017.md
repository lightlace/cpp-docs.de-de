---
title: Schwerwiegender Fehler C1017
ms.date: 11/04/2016
f1_keywords:
- C1017
helpviewer_keywords:
- C1017
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
ms.openlocfilehash: e2309b93be65b049c35abf96572e144a0a518007
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614278"
---
# <a name="fatal-error-c1017"></a>Schwerwiegender Fehler C1017

Ungültiger Ausdruck für Ganzzahlkonstante

Der Ausdruck in einem `#if` Direktive ist nicht vorhanden oder wurde nicht auf eine Konstante ausgewertet.

Definiert Konstanten `#define` müssen Werte, der in eine ganzzahlige Konstante ausgewertet werden soll, wenn sie in verwendet werden eine `#if`, `#elif`, oder `#else` Richtlinie.

Im folgende Beispiel wird die C1017 generiert:

```
// C1017.cpp
#define CONSTANT_NAME "YES"
#if CONSTANT_NAME   // C1017
#endif
```

Mögliche Lösung:

```
// C1017b.cpp
// compile with: /c
#define CONSTANT_NAME 1
#if CONSTANT_NAME
#endif
```

Da `CONSTANT_NAME` ergibt eine Zeichenfolge und keine ganze Zahl, die `#if` -Direktive generiert schwerwiegenden Fehler C1017.

In anderen Fällen wertet der Präprozessor eine nicht definierte Konstante als 0 (null). Dies kann zu unerwarteten Ergebnissen führen, wie im folgenden Beispiel gezeigt. `YES` nicht definiert ist, sodass es auf 0 (null) ausgewertet wird. Der Ausdruck `#if` `CONSTANT_NAME` ergibt "false" und den Code zu verwendenden `YES` wird vom Präprozessor entfernt. `NO` ist auch nicht definiert ist (null), also `#elif` `CONSTANT_NAME==NO` auf "true" ausgewertet wird (`0 == 0`), verursacht den Präprozessor an, lassen Sie den Code in die `#elif` Teil der Anweisung – genau das Gegenteil des beabsichtigten Verhaltens.

```
// C1017c.cpp
// compile with: /c
#define CONSTANT_NAME YES
#if CONSTANT_NAME
   // Code to use on YES...
#elif CONSTANT_NAME==NO
   // Code to use on NO...
#endif
```

Verwenden, um anzuzeigen, genau wie der Compiler Präprozessordirektiven behandelt [/p](../../build/reference/p-preprocess-to-a-file.md), [/e](../../build/reference/e-preprocess-to-stdout.md), oder [/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md).