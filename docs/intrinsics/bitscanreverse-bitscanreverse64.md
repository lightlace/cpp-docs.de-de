---
title: "_BitScanReverse, _BitScanReverse64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_BitScanReverse64"
  - "_BitScanReverse_cpp"
  - "_BitScanReverse"
  - "_BitScanReverse64_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_BitScanReverse intrinsic"
  - "BitScanReverse intrinsic"
  - "bsr instruction"
ms.assetid: 2520a207-af8b-4aad-9ae7-831abeadf376
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _BitScanReverse, _BitScanReverse64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Suchen Sie die Maskendaten vom höchstwertigen Bit \(MSB\) bis zum niedrigstwertigen Bit \(LSB\) für ein festgelegtes Bit \(1\).  
  
## Syntax  
  
```  
unsigned char _BitScanReverse(    unsigned long * Index,    unsigned long Mask ); unsigned char _BitScanReverse64(    unsigned long * Index,    unsigned __int64 Mask );  
```  
  
#### Parameter  
 \[out\] `Index`  
 Geladen mit der Bitposition des ersten festgelegten Bits \(1\), das ermittelt wurde.  
  
 \[in\] `Mask`  
 Der zu suchende 32\-Bit\- oder 64\-Bit\-Wert.  
  
## Rückgabewert  
 Ungleich null, wenn `Index` festgelegt wurde, oder null \(0\), wenn keine festgelegten Bits gefunden wurden.  
  
## Anforderungen  
  
|Systemintern|Architektur|Header|  
|------------------|-----------------|------------|  
|`_BitScanReverse`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_BitScanReverse64`|ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]||  
  
## Beispiel  
  
```  
// BitScanReverse.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(_BitScanReverse)  
  
int main()  
{  
   unsigned long mask = 0x1000;  
   unsigned long index;  
   unsigned char isNonzero;  
  
   cout << "Enter a positive integer as the mask: " << flush;  
   cin >> mask;  
   isNonzero = _BitScanReverse(&index, mask);  
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
Mask: 12 Index: 3  
```  
  
### Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)