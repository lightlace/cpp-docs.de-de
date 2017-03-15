---
title: "Linkertoolfehler LNK1164 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1164"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1164"
ms.assetid: da89765c-affa-4f88-b170-6d6b19a577cf
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Linkertoolfehler LNK1164
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ausrichtung von Abschnitt 'Abschnitt' \(Zahl\) ist größer als \/ALIGN\-Wert  
  
 Die Ausrichtungsgröße für den in der Objektdatei angegebenen Abschnitt überschreitet den mit der [\/ALIGN](../../build/reference/align-section-alignment.md)\-Option angegebenen Wert.  Der **\/ALIGN**\-Wert muss eine Potenz von 2 sein und mit der Abschnittsausrichtung in der Objektdatei übereinstimmen oder sie überschreiten.  
  
 Kompilieren Sie entweder mit einer kleineren Abschnittsausrichtung neu, oder erhöhen Sie den **\/ALIGN**\-Wert.