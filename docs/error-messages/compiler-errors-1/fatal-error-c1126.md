---
title: Schwerwiegender Fehler C1126
ms.date: 11/04/2016
f1_keywords:
- C1126
helpviewer_keywords:
- C1126
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
ms.openlocfilehash: 3f4d152163d3b21ddf99644c34e63f35ca15e6e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230011"
---
# <a name="fatal-error-c1126"></a>Schwerwiegender Fehler C1126

'Bezeichner': automatische speicherbelegung überschreitet die Größe

Speicherplatz für lokale Variablen von einer Funktion (plus eine begrenzte Menge an Speicherplatz, die durch den Compiler an, wie z. B. 20 Bytes für austauschbare Funktionen zusätzlich verwendet) überschreitet den Grenzwert.

Verwenden Sie zum Beheben dieses Fehlers `malloc` oder `new` zuweisen große Datenmengen.