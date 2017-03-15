---
title: "NMAKE: Schwerwiegender Fehler U1056 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1056"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1056"
ms.assetid: da855728-b69e-413c-83ed-df912126215e
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# NMAKE: Schwerwiegender Fehler U1056
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Befehlsprozessor nicht gefunden  
  
 Der Befehlsprozessor befand sich nicht in dem Pfad, der in der **COMSPEC**\-Umgebungsvariablen oder **PATH**\-Umgebungsvariablen angegeben wurde.  
  
 **COMMAND.COM** oder **CMD.EXE** wird von NMAKE beim Ausführen von Befehlen als Befehlsprozessor verwendet.  Der Befehlsprozessor wird zuerst in dem Pfad gesucht, der in **COMSPEC** festgelegt wurde.  Ist **COMSPEC** nicht vorhanden, erfolgt durch NMAKE eine Suche in den Verzeichnissen, die in **PATH** angegeben wurden.