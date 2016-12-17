---
title: "_rotr8, _rotr16"
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
  - "_rotr16"
  - "_rotr8"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_rotr16 intrinsic"
  - "_rotr8 intrinsic"
ms.assetid: dfbd2c82-82b4-427a-ad52-51609027ebff
caps.latest.revision: 17
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# _rotr8, _rotr16
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Drehen Sie die Eingabewerte nach rechts um eine bestimmte Anzahl von Bitpositionen zu dem unwichtigsten Bit.  
  
## Syntax  
  
```  
unsigned char _rotr8(     unsigned char value,     unsigned char shift  ); unsigned short _rotr16(     unsigned short value,     unsigned char shift  );  
```  
  
#### Parameter  
 \[in\] `value`  
 Der zu drehende Wert.  
  
 \[in\] `shift`  
 Die Anzahl der Bits für die Drehung.  
  
## Rückgabewert  
 Der gedrehte Wert.  
  
## Anforderungen  
  
|Systemintern|Architektur|  
|------------------|-----------------|  
|`_rotr8`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`_rotr16`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Im Gegensatz zu einem Verschiebevorgang nach rechts werden bei der Ausführung einer Drehung nach rechts die niedrigen Bits, die am unteren Ende verloren gehen, an die Positioen der höheren Bits verschoben.  
  
## Beispiel  
  
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
  
  **Drehen von 0x41 nach rechts um 0 Bit ergibt 0x41**  
**Drehen von 0x41 nach rechts um 1 Bit ergibt 0xa0**  
**Drehen von 0x41 nach rechts um 2 Bit ergibt 0x50**  
**Drehen von 0x41 nach rechts um 3 Bit ergibt 0x28**  
**Drehen von 0x41 nach rechts um 4 Bit ergibt 0x14**  
**Drehen von 0x41 nach rechts um 5 Bit ergibt 0xa**  
**Drehen von 0x41 nach rechts um 6 Bit ergibt 0x5**  
**Drehen von 0x41 nach rechts um 7 Bit ergibt 0x82**  
**Drehen von 0x12 \(unsigned short\) nach rechts um 10 Bit ergibt 0x480**   
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [\_rotl8, \_rotl16](../intrinsics/rotl8-rotl16.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)