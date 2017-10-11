---
title: Abstand und Ausrichtung von Strukturmembern | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- structure members, padding and alignment
ms.assetid: c999820b-dd47-41fc-b923-e4c7ebbcd30f
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 6c3a87f1277abb9d5cf3b9d87c6713104ba8e108
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="padding-and-alignment-of-structure-members"></a>Abstand und Ausrichtung von Strukturmembern
**ANSI 3.5.2.1** Der Abstand und die Ausrichtung von Strukturmembern und die Angabe, ob ein Bitfeld eine Speichereinheitsgrenze umspannen kann  
  
 Strukturmember werden nacheinander in der Reihenfolge gespeichert, in der sie deklariert werden: das erste Member hat die niedrigste Speicheradresse und das letzte Member die höchste.  
  
 Jedes Datenobjekt verfügt über ein alignment-requirement. Das alignment-requirement für alle Daten (außer Strukturen, Unions und Arrays) ist entweder die Größe des Objekts oder die aktuelle Komprimierungsgröße (diese wird entweder mit "/Zp" oder dem `pack`-Pragma angegeben, je nachdem, was kleiner ist). Bei Strukturen, Unions und Arrays ist das alignment-requirement die größte Ausrichtungsanforderung ihrer Member. Jedem Objekt wird ein offset zugeordnet, sodass Folgendes gilt:  
  
 *offset*  `%` *alignment-requirement* `==` 0  
  
 Benachbarte Bitfelder sind in derselben 1-, 2- oder 4-Byte-Speicherbelegungseinheit gepackt, wenn die Ganzzahltypen die gleiche Größe aufweisen und das folgende Bitfeld in die aktuelle Speicherbelegungseinheit passt, ohne die Grenze zu überschreiten, die durch die allgemeinen Ausrichtungsanforderungen der Bitfelder auferlegt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Unions, Enumerationen und Bitfelder](../c-language/structures-unions-enumerations-and-bit-fields.md)
