---
title: "Ganzzahlige Grenzen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ganzzahlige Grenzen"
  - "Ganzzahlige Grenzen"
  - "Einschränkungen, Ganze Zahl"
  - "LIMITS.H-Headerdatei"
ms.assetid: 6922bdbf-0f49-443b-bc03-ee182e4cbd57
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Ganzzahlige Grenzen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Die Grenzwerte für ganzzahlige Typen sind in der folgenden Tabelle aufgeführt.  Diese Begrenzungen werden auch in der Standardheaderdatei "LIMITS.H" definiert.  
  
### Grenzwerte für ganzzahlige Konstanten  
  
|Konstante|Bedeutung|Wert|  
|---------------|---------------|----------|  
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
|**INT\_MIN**|Minimalwert für eine Variable vom Typ `int`.|–2147483648|  
|**INT\_MAX**|Maximalwert für eine Variable vom Typ `int`.|2147483647|  
|**UINT\_MAX**|Maximalwert für eine Variable vom Typ `unsigned int`.|4294967295 \(0xffffffff\)|  
|**LONG\_MIN**|Minimalwert für eine Variable vom Typ **long**.|–2147483648|  
|**LONG\_MAX**|Maximalwert für eine Variable vom Typ **long**.|2147483647|  
|**ULONG\_MAX**|Maximalwert für eine Variable vom Typ `unsigned long`.|4294967295 \(0xffffffff\)|  
|**\_I64\_MIN**|Minimaler Wert für eine Variable vom Typ `__int64`.|\-9223372036854775808|  
|**\_I64\_MAX**|Maximalwert für eine Variable vom Typ `__int64`.|9223372036854775807|  
|**\_UI64\_MAX**|Maximalwert für eine Variable vom Typ **unsigned \_\_int64**.|18446744073709551615 \(0xffffffffffffffff\)|  
  
 Wenn ein Wert die größte Ganzzahldarstellung übersteigt, generiert der Microsoft\-Compiler einen Fehler.  
  
## END Microsoft\-spezifisch  
  
## Siehe auch  
 [Grenzwerte für Gleitkommakonstanten](../cpp/floating-limits.md)