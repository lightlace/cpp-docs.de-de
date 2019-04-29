---
title: Schwerwiegender Fehler C1509
ms.date: 11/04/2016
f1_keywords:
- C1509
helpviewer_keywords:
- C1509
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
ms.openlocfilehash: efd5b9dd5cdd7ee174bc786c38d9dd841e2ad6ce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397483"
---
# <a name="fatal-error-c1509"></a>Schwerwiegender Fehler C1509

Compilerlimit: zu viele Handler für Ausnahmezustände in der Funktion 'Funktion'. Vereinfachen Sie die Funktion

Der Code überschreitet ein internes Limit für den Handler für Ausnahmezustände (32.768 Staaten).

Die häufigste Ursache ist, dass die Funktion der benutzerdefinierten Klassenvariablen und arithmetische Operatoren einen komplexen Ausdruck enthält.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)

1. Vereinfachen Sie Ausdrücken, indem temporäre Variablen allgemeine Unterausdrücke zuordnen.

1. Teilen Sie die Funktion in kleinere Funktionen.