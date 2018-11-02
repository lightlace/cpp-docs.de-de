---
title: Ausdrucksauswertungsfehler CXX0017
ms.date: 11/04/2016
f1_keywords:
- CXX0017
helpviewer_keywords:
- CAN0017
- CXX0017
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
ms.openlocfilehash: bbf16ae9a503a8525edb42d6bf1fc4336c3f5267
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602529"
---
# <a name="expression-evaluator-error-cxx0017"></a>Ausdrucksauswertungsfehler CXX0017

Symbol konnte nicht gefunden.

Ein Symbol angegeben, die in einem Ausdruck konnte nicht gefunden werden.

Eine mögliche Ursache dieses Fehlers ist der Symbolname Groß-/Kleinschreibung übereinstimmen. Da C und C++ Groß-/Kleinschreibung, muss ein Symbolnamen in die genaue Groß-/Kleinschreibung eingegeben werden, in der sie in der Quelle definiert ist.

Dieser Fehler kann auftreten, wenn eine Variablen umwandeln, um die Variable während des Debuggens überwachen möchten. Die `typedef` ein neuer Name für einen Typ, deklariert jedoch einen neuen Typ nicht definiert. Der Debugger versuchte Typumwandlung ist der Name des definierten Typs erforderlich.

Dieser Fehler ist mit CAN0017 identisch.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)

1. Stellen Sie sicher, dass das Symbol bereits an dem Punkt im Programm deklariert wird, in dem sie verwendet wird.

1. Verwenden Sie einen tatsächlicher Typname umzuwandelnde Variablen im Debugger, anstelle eines `typedef`-Namen definiert.