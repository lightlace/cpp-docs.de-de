---
title: "Maximal zul&#228;ssige Zeichenfolgenl&#228;nge"
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
  - "Längen, Zeichenfolgen"
  - "Maximal zulässige Zeichenfolgenlänge"
  - "Zeichenfolgenlänge, Maximum"
  - "Zeichenfolgen [C++], Länge"
ms.assetid: 99a80e4a-6212-47b7-a6bd-bdf99bd44928
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Maximal zul&#228;ssige Zeichenfolgenl&#228;nge
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 ANSI\-Kompatibilität erfordert, dass einen Compiler nach der Verkettung bis zu 509 Zeichen in einem Zeichenfolgenliteral annimmt.  Die maximale Länge eines in Microsoft C zulässigen Zeichenfolgenliterals ist ca. 2048 Bytes.  Wenn ein Zeichenfolgenliteral jedoch aus Teilen besteht, die in doppelte Anführungszeichen eingeschlossen sind, verkettet der Präprozessor die Teile zu einer einzelnen Zeichenfolge und fügt für jede verkettete Zeile ein zusätzliches Byte zur Gesamtanzahl von Bytes hinzu.  
  
 Angenommen, eine Zeichenfolge besteht aus 40 Zeilen mit 50 Zeichen pro Zeile \(2.000 Zeichen\) und einer Zeile mit 7 Zeichen, und jede Zeile ist in doppelte Anführungszeichen eingeschlossen.  Das ergibt 2.007 Bytes plus ein Byte für das abschließende NULL\-Zeichen, also insgesamt 2.008 Bytes.  Bei der Verkettung wird ein zusätzliches Zeichen für jede der ersten 40 Zeilen hinzugefügt.  Dies ergibt eine Gesamtmenge von 2.048 Bytes.  Beachten Sie jedoch, dass der Präprozessor kein zusätzliches Zeichen für jede Zeile hinzufügt, wenn Zeilenfortsetzungen \(\\\) anstelle von doppelten Anführungszeichen verwendet werden.  
  
 Während eine einzelne Zeichenfolge in Anführungszeichen nicht länger als 2048 Byte sein darf, kann durch Zeichenfolgenverkettung ein Zeichenfolgenliteral von ca. 65535 Bytes erstellt werden.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [C\-Zeichenfolgenliterale](../c-language/c-string-literals.md)