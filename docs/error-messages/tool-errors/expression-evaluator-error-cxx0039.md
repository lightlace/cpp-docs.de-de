---
title: Ausdrucksauswertungsfehler CXX0039
ms.date: 11/04/2016
f1_keywords:
- CXX0039
helpviewer_keywords:
- CXX0039
- CAN0039
ms.assetid: 8bf698d2-e015-4595-944f-72b81aa43d22
ms.openlocfilehash: 053e57a21f0cb75cbd96732edb6812b3557bcd50
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463270"
---
# <a name="expression-evaluator-error-cxx0039"></a>Ausdrucksauswertungsfehler CXX0039

Symbol ist nicht eindeutig

Die C++-ausdrucksauswertung kann nicht welche Instanz eines Symbols für die Verwendung in einem Ausdruck bestimmt werden. Das Symbol tritt mehr als einmal in der Vererbungsstruktur.

Sie müssen den Bereichsauflösungsoperator verwenden (`::`) explizit angeben, die Instanz, die im Ausdruck verwendet.

Dieser Fehler ist mit CAN0039 identisch.