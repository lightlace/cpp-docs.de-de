---
title: Speicherung und Ausrichtung von Strukturen | Microsoft-Dokumentation
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
- alignment of structures
- structure storage
- storing structures
- packing structures
ms.assetid: 60ff292f-2595-4f37-ae00-4c4b4f047196
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0cb5ec55ed3125ac86b0042812ba7fc25388a155
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="storage-and-alignment-of-structures"></a>Speicherung und Ausrichtung von Strukturen
**Microsoft-spezifisch**  
  
 Strukturmember werden nacheinander in der Reihenfolge gespeichert, in der sie deklariert werden: das erste Member hat die niedrigste Speicheradresse und das letzte Member die höchste.  
  
 Jedes Datenobjekt verfügt über ein *alignment-requirement*. Für eine Struktur ist die Anforderung das größte seiner Member. Jedem Objekt wird ein *offset* zugeordnet, sodass Folgendes gilt:  
  
 *offset* `%` *alignment-requirement* `==` 0  
  
 Benachbarte Bitfelder sind in derselben 1-, 2- oder 4-Byte-Speicherbelegungseinheit gepackt, wenn die Ganzzahltypen die gleiche Größe aufweisen und das folgende Bitfeld in die aktuelle Speicherbelegungseinheit passt, ohne die Grenze zu überschreiten, die durch die allgemeinen Ausrichtungsanforderungen der Bitfelder auferlegt werden.  
  
 Um Speicherplatz zu sparen und vorhandene Datenstrukturen nicht zu überschreiten, können Sie Strukturen relativ kompakt speichern. Die [/Zp](../build/reference/zp-struct-member-alignment.md)[*n*]-Compileroption sowie [#pragma pack](../preprocessor/pack.md) steuern, wie Strukturdaten im Speicher „gepackt“ werden. Wenn Sie die Option „/Zp[*n*]“ verwenden, und *n* gleich 1, 2, 4, 8 oder 16 ist, werden die einzelnen Strukturmember nach dem ersten auf Byte-Begrenzungen gespeichert, die die Ausrichtungsanforderung des Felds oder die Komprimierungsgröße darstellen (*n*), je nachdem, welche kleiner ist. Ausgedrückt als Formel, sind die Bytegrenzen  
  
```  
min( n, sizeof( item ) )  
```  
  
 wobei *n* die Komprimierungsgröße ist, ausgedrückt mit der /Zp[*n*]-Option, und *item* ist der Strukturmember. Die Standardkomprimierungsgröße ist "/Zp8".  
  
 Um mit dem `pack`-Pragma eine andere Komprimierung als die in der Befehlszeile für eine bestimmte Struktur angegebene festzulegen, geben Sie das `pack`-Pragma, bei dem die Komprimierungsgröße 1, 2, 4, 8 oder 16 ist, vor der Struktur an. Um die an der Befehlszeile angegebene Komprimierung wiederherzustellen, geben Sie das `pack`-Pragma ohne Argumente an.  
  
 Bitfelder verwenden für den Microsoft C-Compiler standardmäßig die Größe **long**. Strukturmember werden nach der Größe des Typs oder der /Zp [*n*]-Größe ausgerichtet, je nachdem, welche kleiner ist. Die Standardgröße ist 4.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturdeklarationen](../c-language/structure-declarations.md)