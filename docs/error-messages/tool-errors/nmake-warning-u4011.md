---
title: "NMAKE: Warnung U4011 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U4011"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U4011"
ms.assetid: e8244514-eba6-4285-8853-7baeefdcd8a4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# NMAKE: Warnung U4011
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Ziel": nicht alle abhängigen Elemente verfügbar; Ziel nicht erstellt  
  
 Ein abhängiges Element des angegebenen Zieles ist entweder nicht vorhanden oder war nicht mehr aktuell, und ein Befehl zur Aktualisierung der abhängigen Elemente gab einen Exitcode, der nicht null ist, zurück.  Mit der **\/K**\-Option wurde NMAKE angewiesen, nicht betroffene Teile des Erstellungsvorgangs weiterzuverarbeiten und den Exitcode 1 auszugeben, sobald die NMAKE\-Sitzung abgeschlossen ist.  
  
 Dieser Warnung geht die Warnung [U4010](../../error-messages/tool-errors/nmake-warning-u4010.md) für jedes abhängige Element voraus, das nicht erstellt oder aktualisiert werden konnte.