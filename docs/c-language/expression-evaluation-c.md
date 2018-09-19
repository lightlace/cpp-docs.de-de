---
title: Ausdrucksauswertung (C) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- expression evaluation
- expressions [C++], evaluating
ms.assetid: 9493f8cc-64a2-4284-9aaf-26eec11c4f40
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0f97b28067d6257ea14255d3e049adcae99f73ef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060940"
---
# <a name="expression-evaluation-c"></a>Ausdrucksauswertung (C)

Ausdrücke, die mit Zuweisung, unärem Inkrement bzw. unärem Dekrement zusammenhängen oder eine Funktion aufrufen, können Folgen haben, die mit ihrer Auswertung auftreten (Nebeneffekte). Mit dem Erreichen eines "Sequenzpunkts" wird gewährleistet, dass alles vor dem Sequenzpunkt, einschließlich aller möglichen Nebeneffekte, ausgewertet wurde, bevor die Auswertung von Elementen nach dem Sequenzpunkt fortgesetzt wird.

"Nebeneffekte" sind die Änderungen, die durch die Auswertung eines Ausdrucks verursacht werden. Nebeneffekte treten auf, wenn der Wert einer Variablen durch eine Ausdrucksauswertung geändert wird. Alle Zuweisungsvorgänge haben Nebeneffekte. Funktionsaufrufe können auch Nebeneffekte haben, wenn sie den Wert eines extern sichtbaren Elements entweder durch direkte oder indirekte Zuweisung über einen Zeiger ändern.

## <a name="see-also"></a>Siehe auch

[Operanden und Ausdrücke](../c-language/operands-and-expressions.md)