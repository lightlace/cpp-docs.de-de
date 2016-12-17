---
title: "Ganzzahlige Grenzen in C++"
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
  - "Ganzzahlige Grenzen"
  - "Einschränkungen, Ganze Zahl"
  - "Einschränkungen, Ganzzahlkonstanten"
ms.assetid: 0c23cbd6-29fb-4d9c-b689-5984e19748de
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Ganzzahlige Grenzen in C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Die Grenzwerte für ganzzahlige Typen sind in der folgenden Tabelle aufgeführt.  Diese Grenzwerte werden in der Standardheaderdatei LIMITS.H definiert.  Microsoft C ermöglicht zudem die Deklaration von Ganzzahlvariablen mit angegebener Größe, die ganzzahlige Typen der Größe 8\-, 16\-, oder 32\-Bit sind.  Weitere Informationen über ganze Zahlen mit angepasster Größe finden Sie unter [Angepasste Ganzzahltypen](../c-language/c-sized-integer-types.md).  
  
### Grenzwerte für ganzzahlige Konstanten  
  
|**Konstante**|Bedeutung|Wert|  
|-------------------|---------------|----------|  
|**CHAR\_BIT**|Anzahl von Bits in der kleinsten Variable, die kein Bitfeld ist.|8|  
|**SCHAR\_MIN**|Minimalwert für eine Variable vom Typ **signed char**.|–128|  
|**SCHAR\_MAX**|Maximalwert für eine Variable vom Typ **signed char**.|127|  
|**UCHAR\_MAX**|Maximalwert für eine Variable vom Typ `unsigned char`.|255 \(0xff\)|  
|**CHAR\_MIN**|Minimalwert für eine Variable vom Typ `char`.|– 128; 0 wenn \/J\-Option verwendet|  
|**CHAR\_MAX**|Maximalwert für eine Variable vom Typ `char`.|127; 255 wenn \/J\-Option verwendet|  
|**MB\_LEN\_MAX**|Maximale Anzahl von Bytes in einer Konstante mit mehreren Zeichen.|5|  
|**SHRT\_MIN**|Minimalwert für eine Variable vom Typ **short**.|–32768|  
|**SHRT\_MAX**|Maximalwert für eine Variable vom Typ **short**.|32767|  
|**USHRT\_MAX**|Maximalwert für eine Variable vom Typ **unsigned short**.|65535 \(0xffff\)|  
|**INT\_MIN**|Minimalwert für eine Variable vom Typ `int`.|–2147483647 – 1|  
|**INT\_MAX**|Maximalwert für eine Variable vom Typ `int`.|2147483647|  
|**UINT\_MAX**|Maximalwert für eine Variable vom Typ `unsigned int`.|4294967295 \(0xffffffff\)|  
|**LONG\_MIN**|Minimalwert für eine Variable vom Typ **long**.|–2147483647 – 1|  
|**LONG\_MAX**|Maximalwert für eine Variable vom Typ **long**.|2147483647|  
|**ULONG\_MAX**|Maximalwert für eine Variable vom Typ `unsigned long`.|4294967295 \(0xffffffff\)|  
  
 Wenn ein Wert die größte Ganzzahldarstellung übersteigt, generiert der Microsoft\-Compiler einen Fehler.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [C\-Ganzzahlkonstanten](../c-language/c-integer-constants.md)