---
title: Projektbuildfehler prj0006 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0006
dev_langs:
- C++
helpviewer_keywords:
- PRJ0006
ms.assetid: ce092be4-1652-414f-8cb5-b97ef5841f89
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 264b2f90a2d778b1545117ce5c3b1272626ebad6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073251"
---
# <a name="project-build-error-prj0006"></a>Projektbuildfehler PRJ0006

Die temporäre Datei "File" konnte nicht geöffnet werden. Stellen Sie sicher, dass die Datei vorhanden ist und dass das Verzeichnis nicht schreibgeschützt ist.

Visual C++ konnte eine temporäre Datei nicht während des Buildprozesses erstellt werden. Die Gründe hierfür sind:

- Keine temporären Verzeichnis.

- Nur-Lese temp-Verzeichnis.

- Nicht genügend Speicherplatz vorhanden.

- Der Ordner $(IntDir) ist entweder schreibgeschützt oder temporären Dateien enthält, die schreibgeschützt sind.

Dieser Fehler tritt auch folgende Fehler PRJ0007: das Ausgabeverzeichnis "Verzeichnis" konnte nicht erstellt werden. Fehler-PRJ0007 bedeutet, dass das $(IntDir) Verzeichnis konnte nicht erstellt werden, dass dies die Erstellung von vorübergehend Dateien schlägt auch fehl.

Wenn Sie angeben, werden temporäre Dateien erstellt:

- Eine Antwortdatei.

- Ein benutzerdefinierter Buildschritt.

- Ein Buildereignis.