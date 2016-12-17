---
title: "BSCMAKE-Fehler BK1513"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "BK1513"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1513"
ms.assetid: 9ba87c09-8d82-4c80-b0cf-a8de63dcf9da
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# BSCMAKE-Fehler BK1513
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

nicht inkrementelle Aktualisierung erfordert alle.SBR\-Dateien  
  
 BSCMAKE kann keine neue Browserinformationsdatei \(.bsc\) erstellen, weil eine oder mehrere .sbr\-Dateien abgeschnitten werden.  Um die Namen der verkürzten .sbr\-Dateien zu finden, lesen Sie die [BK4502](../../error-messages/tool-errors/bscmake-warning-bk4502.md)\-Warnungen, die mit diesem Fehler einhergehen.  
  
 BSCMAKE kann eine .bsc\-Datei mit einer verkürzten .sbr\-Datei aktualisieren, aber eine neue kann nicht erstellt werden.  BSCMAKE kann eine neue .bsc\-Datei aus den folgenden Gründen erstellen:  
  
-   Fehlende .bsc\-Datei.  
  
-   Falscher Dateiname für .bsc\-Datei angegeben.  
  
-   Beschädigte .bsc\-Datei.  
  
 Um dieses Problem zu beheben, löschen Sie die verkürzten .sbr\-Dateien und erstellen sie neu oder löschen Sie die Lösung und erstellen sie neu.  \(Wählen Sie in der IDE **Erstellen**, um die **Projektmappe zu bereinigen** und wählen Sie dann **Erstellen** und dann **Projektmappe neu erstellen**.\)