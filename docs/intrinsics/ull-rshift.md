---
title: "__ull_rshift"
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
  - "__ull_rshift"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ull_rshift intrinsic"
  - "__ull_rshift intrinsic"
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# __ull_rshift
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ein 64\-Bit\-Wert Verschiebungen x64 für den ersten Parameter angegeben durch mehrere Bits nach rechts angegeben durch den zweiten Parameter.  
  
## Syntax  
  
```  
unsigned __int64 __ull_rshift(   
   unsigned __int64 mask,    
   int nBit   
);  
```  
  
#### Parameter  
 \[in\] `mask`  
 Der 64\-Bit\-Ganzzahlwert Rechts, um das verschoben werden soll.  
  
 \[in\] `nBit`  
 Die Anzahl der Bits verschoben. von Modulo 32 auf x86 und Modulo 64 x64.  
  
## Rückgabewert  
 Die Maske durch `nBit` Bits verschoben.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__ull_rshift`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Wenn der zweite Parameter größer als 31 \(63 auf x86 auf x64\), wird diese Zahl den Modulo \(64 32, ausgeführt auf x64\), um die Anzahl der Bits zu bestimmen, um sich selbst zu verschieben.  `ull` im Namen vorhanden ist `unsigned long long (unsigned __int64)`an.  
  
## Beispiel  
  
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
  
## Output  
  
```  
1  
```  
  
### Microsoft ENDES bestimmten  
  
## Siehe auch  
 [\_\_ll\_lshift](../intrinsics/ll-lshift.md)   
 [\_\_ll\_rshift](../intrinsics/ll-rshift.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)