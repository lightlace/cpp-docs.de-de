---
title: Schwerwiegender Fehler C1126 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1126
dev_langs:
- C++
helpviewer_keywords:
- C1126
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f014aafc60a36bfbb4edad50e7e3ceede6e3c8b2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062474"
---
# <a name="fatal-error-c1126"></a>Schwerwiegender Fehler C1126

'Bezeichner': automatische speicherbelegung überschreitet die Größe

Speicherplatz für lokale Variablen von einer Funktion (plus eine begrenzte Menge an Speicherplatz, die durch den Compiler an, wie z. B. 20 Bytes für austauschbare Funktionen zusätzlich verwendet) überschreitet den Grenzwert.

Verwenden Sie zum Beheben dieses Fehlers `malloc` oder `new` zuweisen große Datenmengen.