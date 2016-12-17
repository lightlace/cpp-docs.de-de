---
title: "NMAKE: Warnung U4010"
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
  - "U4010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U4010"
ms.assetid: 99d8eb9a-ae31-40d1-b8c5-8c66732127d3
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE: Warnung U4010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Ziel" konnte nicht erstellt werden; Vorgang wird fortgesetzt, da \/K angegeben  
  
 Im Befehlsblock für das angegebene Ziel wurde Exitcode, der nicht 0 \(null\) ist, von einem Befehl zurückgegeben.  Mit der **\/K**\-Option wurde NMAKE angewiesen, nicht betroffene Teile des Erstellungsvorgangs weiterzuverarbeiten und den Exitcode 1 auszugeben, sobald die NMAKE\-Sitzung abgeschlossen ist.  
  
 Falls das angegebene Ziel selbst eine abhängige Datei für ein anderes Ziel darstellt, gibt NMAKE nach dieser Warnung die Warnung [U4011](../../error-messages/tool-errors/nmake-warning-u4011.md) aus.