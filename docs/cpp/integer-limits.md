---
title: Ganzzahlige Grenzen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- integral limits
- limits, integer
- LIMITS.H header file
- integer limits
ms.assetid: 6922bdbf-0f49-443b-bc03-ee182e4cbd57
caps.latest.revision: 8
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 67240b24df0c741a2441e17ebe9908c05bfca9f3
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="integer-limits"></a>Ganzzahlige Grenzen
**Microsoft-spezifisch**  
  
 Die Grenzwerte für ganzzahlige Typen sind in der folgenden Tabelle aufgeführt. Diese Begrenzungen werden auch in der Standardheaderdatei "LIMITS.H" definiert.  
  
### <a name="limits-on-integer-constants"></a>Grenzwerte für ganzzahlige Konstanten  
  
|Konstante|Bedeutung|Wert|  
|--------------|-------------|-----------|  
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
|**INT_MIN**|Minimalwert für eine Variable vom Typ `int`.|-2147483648|  
|**INT_MAX**|Maximalwert für eine Variable vom Typ `int`.|2147483647|  
|**UINT_MAX**|Maximalwert für eine Variable vom Typ `unsigned int`.|4294967295 (0xffffffff)|  
|**LONG_MIN**|Minimalwert für eine Variable vom Typ **long**.|-2147483648|  
|**LONG_MAX**|Maximalwert für eine Variable vom Typ **long**.|2147483647|  
|**ULONG_MAX**|Maximalwert für eine Variable vom Typ `unsigned long`.|4294967295 (0xffffffff)|  
|**_I64_MIN**|Minimaler Wert für eine Variable vom Typ `__int64`.|-9223372036854775808|  
|**_I64_MAX**|Maximalwert für eine Variable vom Typ `__int64`.|9223372036854775807|  
|**_UI64_MAX**|Maximalwert für eine Variable vom Typ **unsigned __int64**|18446744073709551615 (0xffffffffffffffff)|  
  
 Wenn ein Wert die größte Ganzzahldarstellung übersteigt, generiert der Microsoft-Compiler einen Fehler.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Grenzwerte für Gleitkommakonstanten](../cpp/floating-limits.md)
