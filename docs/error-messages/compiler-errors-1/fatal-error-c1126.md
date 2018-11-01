---
title: Schwerwiegender Fehler C1126
ms.date: 11/04/2016
f1_keywords:
- C1126
helpviewer_keywords:
- C1126
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
ms.openlocfilehash: 3f4d152163d3b21ddf99644c34e63f35ca15e6e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50457774"
---
# <a name="fatal-error-c1126"></a>Schwerwiegender Fehler C1126

'Bezeichner': automatische speicherbelegung überschreitet die Größe

Speicherplatz für lokale Variablen von einer Funktion (plus eine begrenzte Menge an Speicherplatz, die durch den Compiler an, wie z. B. 20 Bytes für austauschbare Funktionen zusätzlich verwendet) überschreitet den Grenzwert.

Verwenden Sie zum Beheben dieses Fehlers `malloc` oder `new` zuweisen große Datenmengen.