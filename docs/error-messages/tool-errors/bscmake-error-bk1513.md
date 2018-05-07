---
title: BSCMAKE-Fehler BK1513 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1513
dev_langs:
- C++
helpviewer_keywords:
- BK1513
ms.assetid: 9ba87c09-8d82-4c80-b0cf-a8de63dcf9da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 93664a1224b85ec808805da0172aec408e875bc9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="bscmake-error-bk1513"></a>BSCMAKE-Fehler BK1513
nicht inkrementelle Aktualisierung erfordert alle.SBR-Dateien  
  
 BSCMAKE kann keine neue Browserinformationsdatei (.bsc) erstellen, weil eine oder mehrere .sbr-Dateien abgeschnitten werden. Um die Namen der verkürzten .sbr-Dateien zu suchen, lesen Sie die [BK4502](../../error-messages/tool-errors/bscmake-warning-bk4502.md) Warnungen, die diesem Fehler auftreten.  
  
 BSCMAKE kann eine .bsc-Datei mit einer verkürzten .sbr-Datei aktualisieren, aber eine neue kann nicht erstellt werden. BSCMAKE kann eine neue .bsc-Datei aus den folgenden Gründen erstellen:  
  
-   Fehlende .bsc-Datei.  
  
-   Falscher Dateiname für .bsc-Datei angegeben.  
  
-   Beschädigte .bsc-Datei.  
  
 Um dieses Problem zu beheben, löschen Sie die verkürzten .sbr-Dateien und erstellen sie neu oder löschen Sie die Lösung und erstellen sie neu. (Wählen Sie in der IDE **erstellen**, **Projektmappe bereinigen**, und wählen Sie dann **erstellen**, **Projektmappe neu erstellen**.)