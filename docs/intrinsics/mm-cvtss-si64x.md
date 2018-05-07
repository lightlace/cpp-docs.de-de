---
title: _mm_cvtss_si64x | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_cvtss_si64x
dev_langs:
- C++
helpviewer_keywords:
- cvtss2si intrinsic
- _mm_cvtss_si64x intrinsic
ms.assetid: c279aff2-ee29-4271-8829-3ec691bf7718
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 665c52fc0dd0645e25d3014cc28f9fdfba344e2d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="mmcvtsssi64x"></a>_mm_cvtss_si64x
**Microsoft-spezifisch**  
  
 Generiert die [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] erweiterte Version der konvertieren Skalar einzelne Genauigkeit Gleitkommazahl in 64-Bit-Ganzzahl (`cvtss2si`) Anweisung.  
  
## <a name="syntax"></a>Syntax  
  
```  
__int64 _mm_cvtss_si64x(   
   __m128 value   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `value`  
 Eine `__m128` -Struktur,-Gleitkommawerte enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 Eine 64-Bit-Ganzzahl, das Ergebnis der Konvertierung des ersten Gleitkommawerts in eine ganze Zahl.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`_mm_cvtss_si64x`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Das erste Element des Werts Struktur wird in eine ganze Zahl konvertiert und zurückgegeben. Die Rundung Steuerungsbits im MXCSR werden verwendet, um das Rundungsverhalten zu bestimmen. Die Standardeinstellung ist rund um am nächsten liegt, auf die gerade Zahl gerundet wird, wenn der Dezimalwert 0,5 beträgt. Da die `__m128` Struktur stellt eine XMM-Register diese systeminterne Funktion nimmt einen Wert aus dem XMM-Register und schreibt sie in den Systemarbeitsspeicher.  
  
 Diese Routine ist nur als systeminterne Funktion verfügbar.  
  
## <a name="example"></a>Beispiel  
  
```  
// _mm_cvtss_si64x.cpp  
// processor: x64  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvtss_si64x)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    // _mm_load_ps requires an aligned buffer.  
    __declspec(align(16)) float af[4] =  
                           { 101.25, 200.75, 300.5, 400.5 };  
  
    // Load a with the floating point values.  
    // The values will be copied to the XMM registers.  
    a = _mm_load_ps(af);  
  
    // Extract the first element of a and convert to an integer  
    b = _mm_cvtss_si64x(a);  
  
    printf_s("%I64d\n", b);  
}  
```  
  
```Output  
101  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [__m128d](../cpp/m128d.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)