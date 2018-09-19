---
title: _mm_insert_si64, _mm_inserti_si64 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_inserti_si64
- _mm_insert_si64
dev_langs:
- C++
helpviewer_keywords:
- insertq instruction
- _mm_insert_si64 intrinsic
- _mm_inserti_si64 intrinsic
ms.assetid: 897a4b36-8b08-4b00-a18f-7850f5732d7d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a1c6b21ded6814492557ced792772508add06e53
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712835"
---
# <a name="mminsertsi64-mminsertisi64"></a>_mm_insert_si64, _mm_inserti_si64

**Microsoft-spezifisch**  
  
Generiert die `insertq` Anweisung zum Einfügen von Bits aus den zweiten Operanden in den ersten Operanden.  
  
## <a name="syntax"></a>Syntax  
  
```  
__m128i _mm_insert_si64(  
   __m128i Source1,  
   __m128i Source2  
);  
__m128i _mm_inserti_si64(  
   __m128i Source1,  
   __m128i Source2  
   int Length,  
   int Index  
);  
```  
  
#### <a name="parameters"></a>Parameter  
*Quelle1*<br/>
[in] Ein 128-Bit-Feld mit den Daten in die unteren 64 Bits in denen ein Feld eingefügt wird.  
  
*Source2*<br/>
[in] Ein 128-Bit-Feld mit den Daten zum Einfügen in die low-Bits.  Für `_mm_insert_si64`, enthält auch einen Feld-Deskriptor in der oberen Bits.  
  
*Länge*<br/>
[in] Eine ganzzahlige Konstante, die die Länge des Felds einzufügende angibt.  
  
*Index*<br/>
[in] Eine ganzzahlige Konstante, die den Index des Felds das niederwertigste Bit gibt an, in dem Daten eingefügt werden.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein 128-Bit-Feld, dessen unteren 64 Bits die ursprünglichen unteren 64 Bits des enthalten `Source1` durch das angegebene Bitfeld ersetzt werden soll, durch die niedrigen Bits des `Source2`. Die oberen 64 Bits des Rückgabewerts sind nicht definiert.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`_mm_insert_si64`|SSE4a|  
|`_mm_inserti_si64`|SSE4a|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Dieser systeminternen Funktion generiert die `insertq` Anweisung zum Einfügen von Bits aus `Source2` in `Source1`. Es gibt zwei Versionen dieser Funktion: `_mm_inserti_si64`, ist die sofortige-Version und `_mm_insert_si64` wird nicht sofort.  Jede Version einen Bit-Feld mit einer angegebenen Länge aus Source2 extrahiert und fügt es in Quelle1.  Die extrahierten Bits werden die unwichtigsten Bits des Quelle2.  Das Feld Quelle1, in dem diese Bits eingefügt werden, wird durch die Länge und den Index der unwichtigsten Bit definiert.  Die Werte der Länge und Index stammen mod 64, daher sowohl -1 und 127 als 63 interpretiert werden. Wenn die Summe aus der (geringere)-Bit-Index und die Feldlänge (geringere) größer als 64 ist, sind die Ergebnisse nicht definiert. Der Wert 0 (null), für die Feldlänge ist als 64 interpretiert.  Wenn der Feldindex für Länge und Bit beide NULL Bits 63:0 von sind `Source2` einfügen in `Source1`.  Wenn die Länge 0 (null ist), aber der Bit-Index nicht 0 (null ist), sind die Ergebnisse nicht definiert.  
  
 In einem Aufruf _mm_insert_si64 ist die Länge des Felds in Bits 77:72 Source2 und der Index in Bits 69:64 enthalten.  
  
 Wenn Sie aufrufen `_mm_inserti_si64` Argumente an, dass der Compiler nicht ermitteln kann, werden ganzzahlige Konstanten, generiert der Compiler Code, um diese Werte in einer XMM-Register zu packen und zum Aufrufen `_mm_insert_si64`.  
  
 Um zu bestimmen, Hardware-Unterstützung für die `insertq` Anweisungsaufruf der `__cpuid` systeminternen Funktionen mit `InfoType=0x80000001` und überprüfen Sie wenig 6 `CPUInfo[2] (ECX)`. Dieses Bit wird 1, wenn die Anweisung unterstützt wird und 0 andernfalls. Wenn Sie Code, verwendet dieser systeminternen Funktion auf Hardware ausgeführt, die nicht unterstützt. die `insertq` -Anweisung, die die Ergebnisse sind unvorhersehbar.  
  
## <a name="example"></a>Beispiel  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
union {  
    __m128i m;  
    unsigned __int64 ui64[2];  
} source1, source2, source3, result1, result2, result3;  
  
int  
main()  
{  
  
    __int64 mask;  
  
    source1.ui64[0] = 0xffffffffffffffffll;  
    source2.ui64[0] = 0xfedcba9876543210ll;  
    source2.ui64[1] = 0xc10;  
    source3.ui64[0] = source2.ui64[0];  
  
    result1.m = _mm_insert_si64 (source1.m, source2.m);  
    result2.m = _mm_inserti_si64(source1.m, source3.m, 16, 12);  
    mask = 0xffff << 12;  
    mask = ~mask;  
    result3.ui64[0] = (source1.ui64[0] & mask) |  
                      ((source2.ui64[0] & 0xffff) << 12);  
  
    cout << hex << "result1 = 0x" << result1.ui64[0] << endl;  
    cout << "result2 = 0x" << result2.ui64[0] << endl;  
    cout << "result3 = 0x" << result3.ui64[0] << endl;  
  
}  
```  
  
```Output  
result1 = 0xfffffffff3210fff  
result2 = 0xfffffffff3210fff  
result3 = 0xfffffffff3210fff  
```  
  
**Ende Microsoft-spezifisch**  

Copyright 2007 erweiterten Micro-Geräte, Inc. Alle Rechte vorbehalten. Reproduziert werden, mit der Berechtigung, die von erweiterten Micro-Geräte, Inc.  
  
## <a name="see-also"></a>Siehe auch  
 [_mm_extract_si64, _mm_extracti_si64](../intrinsics/mm-extract-si64-mm-extracti-si64.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)