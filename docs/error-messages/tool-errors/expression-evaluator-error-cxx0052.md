---
title: Ausdrucksauswertungsfehler CXX0052
ms.date: 11/04/2016
f1_keywords:
- CXX0052
helpviewer_keywords:
- CXX0052
- CAN0052
ms.assetid: 5060d479-d0a4-4682-b858-c8b9a4f324e6
ms.openlocfilehash: 12b4aff2c07e81a77b1a822fa15beb972a7e1e05
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299581"
---
# <a name="expression-evaluator-error-cxx0052"></a>Ausdrucksauswertungsfehler CXX0052

die Memberfunktion ist nicht vorhanden

Eine Member-Funktion wurde als Haltepunkt angegeben, aber es wurde nicht gefunden. Festlegen eines Haltepunkts an eine Funktion, die Inline ersetzt wurde, kann diesen Fehler verursachen.

Kompilieren Sie die Datei mit inlining erzwungen wird, deaktiviert (/ Ob0) in dieser Funktion einen Haltepunkt festlegen.

Ein Ausdruck, der eine Funktion, die nicht definiert war aufgerufen wird.

Dieser Fehler ist mit CAN0052 identisch.