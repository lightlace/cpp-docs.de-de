---
title: _rotr8 _rotr16 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- _rotr16
- _rotr8
dev_langs:
- C++
helpviewer_keywords:
- _rotr8 intrinsic
- _rotr16 intrinsic
ms.assetid: dfbd2c82-82b4-427a-ad52-51609027ebff
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 726cee6f898af306b8d0743344228e7d11d344f1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="rotr8-rotr16"></a>_rotr8, _rotr16
**Microsoft-spezifisch**  
  
 Drehen Sie die Eingabewerte nach rechts um eine bestimmte Anzahl von Bitpositionen zu dem unwichtigsten Bit.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned char _rotr8(   
   unsigned char value,   
   unsigned char shift   
);  
unsigned short _rotr16(   
   unsigned short value,   
   unsigned char shift   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `value`  
 Der zu drehende Wert.  
  
 [in] `shift`  
 Die Anzahl der Bits für die Drehung.  
  
## <a name="return-value"></a>Rückgabewert  
 Der gedrehte Wert.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`_rotr8`|X86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`_rotr16`|X86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Im Gegensatz zu einem Verschiebevorgang nach rechts werden bei der Ausführung einer Drehung nach rechts die niedrigen Bits, die am unteren Ende verloren gehen, an die Positioen der höheren Bits verschoben.  
  
## <a name="example"></a>Beispiel  
  
```  
// rotr.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_rotr8, _rotr16)  
  
int main()  
{  
    unsigned char c = 'A', c1, c2;  
  
    for (int i = 0; i < 8; i++)  
    {  
       printf_s("Rotating 0x%x right by %d bits gives 0x%x\n", c,  
                i, _rotr8(c, i));  
    }  
  
    unsigned short s = 0x12;  
    int nBit = 10;  
  
    printf_s("Rotating unsigned short 0x%x right by %d bits "  
             "gives 0x%x\n",  
            s, nBit, _rotr16(s, nBit));  
}  
```  
  
```Output  
Rotating 0x41 right by 0 bits gives 0x41  
Rotating 0x41 right by 1 bits gives 0xa0  
Rotating 0x41 right by 2 bits gives 0x50  
Rotating 0x41 right by 3 bits gives 0x28  
Rotating 0x41 right by 4 bits gives 0x14  
Rotating 0x41 right by 5 bits gives 0xa  
Rotating 0x41 right by 6 bits gives 0x5  
Rotating 0x41 right by 7 bits gives 0x82  
Rotating unsigned short 0x12 right by 10 bits gives 0x480  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_rotl8, _rotl16](../intrinsics/rotl8-rotl16.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)