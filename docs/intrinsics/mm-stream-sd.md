---
title: _mm_stream_sd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_stream_sd
dev_langs:
- C++
helpviewer_keywords:
- _mm_stream_sd intrinsic
- movntsd instruction
ms.assetid: 2b4bea5e-e64e-45fa-9afc-88a2e4b82cfc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3e8a65066ad19b78319867782255d70da8d5b721
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="mmstreamsd"></a>_mm_stream_sd
**Microsoft-spezifisch**  
  
 Schreibt 64-Bit-Daten auf eine Speicheradresse, ohne die Caches beschädigen.  
  
## <a name="syntax"></a>Syntax  
  
```  
void _mm_stream_sd(  
   double * Dest,  
   __m128d Source  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `Dest`  
 Ein Zeiger auf den Speicherort, in denen die Quelldaten geschrieben wird.  
  
 [in] `Source`  
 Eine 128-Bit-Wert, der `double` Wert in die unteren 64 Bits geschrieben werden...  
  
## <a name="return-value"></a>Rückgabewert  
 Keine  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`_mm_stream_sd`|SSE4a|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Diese systeminterne Funktion generiert die `movntsd` Anweisung. Um Hardware-Unterstützung für diese Anweisung zu bestimmen, rufen die `__cpuid` systeminternen Funktionen mit `InfoType=0x80000001` und überprüfen Sie Bit 6 von `CPUInfo[2] (ECX)`. Dieses Bit ist 1, wenn die Hardware diese Anweisung, und 0 unterstützt.  
  
 Wenn Sie Code ausführen, verwendet der `_mm_stream_sd` syteminternen Funktion bei der Hardware, die nicht unterstützt wird die `movntsd` -Anweisung, die die Ergebnisse sind unvorhersehbar.  
  
## <a name="example"></a>Beispiel  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
int main()  
{  
    __m128d vals;  
    double d[2];  
  
    d[0] = -1.;  
    d[1] = -2.;  
    vals.m128d_f64[0] = 0.;  
    vals.m128d_f64[1] = 1.;  
    _mm_stream_sd(&d[1], vals);  
    cout << "d[0] = " << d[0] << ", d[1] = " << d[1] << endl;  
}  
  
```  
  
```Output  
d[0] = -1, d[1] = 1  
```  
  
**Ende Microsoft-spezifisch**  
 Copyright 2007 erweiterte Micro-Geräte, Inc. Alle Rechte vorbehalten. Reproduziert mit Genehmigung Advanced Micro-Geräte, Inc.  
  
## <a name="see-also"></a>Siehe auch  
 [_mm_stream_ss](../intrinsics/mm-stream-ss.md)   
 [_mm_store_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_sd)   
 [_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)