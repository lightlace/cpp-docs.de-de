---
title: "Verschiebungen nach rechts | Microsoft Docs"
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
ms.assetid: c878e97d-ea3c-4c6b-90a8-b1b24b2d5b19
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Verschiebungen nach rechts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Ergebnis einer Rechtsverschiebung eines Ganzzahltyps mit Vorzeichen mit negativem Wert  
  
 Das Verschieben eines negativen Werts nach rechts ergibt die Hälfte des absoluten Werts \(abgerundet\).  Zum Beispiel ein signierter `short` Wert –253 \(hexadezimal 0xFF03, Binärzahl 11111111 00000011\) ein Bit nach rechts verschoben erzeugt –127 \(hexadezimal 0xFF81, Binärzahl 11111111 10000001\).  Ein positiver nach rechts verschobener Wert 253 erzeugt \+ 126.  
  
 Rechtsverschiebungen behalten das signierte Bit des signierten Ganzzahltyps bei.  Wenn eine ganze Zahl mit Vorzeichen nach rechts verschoben wird, bleibt das wichtigste Byte festgelegt.  Wenn "0xF0000000" beispielsweise ein signierter `int` ist, ergibt eine Rechtsverschiebung den Wert "0xF8000000".  Beim 32\-maligen Verschieben eines negativen Werts `int` wird hierdurch "0xFFFFFFFF" erzeugt.  
  
 Bei der Rechtsverschiebung einer ganzen Zahl ohne Vorzeichen wird das wichtigste Byte gelöscht.  Wenn "0xF000" nicht signiert ist, lautet das Ergebnis "0x7800".  Beim 32\-maligen Verschieben eines Werts `unsigned` oder positiven `int`\-Werts wird hierdurch "0x00000000" erzeugt.  
  
## Siehe auch  
 [Ganze Zahlen](../c-language/integers.md)