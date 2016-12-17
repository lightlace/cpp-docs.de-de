---
title: "__shiftleft128"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "__shiftleft128"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__shiftleft128 intrinsic"
ms.assetid: 557b846a-8fb0-469d-91ac-1b1fad80dc2a
caps.latest.revision: 17
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# __shiftleft128
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Verschiebt eine 128\-Bit\-Menge, dargestellt als zwei 64\-Bit\-Mengen `LowPart` und `HighPart`, um eine angegebene Anzahl von Bits, die durch `Shift` definiert wird, nach links und gibt die unteren 64 Bits des Ergebnisses zurück.  
  
## Syntax  
  
```  
unsigned __int64 __shiftleft128(     unsigned __int64 LowPart,     unsigned __int64 HighPart,     unsigned char Shift  );  
```  
  
#### Parameter  
 \[in\] `LowPart`  
 Die unteren 64 Bits der zu verschiebenden 128\-Bit\-Menge.  
  
 \[in\] `HighPart`  
 Die oberen 64 Bits der zu verschiebenden 128\-Bit\-Menge.  
  
 \[in\] `Shift`  
 Die Anzahl der zu verschiebenden Bits.  
  
## Rückgabewert  
 Die oberen 64 Bits des Ergebnisses.  
  
## Anforderungen  
  
|Systemintern|Architektur|  
|------------------|-----------------|  
|`__shiftleft128`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Der `Shift`\-Wert ist immer modulo 64. So verschiebt z. B. beim Aufrufen von `__shiftleft128(1, 0, 64)` die Funktion die `0`\-Bits des unteren Teils nach links und gibt einen oberen Teil von `0` und nicht von `1` zurück, wie man annehmen könnte.  
  
## Beispiel  
  
```  
// shiftleft128.c  
// processor: IPF, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic (__shiftleft128, __shiftright128)  
  
int main()  
{  
    unsigned __int64 i = 0x1I64;  
    unsigned __int64 j = 0x10I64;  
    unsigned __int64 ResultLowPart;  
    unsigned __int64 ResultHighPart;  
  
    ResultLowPart = i << 1;  
    ResultHighPart = __shiftleft128(i, j, 1);  
  
    // concatenate the low and high parts padded with 0's  
    // to display correct hexadecimal 128 bit values  
    printf_s("0x%02I64x%016I64x << 1 = 0x%02I64x%016I64x\n",  
             j, i, ResultHighPart, ResultLowPart);  
  
    ResultHighPart = j >> 1;  
    ResultLowPart = __shiftright128(i, j, 1);  
  
    printf_s("0x%02I64x%016I64x >> 1 = 0x%02I64x%016I64x\n",  
             j, i, ResultHighPart, ResultLowPart);    
}  
```  
  
  **0x100000000000000001 \<\< 1 \= 0x200000000000000002**  
**0x100000000000000001 \>\> 1 \= 0x080000000000000000**   
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [\_\_shiftright128](../intrinsics/shiftright128.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)