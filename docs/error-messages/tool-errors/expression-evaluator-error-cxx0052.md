---
title: Ausdrucksauswertungsfehler CXX0052 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0052
dev_langs:
- C++
helpviewer_keywords:
- CXX0052
- CAN0052
ms.assetid: 5060d479-d0a4-4682-b858-c8b9a4f324e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ba8fb898930ef830857773a89cd80e4c43c59c4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028154"
---
# <a name="expression-evaluator-error-cxx0052"></a>Ausdrucksauswertungsfehler CXX0052

die Memberfunktion ist nicht vorhanden

Eine Member-Funktion wurde als Haltepunkt angegeben, aber es wurde nicht gefunden. Festlegen eines Haltepunkts an eine Funktion, die Inline ersetzt wurde, kann diesen Fehler verursachen.

Kompilieren Sie die Datei mit inlining erzwungen wird, deaktiviert (/ Ob0) in dieser Funktion einen Haltepunkt festlegen.

Ein Ausdruck, der eine Funktion, die nicht definiert war aufgerufen wird.

Dieser Fehler ist mit CAN0052 identisch.