---
title: Ausdrucksauswertungsfehler CXX0015 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0015
dev_langs:
- C++
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1aa37a2cc7208063ce4cfa786de196842ab42b45
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050815"
---
# <a name="expression-evaluator-error-cxx0015"></a>Ausdrucksauswertungsfehler CXX0015

Ausdruck zu komplex (Stapelüberlauf)

Der eingegebene Ausdruck war zu komplex oder geschachtelte zu tief für die Menge an Speicherplatz für die C++-ausdrucksauswertung.

Überlauf tritt auf, in der Regel, da zu viele ausstehende Berechnungen.

Ordnen Sie den Ausdruck so, dass jede Komponente des Ausdrucks ausgewertet werden kann, wenn es gefunden wird, anstatt zu warten, bis andere Teile des Ausdrucks berechnet werden soll.

Unterbrechen Sie mehrere Befehle mit den Ausdruck.

Dieser Fehler ist mit CAN0015 identisch.