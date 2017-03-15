---
title: "_BitScanForward, _BitScanForward64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_BitScanForward"
  - "_BitScanForward_cpp"
  - "_BitScanForward64_cpp"
  - "_BitScanForward64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_BitScanForward intrinsic"
  - "BitScanForward intrinsic"
  - "bsf instruction"
ms.assetid: 405e60fb-0815-42a7-9b02-6fc035122203
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _BitScanForward, _BitScanForward64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Suchen Sie die Maskendaten vom niedrigstwertigen Bit \(LSB\) bis zum höchstwertigen Bit \(MSB\) für ein festgelegtes Bit \(1\).  
  
## Syntax  
  
```  
unsigned char _BitScanForward(    unsigned long * Index,    unsigned long Mask ); unsigned char _BitScanForward64(    unsigned long * Index,    unsigned __int64 Mask );  
```  
  
#### Parameter  
 \[out\] `Index`  
 Geladen mit der Bitposition des ersten festgelegten Bits \(1\), das ermittelt wurde.  
  
 \[in\] `Mask`  
 Der zu suchende 32\-Bit\- oder 64\-Bit\-Wert.  
  
## Rückgabewert  
 0, wenn die Maske null ist; andernfalls ungleich null.  
  
## Hinweise  
 Wenn ein festgelegtes Bit gefunden wird, wird die Bitposition des ersten festgelegten gefundenen Bits in den ersten Parameter zurückgegeben.  Wenn kein festgelegtes Bit gefunden wird, wird 0 zurückgegeben; andernfalls wird 1 zurückgegeben.  
  
## Anforderungen  
  
|Systemintern|Architektur|  
|------------------|-----------------|  
|`_BitScanForward`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`_BitScanForward64`|ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Beispiel  
  
```  
// BitScanForward.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(_BitScanForward)  
  
int main()  
{  
   unsigned long mask = 0x1000;  
   unsigned long index;  
   unsigned char isNonzero;  
  
   cout << "Enter a positive integer as the mask: " << flush;  
   cin >> mask;  
   isNonzero = _BitScanForward(&index, mask);  
   if (isNonzero)  
   {  
      cout << "Mask: " << mask << " Index: " << index << endl;  
   }  
   else  
   {  
      cout << "No set bits found.  Mask is zero." << endl;  
   }  
}  
```  
  
## Eingabe  
  
```  
12  
```  
  
## Beispielausgabe  
  
```  
Enter a positive integer as the mask:   
Mask: 12 Index: 2  
```  
  
### Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)