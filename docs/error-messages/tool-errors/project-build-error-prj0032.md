---
title: Projektbuildfehler PRJ0032
ms.date: 11/04/2016
f1_keywords:
- PRJ0032
helpviewer_keywords:
- PRJ0032
ms.assetid: bc6acbea-4041-4237-8b5a-f0434705d89f
ms.openlocfilehash: f1f292f3979c993a8fa8cb8ff44653ac7124b121
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499835"
---
# <a name="project-build-error-prj0032"></a>Projektbuildfehler PRJ0032

Die 'Outputs'-Eigenschaft für den benutzerdefinierten Buildschritt auf Projektebene enthalten "Makros", die als "Macro_expansion" ausgewertet wird.

Ein benutzerdefinierten Buildschritt an einem Projekt musste ungültige Ausgabe wahrscheinlich aufgrund eines Problems der Makro-Evaluierung. Dass der Pfad enthält Zeichen oder eine Kombination von Zeichen, die in einem Dateipfad unzulässig sind falsch formatiert wurde, wird von dieser Fehler auch bedeuten.

Um diesen Fehler zu beheben, korrigieren Sie das Makro oder die Pfadangabe. Der ausgewertete Pfad ist ein absoluter Pfad vom Projektverzeichnis.