---
title: Ausdrucksauswertungsfehler CXX0030
ms.date: 11/04/2016
f1_keywords:
- CXX0030
helpviewer_keywords:
- CAN0030
- CXX0030
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
ms.openlocfilehash: 1e52b238905fba5c310a89377b81548a1c6b5784
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500346"
---
# <a name="expression-evaluator-error-cxx0030"></a>Ausdrucksauswertungsfehler CXX0030

Ausdruck kann nicht ausgewertet werden

Ausdrucksauswertung des Debuggers konnte einen Wert für den Ausdruck nicht abrufen, laut. Eine wahrscheinliche Ursache ist, dass der Ausdruck in den Speicher verweist, die außerhalb des Programms-Adressraum ist (einen null-Zeiger zu dereferenzieren, ist ein Beispiel). Windows lässt sich nicht auf den Zugriff auf den Speicher aus, die außerhalb des Programms Adressraum ist.

Möglicherweise möchten den Ausdruck, der die Verwendung von Klammern zur Steuerung der Reihenfolge der Auswertung zu schreiben.

Dieser Fehler ist mit CAN0030 identisch.