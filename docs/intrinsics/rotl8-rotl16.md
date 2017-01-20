---
title: "_rotl8, _rotl16"
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
  - "_rotl8"
  - "_rotl16"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_rotl16 intrinsic"
  - "_rotl8 intrinsic"
ms.assetid: 8c519ab6-aef9-4f07-a387-daee8408368f
caps.latest.revision: 17
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# _rotl8, _rotl16
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Drehen Sie die Eingabewerte um eine angegebene Anzahl Bitpositionen nach links auf das höchstwertige Bit \(MSB\).  
  
## Syntax  
  
```  
unsigned char _rotl8(     unsigned char value,     unsigned char shift  ); unsigned short _rotl16(     unsigned short value,     unsigned char shift  );  
```  
  
#### Parameter  
 \[in\] `value`  
 Der zu drehende Wert.  
  
 \[in\] `shift`  
 Die Anzahl der zu drehenden Bits.  
  
## Rückgabewert  
 Der gedrehte Wert.  
  
## Anforderungen  
  
|Systemintern|Architektur|  
|------------------|-----------------|  
|`_rotl8`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`_rotl16`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Im Gegensatz zu Verschiebevorgängen nach links werden bei einem Drehvorgang nach links die hochwertigen Bits, die aus dem oberen Bereich herausfallen, an die Bitpositionen mit dem niedrigsten Wert verschoben.  
  
## Beispiel  
  
```  
// rotl.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_rotl8, _rotl16)  
  
int main()  
{  
    unsigned char c = 'A', c1, c2;  
  
    for (int i = 0; i < 8; i++)  
    {  
       printf_s("Rotating 0x%x left by %d bits gives 0x%x\n", c,  
               i, _rotl8(c, i));  
    }  
  
    unsigned short s = 0x12;  
    int nBit = 10;  
  
    printf_s("Rotating unsigned short 0x%x left by %d bits gives 0x%x\n",  
            s, nBit, _rotl16(s, nBit));  
}  
```  
  
  **Drehen von 0x41 nach links um 0 Bits ergibt 0x41**  
**Drehen von 0x41 nach links um 1 Bit ergibt 0x82**  
**Drehen von 0x41 nach links um 2 Bits ergibt 0x5**  
**Drehen von 0x41 nach links um 3 Bits ergibt 0xa**  
**Drehen von 0x41 nach links um 4 Bits ergibt 0x14**  
**Drehen von 0x41 nach links um 5 Bits ergibt 0x28**  
**Drehen von 0x41 nach links um 6 Bits ergibt 0x50**  
**Drehen von 0x41 nach links um 7 Bits ergibt 0xa0**  
**Drehen der kurzen Ganzzahl ohne Vorzeichen 0x12 nach links um 10 Bits ergibt 0x4800**   
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [\_rotr8, \_rotr16](../intrinsics/rotr8-rotr16.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)