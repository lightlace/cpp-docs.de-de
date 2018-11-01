---
title: Projektbuildfehler PRJ0024
ms.date: 08/27/2018
f1_keywords:
- PRJ0024
helpviewer_keywords:
- PRJ0024
ms.assetid: 8bde6368-6c1b-4e04-bc5e-3c6d0b8fa1d7
ms.openlocfilehash: 645b898bdffcc6d7b397c25eb3c41cea25cb361f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50589643"
---
# <a name="project-build-error-prj0024"></a>Projektbuildfehler PRJ0024

> Unicodepfad '*Pfad*' konnte nicht in ANSI-Codepage des Benutzers übersetzt werden.

*Pfad* ist die ursprüngliche Unicode-Version von der Path-Zeichenfolge. Dieser Fehler kann in Fällen auftreten, wenn ein Unicodepfad, der für die aktuelle Codepage des Systems nicht direkt in ANSI übersetzt werden kann nicht vorhanden ist.

Dieser Fehler kann auftreten, wenn Sie arbeiten mit einem Projekt, das entwickelt wurde auf einem System, das Verwenden einer Codepage, die nicht auf Ihrem Computer vorhanden ist.

Die Auflösung für diesen Fehler ist, aktualisieren Sie den Pfad zur Verwendung von ANSI-Text oder um die Codepage auf dem Computer installieren und als dem als Standard festgelegt haben.