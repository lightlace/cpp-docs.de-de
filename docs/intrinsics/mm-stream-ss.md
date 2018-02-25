---
title: _mm_stream_ss | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- _mm_stream_ss
dev_langs:
- C++
helpviewer_keywords:
- movntss instruction
- _mm_stream_ss intrinsic
ms.assetid: c53dffe9-0dfe-4063-85d3-e8987b870fce
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 420952d58bb46012741ee95ced4cf39c12d381cd
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="mmstreamss"></a>_mm_stream_ss  
  
**Microsoft-spezifisch**  
  
 Schreibt 32-Bit-Daten auf eine Speicheradresse, ohne die Caches beschädigen.  
  
## <a name="syntax"></a>Syntax  
  
```  
void _mm_stream_ss(  
   float * Dest,  
   __m128 Source  
);  
```  
  
#### <a name="parameters"></a>Parameter  
  
 [out] `Dest`  
 Ein Zeiger auf den Speicherort, in die Quelldaten geschrieben wird.  
  
 [in] `Source`  
 Eine 128-Bit-Zahl, die enthält die `float` Wert in die unteren 32 Bits geschrieben werden...  
  
## <a name="return-value"></a>Rückgabewert  
  
 Keine  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`_mm_stream_ss`|SSE4a|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
  
Diese systeminterne Funktion generiert die `movntss` Anweisung. Um Hardware-Unterstützung für diese Anweisung zu bestimmen, rufen die `__cpuid` systeminternen Funktionen mit `InfoType=0x80000001` und überprüfen Sie Bit 6 von `CPUInfo[2] (ECX)`. Dieses Bit ist 1, wenn die Anweisung unterstützt wird und 0 andernfalls.  
  
Wenn Sie Code ausführen, verwendet der `_mm_stream_ss` syteminternen Funktion bei der Hardware, die nicht unterstützt wird die `movntss` -Anweisung, die die Ergebnisse sind unvorhersehbar.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
int main()  
{  
    __m128 vals;  
    float f[4];  
  
    f[0] = -1.;  
    f[1] = -2.;  
    f[2] = -3.;  
    f[3] = -4.;  
    vals.m128_f32[0] = 0.;  
    vals.m128_f32[1] = 1.;  
    vals.m128_f32[2] = 2.;  
    vals.m128_f32[3] = 3.;  
    _mm_stream_ss(&f[3], vals);  
    cout << "f[0] = " << f[0] << ", f[1] = " << f[1] << endl;  
    cout << "f[1] = " << f[1] << ", f[3] = " << f[3] << endl;  
}  
```  
  
```Output  
f[0] = -1, f[1] = -2  
f[2] = -3, f[3] = 3  
```  
  
**Ende Microsoft-spezifisch**  

Copyright 2007 erweiterte Micro-Geräte, Inc. Alle Rechte vorbehalten. Reproduziert mit Genehmigung Advanced Micro-Geräte, Inc.  
  
## <a name="see-also"></a>Siehe auch  
 [_mm_stream_sd](../intrinsics/mm-stream-sd.md)   
 [_mm_stream_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_stream_ps)   
 [_mm_store_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_ss)   
 [_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)