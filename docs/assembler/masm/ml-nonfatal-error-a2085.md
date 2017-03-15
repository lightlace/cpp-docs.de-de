---
title: "ML Nonfatal Error A2085 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2085"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2085"
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Nonfatal Error A2085
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**akzeptiert keine Register Anweisung oder in CPU\-Modus aktuellen**  
  
 Es wurde versucht, eine Anweisung, ein Register oder ein Schlüsselwort zu verwenden, das für den aktuellen Modus des Prozessors ungültig war.  
  
 Zum Beispiel erfordern 32\-Bit\-Register oben oder [.386](../../assembler/masm/dot-386.md) .  CR0 Steuerelement registriert wie oben oder [.386P](../../assembler/masm/dot-386p.md) privilegierten Modus erfordern.  Dieser Fehler wird auch für die **NEAR32**, **FAR32**und **FLAT** Schlüsselwörter generiert, die erfordern.**386** oder oben.  
  
## Siehe auch  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)