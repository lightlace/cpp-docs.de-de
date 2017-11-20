---
title: "_bittestandcomplement, _bittestandcomplement64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_bittestandcomplement64"
  - "_bittestandcomplement64_cpp"
  - "_bittestandcomplement_cpp"
  - "_bittestandcomplement"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_bittestandcomplement intrinsic"
  - "_bittestandcomplement64 intrinsic"
  - "btc instruction"
ms.assetid: 53fa12dd-835e-4e5d-baec-a431c8678806
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _bittestandcomplement, _bittestandcomplement64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Erzeugen Sie eine Anweisung, die Bit `b` der Adresse `a` untersucht, den aktuellen Wert zurückgibt und das Bit auf seiner Ergänzung setzt.  
  
## Syntax  
  
```  
unsigned char _bittestandcomplement(    long *a,    long b ); unsigned char _bittestandcomplement64(    __int64 *a,    __int64 b );  
```  
  
#### Parameter  
 \[in, out\] `a`  
 Ein Zeiger auf den zu untersuchenden Speicher.  
  
 \[in\] `b`  
 Die zu testende Bitposition.  
  
## Rückgabewert  
 Das Bit an der angegebenen Position.  
  
## Anforderungen  
  
|Systemintern|Architektur|  
|------------------|-----------------|  
|`_bittestandcomplement`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`_bittestandcomplement64`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Diese Routine ist nur als systeminterne Funktion verfügbar.  
  
## Beispiel  
  
```  
// bittestandcomplement.cpp  
// processor: x86, IPF, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_bittestandcomplement)  
#ifdef _M_AMD64  
#pragma intrinsic(_bittestandcomplement64)  
#endif  
  
int main()  
{  
   long i = 1;  
   __int64 i64 = 0x1I64;  
   unsigned char result;  
   printf("Initial value: %d\n", i);  
   printf("Testing bit 1\n");  
   result = _bittestandcomplement(&i, 1);  
   printf("Value changed to %d, Result: %d\n", i, result);  
#ifdef _M_AMD64  
   printf("Testing bit 0\n");  
   result = _bittestandcomplement64(&i64, 0);  
   printf("Value changed to %I64d, Result: %d\n", i64, result);  
#endif  
}  
```  
  
## Beispielausgabe  
  
```  
Initial value: 1  
Testing bit 1  
Value changed to 3, Result: 0  
Testing bit 0  
Value changed to 0, Result: 1  
```  
  
### Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)