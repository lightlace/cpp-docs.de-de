---
title: __ull_rshift | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __ull_rshift
dev_langs: C++
helpviewer_keywords:
- ull_rshift intrinsic
- __ull_rshift intrinsic
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c0951a930ad5baec5b293aee0fe8e70c0a38a12f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ullrshift"></a>__ull_rshift
**Microsoft-spezifisch**  
  
 auf X64 Verschiebt einen 64-Bit-Wert, der durch den ersten Parameter auf der rechten Seite angegeben eine Anzahl von Bits, die durch den zweiten Parameter angegeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned __int64 __ull_rshift(   
   unsigned __int64 mask,    
   int nBit   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `mask`  
 Der 64-Bit-Ganzzahl-Wert nach rechts verschoben werden soll.  
  
 [in] `nBit`  
 Die Anzahl der zu verschiebenden modulo 32 auf X86 und modulo auf X64 64 Bits.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Maske verschoben werden, indem `nBit` Bits.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__ull_rshift`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Wenn der zweite Parameter größer als 31 auf X86 (63 auf X64),, die Anzahl modulo 32 (64 auf X64) ausgeführt wird ist, um zu bestimmen, die Anzahl der zu verschiebenden Bits. Die `ull` gibt den Namen an `unsigned long long (unsigned __int64)`.  
  
## <a name="example"></a>Beispiel  
  
```  
// ull_rshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ull_rshift)  
  
int main()  
{  
   unsigned __int64 mask = 0x100;  
   int nBit = 8;  
   mask = __ull_rshift(mask, nBit);  
   cout << hex << mask << endl;  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
1  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [__ll_lshift](../intrinsics/ll-lshift.md)   
 [__ll_rshift](../intrinsics/ll-rshift.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)