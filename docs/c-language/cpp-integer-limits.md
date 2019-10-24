---
title: C- C++ und ganzzahlige Limits
ms.date: 10/21/2019
helpviewer_keywords:
- limits, integer
- limits, integer constants
- integer limits
ms.assetid: 0c23cbd6-29fb-4d9c-b689-5984e19748de
ms.openlocfilehash: 6940f36e37ec58ca8fe23c9062928cbf90b125bd
ms.sourcegitcommit: ea9d78dbb93bf3f8841dde93dbc12bd66f6f32ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72778375"
---
# <a name="c-and-c-integer-limits"></a>C- C++ und ganzzahlige Limits

**Microsoft-spezifisch**

Die Grenzwerte für ganzzahlige Typen C++ in C und sind in der folgenden Tabelle aufgeführt. Diese Grenzwerte werden in der C-Standard Header Datei `<limits.h>` definiert. Der C++ Standard Bibliotheks Header `<limits>` enthält `<climits>`, der `<limits.h>` enthält.

Microsoft C gestattet auch die Deklaration von ganz Zahl Variablen mit Größenangabe, bei denen es sich um ganzzahlige Typen der Größe 8-, 16-, 32-oder 64-Bits handelt. Weitere Informationen zu Größen Ganzzahlen in C finden Sie unter [Integer Integer Types](../c-language/c-sized-integer-types.md).

## <a name="limits-on-integer-constants"></a>Grenzwerte für ganzzahlige Konstanten

|**Konstante**|Bedeutung|Wert|
|------------------|-------------|-----------|
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
|**INT_MIN**|Minimalwert für eine Variable vom Typ **int**.|-2147483647 - 1|
|**INT_MAX**|Maximalwert für eine Variable vom Typ **int**.|2147483647|
|**UINT_MAX**|Maximalwert für eine Variable vom Typ **unsigned int**.|4294967295 (0xffffffff)|
|**LONG_MIN**|Minimalwert für eine Variable vom Typ **long**.|-2147483647 - 1|
|**LONG_MAX**|Maximalwert für eine Variable vom Typ **long**.|2147483647|
|**ULONG_MAX**|Maximalwert für eine Variable vom Typ **unsigned long**.|4294967295 (0xffffffff)|
|**LLONG_MIN**|Minimalwert für eine Variable vom Typ **Long Long**.|-9.223.372.036.854.775.807-1|
|**LLONG_MAX**|Maximalwert für eine Variable vom Typ **Long Long**.|9,223,372,036,854,775,807|
|**ULLONG_MAX**|Maximalwert für eine Variable vom Typ " **Ganzzahl ohne Vorzeichen long long**".|18446744073709551615 (0xFFFFFFFFFFFFFFFF)|

Wenn ein Wert die größte Ganzzahldarstellung übersteigt, generiert der Microsoft-Compiler einen Fehler.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[C-Ganzzahlkonstanten](../c-language/c-integer-constants.md)
