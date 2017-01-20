---
title: "NMAKE: Warnung U4004"
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
  - "U4004"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U4004"
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE: Warnung U4004
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zu viele Regeln für Ziel "Zielname"  
  
 Es wurde mehr als ein Beschreibungsblock für das angegebene Ziel mit dem Doppelpunkt \(**:**\) als Trennzeichen angegeben.  Die Befehle im ersten Beschreibungsblock wurden von NMAKE ausgeführt und weitere Blöcke ignoriert.  
  
 Um dasselbe Ziel in mehrfachen Abhängigkeiten anzugeben, werden zwei Doppelpunkte \(`::`\) als Trennzeichen in jeder Abhängigkeitszeile verwendet.