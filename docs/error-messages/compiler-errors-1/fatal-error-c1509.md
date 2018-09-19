---
title: Schwerwiegender Fehler C1509 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1509
dev_langs:
- C++
helpviewer_keywords:
- C1509
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 837ab5b7cf76b724726c6c52fbfe974d4da6ca85
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033133"
---
# <a name="fatal-error-c1509"></a>Schwerwiegender Fehler C1509

Compilerlimit: zu viele Handler für Ausnahmezustände in der Funktion 'Funktion'. Vereinfachen Sie die Funktion

Der Code überschreitet ein internes Limit für den Handler für Ausnahmezustände (32.768 Staaten).

Die häufigste Ursache ist, dass die Funktion der benutzerdefinierten Klassenvariablen und arithmetische Operatoren einen komplexen Ausdruck enthält.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)

1. Vereinfachen Sie Ausdrücken, indem temporäre Variablen allgemeine Unterausdrücke zuordnen.

1. Teilen Sie die Funktion in kleinere Funktionen.