---
title: Projektbuildfehler PRJ0006
ms.date: 11/04/2016
f1_keywords:
- PRJ0006
helpviewer_keywords:
- PRJ0006
ms.assetid: ce092be4-1652-414f-8cb5-b97ef5841f89
ms.openlocfilehash: d62c774411fda80a3e94044b3272567177328ff5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62359656"
---
# <a name="project-build-error-prj0006"></a>Projektbuildfehler PRJ0006

Die temporäre Datei "File" konnte nicht geöffnet werden. Stellen Sie sicher, dass die Datei vorhanden ist und dass das Verzeichnis nicht schreibgeschützt ist.

Visual C++ konnte eine temporäre Datei nicht während des Buildprozesses erstellt werden. Die Gründe hierfür sind:

- Keine temporären Verzeichnis.

- Nur-Lese temp-Verzeichnis.

- Nicht genügend Speicherplatz vorhanden.

- Der Ordner $(IntDir) ist entweder schreibgeschützt oder temporären Dateien enthält, die schreibgeschützt sind.

Dieser Fehler tritt auch folgende Fehler PRJ0007: Das Ausgabeverzeichnis "Verzeichnis" konnte nicht erstellt werden. Fehler-PRJ0007 bedeutet, dass das $(IntDir) Verzeichnis konnte nicht erstellt werden, dass dies die Erstellung von vorübergehend Dateien schlägt auch fehl.

Wenn Sie angeben, werden temporäre Dateien erstellt:

- Eine Antwortdatei.

- Ein benutzerdefinierter Buildschritt.

- Ein Buildereignis.