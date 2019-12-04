---
title: Schwerwiegender Fehler C1017
ms.date: 11/04/2016
f1_keywords:
- C1017
helpviewer_keywords:
- C1017
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
ms.openlocfilehash: 0feda3bc4c3729d3101be356220aa0124ba85190
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756941"
---
# <a name="fatal-error-c1017"></a>Schwerwiegender Fehler C1017

Ungültiger Ausdruck für Ganzzahlkonstante

Der Ausdruck in einer `#if` Direktive ist nicht vorhanden oder wurde nicht zu einer Konstanten ausgewertet.

Mit `#define` definierte Konstanten müssen Werte aufweisen, die zu einer ganzzahligen Konstante ausgewertet werden, wenn Sie in einer `#if`-, `#elif`-oder `#else`-Direktive verwendet werden.

Im folgenden Beispiel wird C1017 generiert:

```cpp
// C1017.cpp
#define CONSTANT_NAME "YES"
#if CONSTANT_NAME   // C1017
#endif
```

Mögliche Lösung:

```cpp
// C1017b.cpp
// compile with: /c
#define CONSTANT_NAME 1
#if CONSTANT_NAME
#endif
```

Da `CONSTANT_NAME` zu einer Zeichenfolge und nicht zu einer ganzen Zahl ausgewertet wird, generiert die `#if` Direktive einen schwerwiegenden Fehler C1017.

In anderen Fällen wertet der Präprozessor eine nicht definierte Konstante als 0 (null) aus. Dies kann zu unbeabsichtigten Ergebnissen führen, wie im folgenden Beispiel gezeigt. `YES` ist nicht definiert, daher ergibt es NULL. Der Ausdruck `#if` `CONSTANT_NAME` als false ausgewertet wird, und der Code, der für `YES` verwendet werden soll, wird vom Präprozessor entfernt. `NO` ist ebenfalls nicht definiert (null), sodass `#elif` `CONSTANT_NAME==NO` als true ausgewertet wird (`0 == 0`), sodass der Präprozessor den Code im `#elif` Teil der Anweisung verlässt – genau das Gegenteil des beabsichtigten Verhaltens.

```cpp
// C1017c.cpp
// compile with: /c
#define CONSTANT_NAME YES
#if CONSTANT_NAME
   // Code to use on YES...
#elif CONSTANT_NAME==NO
   // Code to use on NO...
#endif
```

Verwenden Sie [/P](../../build/reference/p-preprocess-to-a-file.md), [/E](../../build/reference/e-preprocess-to-stdout.md)oder [/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md), um genau zu sehen, wie der Compiler Präprozessordirektiven behandelt.
