---
title: "Systeminterne Funktionen „_InterlockedXor“ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedXor_nf"
  - "_InterlockedXor_np"
  - "_InterlockedXor64_HLERelease"
  - "_InterlockedXor8_acq"
  - "_InterlockedXor64_acq"
  - "_InterlockedXor64_rel"
  - "_InterlockedXor64_nf"
  - "_InterlockedXor_acq"
  - "_InterlockedXor16"
  - "_InterlockedXor64_np"
  - "_InterlockedXor64"
  - "_InterlockedXor_HLEAcquire"
  - "_InterlockedXor_HLERelease"
  - "_InterlockedXor_cpp"
  - "_InterlockedXor16_rel"
  - "_InterlockedXor8_rel"
  - "_InterlockedXor8"
  - "_InterlockedXor64_HLEAcquire"
  - "_InterlockedXor16_nf"
  - "_InterlockedXor16_acq"
  - "_InterlockedXor16_np"
  - "_InterlockedXor8_fn"
  - "_InterlockedXor8_np"
  - "_InterlockedXor64_cpp"
  - "_InterlockedXor_rel"
  - "_InterlockedXor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Systeminterne Funktion „_InterlockedXor“"
  - "Systeminterne Funktion „_InterlockedXor64“"
  - "Systeminterne Funktion „InterlockedXor“"
  - "Systeminterne Funktion „InterlockedXor64“"
ms.assetid: faef1796-cb5a-4430-b1e2-9d5eaf9b4a91
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# Systeminterne Funktionen „_InterlockedXor“
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Führen Sie eine atomische bitweise exklusive oder \(XOR\)\-Operation für eine Variable aus, die von mehreren Threads gemeinsam verwendet wird.  
  
## Syntax  
  
```  
long _InterlockedXor(    long volatile * Value,    long Mask ); long _InterlockedXor_acq(    long volatile * Value,    long Mask ); long _InterlockedXor_HLEAcquire(    long volatile * Value,    long Mask ); long _InterlockedXor_HLERelease(    long volatile * Value,    long Mask ); long _InterlockedXor_nf(    long volatile * Value,    long Mask ); long _InterlockedXor_np(    long volatile * Value,    long Mask ); long _InterlockedXor_rel(    long volatile * Value,    long Mask ); char _InterlockedXor8(    char volatile * Value,    char Mask ); char _InterlockedXor8_acq(    char volatile * Value,    char Mask ); char _InterlockedXor8_nf(    char volatile * Value,    char Mask ); char _InterlockedXor8_np(    char volatile * Value,    char Mask ); char _InterlockedXor8_rel(    char volatile * Value,    char Mask ); short _InterlockedXor16(    short volatile * Value,    short Mask ); short _InterlockedXor16_acq(    short volatile * Value,    short Mask ); short _InterlockedXor16_nf (    short volatile * Value,    short Mask ); short _InterlockedXor16_np (    short volatile * Value,    short Mask ); short _InterlockedXor16_rel(    short volatile * Value,    short Mask ); __int64 _InterlockedXor64(    __int64 volatile * Value,    __int64 Mask ); __int64 _InterlockedXor64_acq(    __int64 volatile * Value,    __int64 Mask );  __int64 _InterlockedXor64_HLEAcquire(    __int64 volatile * Value,    __int64 Mask ); __int64 _InterlockedXor64_HLERelease(    __int64 volatile * Value,    __int64 Mask );  __int64 _InterlockedXor64_nf(    __int64 volatile * Value,    __int64 Mask ); __int64 _InterlockedXor64_np(    __int64 volatile * Value,    __int64 Mask ); __int64 _InterlockedXor64_rel(    __int64 volatile * Value,    __int64 Mask );  
```  
  
#### Parameter  
 \[in, out\] `Value`  
 Ein Zeiger auf den ersten Operanden, der durch das Ergebnis ersetzt wird.  
  
 \[in\] `Mask`  
 Der zweite Operand.  
  
## Rückgabewert  
 Der ursprüngliche Wert des ersten Operanden.  
  
## Anforderungen  
  
|Systemintern|Architektur|Header|  
|------------------|-----------------|------------|  
|`_InterlockedXor`, `_InterlockedXor8`, `_InterlockedXor16`, `_InterlockedXor64`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedXor_acq`, `_InterlockedXor_nf`, `_InterlockedXor_rel`, `_InterlockedXor8_acq`, `_InterlockedXor8_nf`, `_InterlockedXor8_rel`, `_InterlockedXor16_acq`, `_InterlockedXor16_nf`, `_InterlockedXor16_rel`, `_InterlockedXor64_acq`, `_InterlockedXor64_nf`, `_InterlockedXor64_rel`,|ARM|\<intrin.h\>|  
|`_InterlockedXor_np`, `_InterlockedXor8_np`, `_InterlockedXor16_np`, `_InterlockedXor64_np`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedXor_HLEAcquire`, `_InterlockedXor_HLERelease`, `_InterlockedXor64_HLEAcquire`, `_InterlockedXor64_HLERelease`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h\>|  
  
## Hinweise  
 Die Nummer im Namen jeder einzelnen Funktion gibt die Bitgröße der Argumente an.  
  
 Verwenden Sie auf ARM\-Plattformen die systeminternen Funktionen mit den Suffixen `_acq` und `_rel`, wenn Sie Semantiken abrufen und freigeben müssen, beispielsweise am Anfang und Ende eines kritischen Abschnitts.  Die systeminternen ARM\-Funktionen mit dem Suffix `_nf` \(„no fence“\) dienen nicht als Arbeitsspeicherbarriere.  
  
 Die systeminternen Funktionen mit dem Suffix `_np` \(„no prefetch“\) verhindern, dass ein möglicher Vorabrufvorgang vom Compiler eingefügt wird.  
  
 Auf Intel\-Plattformen, die Hardware Lock Elision \(HLE\)\-Anweisungen unterstützen, enthalten die systeminternen Funktionen mit den Suffixen `_HLEAcquire` und `_HLERelease` einen Hinweis für den Prozessor, wie die Leistung durch den Wegfall der Schreibsperre in der Hardware beschleunigt werden kann.  Wenn diese systeminternen Funktionen auf Plattformen aufgerufen werden, die HLE nicht unterstützen, wird der Hinweis ignoriert.  
  
## Beispiel  
  
```  
// _InterLockedXor.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_InterlockedXor)  
  
int main()  
{  
        long data1 = 0xFF00FF00;  
        long data2 = 0x00FFFF00;  
        long retval;  
        retval = _InterlockedXor(&data1, data2);  
        printf_s("0x%x 0x%x 0x%x", data1, data2, retval);   
}  
```  
  
  **0xffff0000 0xffff00 0xff00ff00**   
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [Konflikt mit dem x86\-Compiler](../build/conflicts-with-the-x86-compiler.md)