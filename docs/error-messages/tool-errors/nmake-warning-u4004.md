---
title: "NMAKE: Warnung U4004 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U4004"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U4004"
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# NMAKE: Warnung U4004
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zu viele Regeln für Ziel "Zielname"  
  
 Es wurde mehr als ein Beschreibungsblock für das angegebene Ziel mit dem Doppelpunkt \(**:**\) als Trennzeichen angegeben.  Die Befehle im ersten Beschreibungsblock wurden von NMAKE ausgeführt und weitere Blöcke ignoriert.  
  
 Um dasselbe Ziel in mehrfachen Abhängigkeiten anzugeben, werden zwei Doppelpunkte \(`::`\) als Trennzeichen in jeder Abhängigkeitszeile verwendet.