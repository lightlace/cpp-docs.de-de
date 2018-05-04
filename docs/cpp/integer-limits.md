---
title: Ganzzahlige Grenzen | Microsoft Docs
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- integral limits
- limits, integer
- limits.h header file
- integer limits
ms.assetid: 6922bdbf-0f49-443b-bc03-ee182e4cbd57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 656873dc510f53fc05250a28c61cc452078c4aca
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="integer-limits"></a>Ganzzahlige Grenzen

**Microsoft-spezifisch**

Die Grenzwerte für ganzzahlige Typen sind in der folgenden Tabelle aufgeführt. Diese Begrenzungen werden auch in der Standardheaderdatei < limits.h > definiert.

## <a name="limits-on-integer-constants"></a>Grenzwerte für ganzzahlige Konstanten

|Konstante|Bedeutung|Wert|
|--------------|-------------|-----------|
|**CHAR_BIT**|Anzahl von Bits in der kleinsten Variable, die kein Bitfeld ist.|8|
|**SCHAR_MIN**|Minimalwert für eine Variable vom Typ **signed char**.|-128|
|**SCHAR_MAX**|Maximalwert für eine Variable vom Typ **signed char**.|127|
|**UCHAR_MAX**|Maximalwert für eine Variable vom Typ **unsigned char**.|255 (0xff)|
|**CHAR_MIN**|Minimalwert für eine Variable vom Typ **char**.|-128; 0 wenn /J-Option verwendet|
|**CHAR_MAX**|Maximalwert für eine Variable vom Typ **char**.|127; 255 wenn /J-Option verwendet|
|**MB_LEN_MAX**|Maximale Anzahl von Bytes in einer Konstante mit mehreren Zeichen.|5|
|**SHRT_MIN**|Minimalwert für eine Variable vom Typ **short**.|-32768|
|**SHRT_MAX**|Maximalwert für eine Variable vom Typ **short**.|32767|
|**USHRT_MAX**|Maximalwert für eine Variable vom Typ **unsigned short**.|65535 (0xffff)|
|**INT_MIN**|Minimalwert für eine Variable vom Typ **int**.|-2147483648|
|**INT_MAX**|Maximalwert für eine Variable vom Typ **int**.|2147483647|
|**UINT_MAX**|Maximalwert für eine Variable vom Typ **unsigned int**.|4294967295 (0xffffffff)|
|**LONG_MIN**|Minimalwert für eine Variable vom Typ **long**.|-2147483648|
|**LONG_MAX**|Maximalwert für eine Variable vom Typ **long**.|2147483647|
|**ULONG_MAX**|Maximalwert für eine Variable vom Typ **unsigned long**.|4294967295 (0xffffffff)|
|**LLONG_MIN**|Minimalwert für eine Variable vom Typ **long long**|-9223372036854775808|
|**LLONG_MAX**|Maximalwert für eine Variable vom Typ **long long**|9223372036854775807|
|**ULLONG_MAX**|Maximalwert für eine Variable vom Typ **unsigned long long**|18446744073709551615 (0xffffffffffffffff)|

Wenn ein Wert die größte Ganzzahldarstellung übersteigt, generiert der Microsoft-Compiler einen Fehler.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Grenzwerte für Gleitkommakonstanten](../cpp/floating-limits.md)  
