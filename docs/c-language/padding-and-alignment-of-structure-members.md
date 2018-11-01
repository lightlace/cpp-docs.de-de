---
title: Abstand und Ausrichtung von Strukturmembern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- structure members, padding and alignment
ms.assetid: c999820b-dd47-41fc-b923-e4c7ebbcd30f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a1b301372a9998197c46c1e44c91c9d3456cea8e
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808211"
---
# <a name="padding-and-alignment-of-structure-members"></a>Abstand und Ausrichtung von Strukturmembern

**ANSI 3.5.2.1** Der Abstand und die Ausrichtung von Strukturmembern und die Angabe, ob ein Bitfeld eine Speichereinheitsgrenze umspannen kann

Strukturmember werden nacheinander in der Reihenfolge gespeichert, in der sie deklariert werden: das erste Member hat die niedrigste Speicheradresse und das letzte Member die höchste.

Jedes Datenobjekt verfügt über ein alignment-requirement. Das alignment-requirement für alle Daten (außer Strukturen, Unions und Arrays) ist entweder die Größe des Objekts oder die aktuelle Komprimierungsgröße (diese wird entweder mit "/Zp" oder dem `pack`-Pragma angegeben, je nachdem, was kleiner ist). Bei Strukturen, Unions und Arrays ist das alignment-requirement die größte Ausrichtungsanforderung ihrer Member. Jedem Objekt wird ein offset zugeordnet, sodass Folgendes gilt:

*offset* **%** *alignment-requirement* **== 0**

Benachbarte Bitfelder sind in derselben 1-, 2- oder 4-Byte-Speicherbelegungseinheit gepackt, wenn die Ganzzahltypen die gleiche Größe aufweisen und das folgende Bitfeld in die aktuelle Speicherbelegungseinheit passt, ohne die Grenze zu überschreiten, die durch die allgemeinen Ausrichtungsanforderungen der Bitfelder auferlegt werden.

## <a name="see-also"></a>Siehe auch

[Strukturen, Unions, Enumerationen und Bitfelder](../c-language/structures-unions-enumerations-and-bit-fields.md)