---
title: "Abstand und Ausrichtung von Strukturmembern"
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
  - "Strukturmember, Abstand und Ausrichtung"
ms.assetid: c999820b-dd47-41fc-b923-e4c7ebbcd30f
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Abstand und Ausrichtung von Strukturmembern
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.5.2.1** Der Abstand und die Ausrichtung von Strukturmembern und die Angabe, ob ein Bitfeld eine Speichereinheitsgrenze umspannen kann  
  
 Strukturmember werden nacheinander in der Reihenfolge gespeichert, in der sie deklariert werden: das erste Member hat die niedrigste Speicheradresse und das letzte Member die höchste.  
  
 Jedes Datenobjekt verfügt über ein alignment\-requirement.  Das alignment\-requirement für alle Daten \(außer Strukturen, Unions und Arrays\) ist entweder die Größe des Objekts oder die aktuelle Komprimierungsgröße \(diese wird entweder mit "\/Zp" oder dem `pack`\-Pragma angegeben, je nachdem, was kleiner ist\).  Bei Strukturen, Unions und Arrays ist das alignment\-requirement die größte Ausrichtungsanforderung ihrer Member.  Jedem Objekt wird ein offset zugeordnet, sodass Folgendes gilt:  
  
 *offset*  `%` *alignment\-requirement* `==` 0  
  
 Benachbarte Bitfelder sind in derselben 1\-, 2\- oder 4\-Byte\-Speicherbelegungseinheit gepackt, wenn die Ganzzahltypen die gleiche Größe aufweisen und das folgende Bitfeld in die aktuelle Speicherbelegungseinheit passt, ohne die Grenze zu überschreiten, die durch die allgemeinen Ausrichtungsanforderungen der Bitfelder auferlegt werden.  
  
## Siehe auch  
 [Strukturen, Unions, Enumerationen und Bitfelder](../c-language/structures-unions-enumerations-and-bit-fields.md)