---
title: "LIB-Ausgabedateien | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Lib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ausgabedateien, LIB"
ms.assetid: e73d2f9b-a42d-402b-b7e3-3a94bebb317e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# LIB-Ausgabedateien
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die von LIB erstellten Ausgabedateien hängen von dem Modus ab, in dem das Programm verwendet wird \(siehe nachfolgende Tabelle\).  
  
|Modus|Ausgabe|  
|-----------|-------------|  
|Standard \(Erstellen oder Ändern einer Bibliothek\)|COFF\-Bibliothek \(**.lib**\)|  
|Extrahieren eines Members mit **\/EXTRACT**|Objektdatei \(**.obj**\)|  
|Erstellen einer Exportdatei und Importbibliothek mit **\/DEF**|Importbibliothek \(**.lib**\) und Exportdatei \(**.exp**\)|  
  
## Siehe auch  
 [Übersicht über LIB](../../build/reference/overview-of-lib.md)