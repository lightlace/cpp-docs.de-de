---
title: "__ll_rshift | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__ll_rshift_cpp"
  - "__ll_rshift"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__ll_rshift intrinsic"
  - "ll_rshift intrinsic"
ms.assetid: ef13b732-d122-44a0-add9-f5544a2c4ab2
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# __ll_rshift
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Verschiebt einen 64\-Bit\-Wert, der durch den ersten Parameter mehrere Bits nach rechts angegeben ist, die durch den zweiten Parameter angegeben werden.  
  
## Syntax  
  
```  
__int64 __ll_rshift(  
   __int64 Mask,  
   int nBit  
);  
```  
  
#### Parameter  
 \[in\] `Mask`  
 Der 64\-Bit\-Ganzzahlwert Rechts, um das verschoben werden soll.  
  
 \[in\] `nBit`  
 Die Anzahl der Bits verschoben. von Modulo 64 x64 und Modulo 32 auf x86.  
  
## Rückgabewert  
 Die Maske durch `nBit` Bits verschoben.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__ll_rshift`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Wenn der zweite Parameter größer als 64 \(null\) auf 32 auf x86 \(x64\), wird diese Zahl den Modulo übernommen, 64 \(32 auf x86\), um die Anzahl der Bits zu bestimmen, um sich selbst zu verschieben.  Das Präfix `ll` gibt an, dass dies ein Vorgang für `long long`ist, ein anderer Name für `__int64`, der 64\-Bit\-ganzzahlige Typ mit Vorzeichen.  
  
## Beispiel  
  
```  
// ll_rshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ll_rshift)  
  
int main()  
{  
   __int64 Mask = - 0x100;  
   int nBit = 4;  
   cout << hex << Mask << endl;  
   cout << " - " << (- Mask) << endl;  
   Mask = __ll_rshift(Mask, nBit);  
   cout << hex << Mask << endl;  
   cout << " - " << (- Mask) << endl;  
}  
```  
  
## Output  
  
```  
ffffffffffffff00  
 - 100  
fffffffffffffff0  
 - 10  
```  
  
 **Hinweis**, wenn `_ull_rshift` verwendet wurde, würde das MSB des Werts RIGHT\-verschobenen wurden \(null\) sein. Daher würde das gewünschte Ergebnis nicht im Falle eines negativen Werts erzielt worden sein.  
  
### Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [\_\_ll\_lshift](../intrinsics/ll-lshift.md)   
 [\_\_ull\_rshift](../intrinsics/ull-rshift.md)