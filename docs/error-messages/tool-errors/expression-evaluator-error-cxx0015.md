---
title: Ausdrucksauswertungsfehler CXX0015
ms.date: 11/04/2016
f1_keywords:
- CXX0015
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
ms.openlocfilehash: f73aef18563426d28a81b92b3c37d1b7e345d0d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397145"
---
# <a name="expression-evaluator-error-cxx0015"></a>Ausdrucksauswertungsfehler CXX0015

Ausdruck zu komplex (Stapelüberlauf)

Der eingegebene Ausdruck war zu komplex oder geschachtelte zu tief für die Menge an Speicherplatz für die C++-ausdrucksauswertung.

Überlauf tritt auf, in der Regel, da zu viele ausstehende Berechnungen.

Ordnen Sie den Ausdruck so, dass jede Komponente des Ausdrucks ausgewertet werden kann, wenn es gefunden wird, anstatt zu warten, bis andere Teile des Ausdrucks berechnet werden soll.

Unterbrechen Sie mehrere Befehle mit den Ausdruck.

Dieser Fehler ist mit CAN0015 identisch.