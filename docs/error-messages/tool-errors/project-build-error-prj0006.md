---
title: Projektbuildfehler prj0006 | Microsoft Docs
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
ms.openlocfilehash: 151c22bf13c13de21e89a5c96185cf1c4c1ca349
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-error-prj0006"></a>Projektbuildfehler PRJ0006
Die temporäre Datei "File" konnte nicht geöffnet werden. Stellen Sie sicher, dass die Datei vorhanden ist, dass das Verzeichnis nicht schreibgeschützt ist.  
  
 Visual C++ konnte eine temporäre Datei nicht während des Buildprozesses erstellt werden. Die Gründe hierfür sind:  
  
-   Keine temp-Verzeichnis.  
  
-   Nur-Lese temp-Verzeichnis.  
  
-   Nicht genügend Speicherplatz vorhanden.  
  
-   Der Ordner $(IntDir) ist entweder schreibgeschützt oder enthält temporäre Dateien, die schreibgeschützt sind.  
  
 Dieser Fehler tritt auch folgenden Fehler PRJ0007: Ausgabe "Verzeichnis" konnte nicht erstellt werden. Fehler PRJ0007 bedeutet, dass das $(IntDir) Verzeichnis konnte nicht erstellt werden, die Erstellung von temporären Dateien Gleichzeichen schlägt auch fehl.  
  
 Wenn Sie angeben, werden temporäre Dateien erstellt:  
  
-   Eine Antwortdatei.  
  
-   Einen benutzerdefinierten Buildschritt.  
  
-   Ein Buildereignis.