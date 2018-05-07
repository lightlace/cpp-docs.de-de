---
title: _BitScanReverse _BitScanReverse64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _BitScanReverse64
- _BitScanReverse_cpp
- _BitScanReverse
- _BitScanReverse64_cpp
dev_langs:
- C++
helpviewer_keywords:
- bsr instruction
- _BitScanReverse intrinsic
- BitScanReverse intrinsic
ms.assetid: 2520a207-af8b-4aad-9ae7-831abeadf376
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 35d51f3e7eaf0daeca006ff669398c9a3727a098
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="bitscanreverse-bitscanreverse64"></a>_BitScanReverse, _BitScanReverse64
**Microsoft-spezifisch**  
  
 Suchen Sie die Maskendaten vom höchstwertigen Bit (MSB) bis zum niedrigstwertigen Bit (LSB) für ein festgelegtes Bit (1).  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned char _BitScanReverse(  
   unsigned long * Index,  
   unsigned long Mask  
);  
unsigned char _BitScanReverse64(  
   unsigned long * Index,  
   unsigned __int64 Mask  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `Index`  
 Geladen mit der Bitposition des ersten festgelegten Bits (1), das ermittelt wurde.  
  
 [in] `Mask`  
 Der zu suchende 32-Bit- oder 64-Bit-Wert.  
  
## <a name="return-value"></a>Rückgabewert  
 Ungleich null, wenn `Index` festgelegt wurde, oder null (0), wenn keine festgelegten Bits gefunden wurden.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|Header|  
|---------------|------------------|------------|  
|`_BitScanReverse`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h>|  
|`_BitScanReverse64`|ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]||  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="input"></a>Eingabe  
  
```  
12  
```  
  
## <a name="sample-output"></a>Beispielausgabe  
  
```  
Enter a positive integer as the mask:   
Mask: 12 Index: 3  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)