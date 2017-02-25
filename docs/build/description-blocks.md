---
title: "Beschreibungsbl&#246;cke | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Blöcke, Beschreibung"
  - "Beschreibungsblöcke"
  - "NMAKE (Programm), Beschreibungsblöcke"
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Beschreibungsbl&#246;cke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Beschreibungsblock ist eine Abhängigkeitszeile, die sich optional vor einem Befehlsblock befinden kann:  
  
```  
targets... : dependents...  
    commands...  
```  
  
 Eine Abhängigkeitszeile gibt mindestens ein Ziel und bei Bedarf abhängige Dateien an.  Ein Ziel muss sich am Anfang der Zeile befinden.  Ziele von abhängigen Dateien werden durch einen Doppelpunkt \(**:**\) getrennt. Leerzeichen oder Tabstopps sind zulässig.  Zeilen werden nach einem Ziel oder einer abhängigen Datei durch umgekehrte Schrägstriche \(\\\) getrennt.  Wenn ein Ziel nicht vorhanden ist oder einen früheren Timestamp als eine abhängige Datei besitzt bzw. wenn es sich um ein [Pseudoziel](../build/pseudotargets.md) handelt, werden die Befehle von NMAKE ausgeführt.  Wenn eine abhängige Datei an einem anderen Ort ein Ziel darstellt und nicht vorhanden ist bzw. in Bezug auf eigene abhängige Dateien nicht mehr aktuell ist, wird die abhängige Datei von NMAKE aktualisiert, bevor die momentane Abhängigkeit aktualisiert wird.  
  
## Worüber möchten Sie mehr erfahren?  
 [Ziele](../build/targets.md)  
  
 [Abhängige Dateien](../build/dependents.md)  
  
## Siehe auch  
 [NMAKE\-Referenz](../build/nmake-reference.md)