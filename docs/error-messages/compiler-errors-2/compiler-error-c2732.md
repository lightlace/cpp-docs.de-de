---
title: Compilerfehler C2732
ms.date: 11/04/2016
f1_keywords:
- C2732
helpviewer_keywords:
- C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
ms.openlocfilehash: 820a620b7e4414123c56433f84536393834f6fd6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50585366"
---
# <a name="compiler-error-c2732"></a>Compilerfehler C2732

Bindungsangaben widersprechen vorheriger Angabe für 'function'

Die Funktion wurde bereits mit einem anderen Bindungsspezifizierer deklariert.

Dieser Fehler kann durch das Einbeziehen von Dateien mit unterschiedlichen Bindungsspezifizierern verursacht werden.

Um diesen Fehler zu beheben, ändern Sie die `extern`-Anweisungen, sodass die Bindungen übereinstimmen. Brechen Sie im Besonderen `#include`-Anweisung nicht in `extern "C"`-Blöcke um.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2732 generiert:

```
// C2732.cpp
extern void func( void );   // implicit C++ linkage
extern "C" void func( void );   // C2732
```