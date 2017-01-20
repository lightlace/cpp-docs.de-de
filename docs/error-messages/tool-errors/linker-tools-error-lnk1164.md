---
title: "Linkertoolfehler LNK1164"
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
  - "LNK1164"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1164"
ms.assetid: da89765c-affa-4f88-b170-6d6b19a577cf
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK1164
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ausrichtung von Abschnitt 'Abschnitt' \(Zahl\) ist größer als \/ALIGN\-Wert  
  
 Die Ausrichtungsgröße für den in der Objektdatei angegebenen Abschnitt überschreitet den mit der [\/ALIGN](../../build/reference/align-section-alignment.md)\-Option angegebenen Wert.  Der **\/ALIGN**\-Wert muss eine Potenz von 2 sein und mit der Abschnittsausrichtung in der Objektdatei übereinstimmen oder sie überschreiten.  
  
 Kompilieren Sie entweder mit einer kleineren Abschnittsausrichtung neu, oder erhöhen Sie den **\/ALIGN**\-Wert.