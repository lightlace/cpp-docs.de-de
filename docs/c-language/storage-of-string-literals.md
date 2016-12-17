---
title: "Speicherung von Zeichenfolgenliteralen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Zeichenfolgenliterale, Speicher"
ms.assetid: ba5e4d2c-d456-44b3-a8ca-354af547ac50
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Speicherung von Zeichenfolgenliteralen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Zeichen einer Literalzeichenfolge werden in Reihenfolge an zusammenhängenden Speicherorten gespeichert.  Eine Escapesequenz \(wie z. B. **\\\\** oder **\\"**\) innerhalb eines Zeichenfolgenliterals zählt als einzelnes Zeichen.  Ein NULL\-Zeichen \(dargestellt durch die Escapesequenz **\\0**\) wird automatisch angefügt und markiert das Ende eines Zeichenfolgenliterals. \(Dies tritt während [Übersetzungsphase](../preprocessor/phases-of-translation.md) 7\) auf. Beachten Sie, dass der Compiler zwei identische Zeichenfolgen nicht an zwei verschiedenen Adressen speichert.  [\/GF](../build/reference/gf-eliminate-duplicate-strings.md) erzwingt, dass der Compiler eine einzige Kopie von identischen Zeichenfolgen in die ausführbare Datei einfügt.  
  
## Hinweise  
 **Microsoft\-spezifisch**  
  
 Zeichenfolgen haben eine statische Speicherdauer.  Weitere Informationen über die Speicherdauer finden Sie unter [Speicherklassen](../c-language/c-storage-classes.md).  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [C\-Zeichenfolgenliterale](../c-language/c-string-literals.md)