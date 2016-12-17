---
title: "Aggregate und Unions"
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
helpviewer_keywords: 
  - "Aggregate [C++], Und Unions"
ms.assetid: 859fc211-b111-4f12-af98-de78e48f9b92
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Aggregate und Unions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Andere Typen wie Arrays, Strukturen und Unions erfordern eine strengere Ausrichtung, um die Konsistenz von Speicher und Datenabruf bei Aggregaten und Unions zu gewährleisten.  Im Folgenden die Definitionen für Array, Struktur und Union:  
  
 Array  
 Enthält eine geordnete Gruppe benachbarter Datenobjekte.  Die einzelnen Objekte werden als Elemente bezeichnet.  Alle Elemente innerhalb eines Arrays besitzen dieselbe Größe und denselben Datentyp.  
  
 Struktur  
 Enthält eine geordnete Gruppe von Datenobjekten.  Im Gegensatz zu den Elementen eines Arrays können die Datenobjekte einer Struktur unterschiedliche Datentypen und Größen besitzen.  Die einzelnen Datenobjekte in einer Struktur werden als Member bezeichnet.  
  
 Union  
 Ein Objekt, das einen beliebigen Member aus einem Satz benannter Member enthält.  Die Member des benannten Satzes können beliebigen Typs sein.  Der einer Union zugewiesene Speicher entspricht dem für den größten Member der Union erforderlichen Speicher, ggf. plus Leerspeicher zur Ausrichtung.  
  
 In der folgenden Tabelle wird die empfohlene Ausrichtung für die skalaren Member von Unions und Strukturen angezeigt.  
  
||||  
|-|-|-|  
|Skalartyp|C\-Datentyp|Erforderliche Ausrichtung|  
|**INT8**|`char`|Byte|  
|**UINT8**|`unsigned char`|Byte|  
|**INT16**|**short**|Word|  
|**UINT16**|**unsigned short**|Word|  
|**INT32**|**int, long**|Doubleword|  
|**UINT32**|**unsigned int, unsigned long**|Doubleword|  
|**INT64**|`__int64`|Quadword|  
|**UINT64**|**unsigned \_\_int64**|Quadword|  
|**FP32 \(einfache Genauigkeit\)**|**float**|Doubleword|  
|**FP64 \(doppelte Genauigkeit\)**|**double**|Quadword|  
|**POINTER**|**\***|Quadword|  
|`__m64`|**struct \_\_m64**|Quadword|  
|`__m128`|**struct \_\_m128**|Octaword|  
  
 Es gelten folgende Aggregatausrichtungsregeln:  
  
-   Die Ausrichtung eines Arrays entspricht der Ausrichtung eines der Array\-Elemente.  
  
-   Die Ausrichtung des Anfangs einer Struktur oder einer Union ist die maximale Ausrichtung eines einzelnen Member.  Jeder Member innerhalb der Struktur oder Union muss korrekt ausgerichtet werden, wie in der vorhergehenden Tabelle definiert. Dabei kann abhängig vom vorhergehenden Member ein implizites internes Auffüllen erforderlich sein.  
  
-   Die Größe der Struktur muss ein ganzzahliges Vielfaches seiner Ausrichtung sein, sodass möglicherweise ein Auffüllen nach dem letzten Member erforderlich ist.  Da Strukturen und Unions in Arrays gruppiert werden können, muss jedes Array\-Element einer Struktur oder Union an der zuvor bestimmten korrekten Ausrichtung beginnen und enden.  
  
-   Daten können auf eine solche Weise ausgerichtet werden, dass sie größer als die Ausrichtungsanforderungen sind, solange die oben genannten Regeln eingehalten werden.  
  
-   Ein bestimmter Compiler kann de Komprimierung einer Struktur aus Gründen der Größe anpassen.  Beispielsweise erlaubt [\/Zp \(Ausrichten des Strukturmembers\)](../build/reference/zp-struct-member-alignment.md) das Anpassen der Komprimierung von Strukturen.  
  
## Siehe auch  
 [Typen und Speicher](../build/types-and-storage.md)