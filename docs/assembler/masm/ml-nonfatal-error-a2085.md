---
title: "ML Nonfatal Error A2085"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "A2085"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2085"
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# ML Nonfatal Error A2085
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**akzeptiert keine Register Anweisung oder in CPU\-Modus aktuellen**  
  
 Es wurde versucht, eine Anweisung, ein Register oder ein Schlüsselwort zu verwenden, das für den aktuellen Modus des Prozessors ungültig war.  
  
 Zum Beispiel erfordern 32\-Bit\-Register oben oder [.386](../../assembler/masm/dot-386.md) .  CR0 Steuerelement registriert wie oben oder [.386P](../../assembler/masm/dot-386p.md) privilegierten Modus erfordern.  Dieser Fehler wird auch für die **NEAR32**, **FAR32**und **FLAT** Schlüsselwörter generiert, die erfordern.**386** oder oben.  
  
## Siehe auch  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)