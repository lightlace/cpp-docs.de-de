---
title: Ganzzahlige Grenzen in C++ | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- limits, integer
- limits, integer constants
- integer limits
ms.assetid: 0c23cbd6-29fb-4d9c-b689-5984e19748de
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: c1d45ba449173c5cc2bf3fbed663a7d987c22e1c
ms.lasthandoff: 04/01/2017

---
# <a name="c-integer-limits"></a>Ganzzahlige Grenzen in C++
**Microsoft-spezifisch**  
  
 Die Grenzwerte für ganzzahlige Typen sind in der folgenden Tabelle aufgeführt. Diese Grenzwerte werden in der Standardheaderdatei LIMITS.H definiert. Microsoft C ermöglicht zudem die Deklaration von Ganzzahlvariablen mit angegebener Größe, die ganzzahlige Typen der Größe 8-, 16-, oder 32-Bit sind. Weitere Informationen über ganze Zahlen mit angepasster Größe finden Sie unter [Angepasste Ganzzahltypen](../c-language/c-sized-integer-types.md).  
  
### <a name="limits-on-integer-constants"></a>Grenzwerte für ganzzahlige Konstanten  
  
|**Konstante**|Bedeutung|Wert|  
|------------------|-------------|-----------|  
|**CHAR_BIT**|Anzahl von Bits in der kleinsten Variable, die kein Bitfeld ist.|8|  
|**SCHAR_MIN**|Minimalwert für eine Variable vom Typ **signed char**.|-128|  
|**SCHAR_MAX**|Maximalwert für eine Variable vom Typ **signed char**.|127|  
|**UCHAR_MAX**|Maximalwert für eine Variable vom Typ `unsigned char`.|255 (0xff)|  
|**CHAR_MIN**|Minimalwert für eine Variable vom Typ `char`.|-128; 0 wenn /J-Option verwendet|  
|**CHAR_MAX**|Maximalwert für eine Variable vom Typ `char`.|127; 255 wenn /J-Option verwendet|  
|**MB_LEN_MAX**|Maximale Anzahl von Bytes in einer Konstante mit mehreren Zeichen.|5|  
|**SHRT_MIN**|Minimalwert für eine Variable vom Typ **short**.|-32768|  
|**SHRT_MAX**|Maximalwert für eine Variable vom Typ **short**.|32767|  
|**USHRT_MAX**|Maximalwert für eine Variable vom Typ **unsigned short**.|65535 (0xffff)|  
|**INT_MIN**|Minimalwert für eine Variable vom Typ `int`.|-2147483647 - 1|  
|**INT_MAX**|Maximalwert für eine Variable vom Typ `int`.|2147483647|  
|**UINT_MAX**|Maximalwert für eine Variable vom Typ `unsigned int`.|4294967295 (0xffffffff)|  
|**LONG_MIN**|Minimalwert für eine Variable vom Typ **long**.|-2147483647 - 1|  
|**LONG_MAX**|Maximalwert für eine Variable vom Typ **long**.|2147483647|  
|**ULONG_MAX**|Maximalwert für eine Variable vom Typ `unsigned long`.|4294967295 (0xffffffff)|  
  
 Wenn ein Wert die größte Ganzzahldarstellung übersteigt, generiert der Microsoft-Compiler einen Fehler.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [C-Ganzzahlkonstanten](../c-language/c-integer-constants.md)
