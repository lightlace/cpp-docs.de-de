---
title: Projektbuildfehler prj0006 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0006
dev_langs: C++
helpviewer_keywords: PRJ0006
ms.assetid: ce092be4-1652-414f-8cb5-b97ef5841f89
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 817450fb6b72f985d7ff49f7e65f9dfa0933b4d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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