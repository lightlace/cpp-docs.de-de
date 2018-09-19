---
title: Ausdrucksauswertungsfehler CXX0017 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0017
dev_langs:
- C++
helpviewer_keywords:
- CAN0017
- CXX0017
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 431071137fb3f5b1b276327ee7d21f323ac24c5b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136236"
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