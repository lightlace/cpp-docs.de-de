---
title: _bittest _bittest64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _bittest64
- _bittest_cpp
- _bittest64_cpp
- _bittest
dev_langs: C++
helpviewer_keywords:
- _bittest intrinsic
- _bittest64 intrinsic
- bt instruction
ms.assetid: 15e62afb-abea-4ee7-a6b1-13efa2034937
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5f4a3606e21bbd695e0803acfcb98270dfbb48a5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="bittest-bittest64"></a>_bittest, _bittest64
**Microsoft-spezifisch**  
  
Generiert die `bt`-Anweisung, die das Bit an Position `b` der Adresse `a` untersucht, und gibt den Wert dieses Bits zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned char _bittest(  
   long const *a,  
   long b  
);  
unsigned char _bittest64(  
   __int64 const *a,  
   __int64 b  
);  
```  
  
### <a name="parameters"></a>Parameter  
[in] `a`  
Ein Zeiger auf den zu untersuchenden Speicher.  
  
[in] `b`  
Die zu testende Bitposition.  
  
### <a name="return-value"></a>Rückgabewert  
Das Bit an der angegebenen Position.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|Header|  
|---------------|------------------|------------|  
|`_bittest`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<INTRIN.h >|  
|`_bittest64`|ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<INTRIN.h >|  
  
## <a name="remarks"></a>Hinweise  
Diese Routine ist nur als systeminterne Funktion verfügbar.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// bittest.cpp  
// processor: x86, ARM, x64  
  
#include <stdio.h>  
#include <intrin.h>  
  
long num = 78002;  
  
int main()  
{  
    unsigned char bits[32];  
    long nBit;  
  
    printf_s("Number: %d\n", num);  
  
    for (nBit = 0; nBit < 31; nBit++)  
    {  
        bits[nBit] = _bittest(&num, nBit);  
    }  
  
    printf_s("Binary representation:\n");  
    while (nBit--)  
    {  
        if (bits[nBit])  
            printf_s("1");  
        else  
            printf_s("0");  
    }  
}  
```  
  
```Output  
Number: 78002  
Binary representation:  
0000000000000010011000010110010  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)