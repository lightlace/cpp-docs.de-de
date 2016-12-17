---
title: "Systeminterne Funktionen „_InterlockedOr“"
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
  - "_InterlockedOr8_nf"
  - "_InterlockedOr_HLEAcquire"
  - "_InterlockedOr16_nf"
  - "_InterlockedOr64"
  - "_InterlockedOr8_np"
  - "_InterlockedOr64_cpp"
  - "_InterlockedOr8_acq"
  - "_InterlockedOr_nf"
  - "_InterlockedOr64_acq"
  - "_InterlockedOr_np"
  - "_InterlockedOr8"
  - "_InterlockedOr"
  - "_InterlockedOr64_np"
  - "_InterlockedOr_acq"
  - "_InterlockedOr64_HLERelease"
  - "_InterlockedOr16_np"
  - "_InterlockedOr_cpp"
  - "_InterlockedOr8_rel"
  - "_InterlockedOr64_rel"
  - "_InterlockedOr16_acq"
  - "_InterlockedOr_rel"
  - "_InterlockedOr16_rel"
  - "_InterlockedOr_HLERelease"
  - "_InterlockedOr64_HLEAcquire"
  - "_InterlockedOr16"
  - "_InterlockedOr64_nf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Systeminterne Funktion „_InterlockedOr“"
  - "Systeminterne Funktion „_InterlockedOr_acq“"
  - "Systeminterne Funktion „_InterlockedOr_HLEAcquire“"
  - "Systeminterne Funktion „_InterlockedOr_HLERelease“"
  - "Systeminterne Funktion „_InterlockedOr_nf“"
  - "Systeminterne Funktion „_InterlockedOr_np“"
  - "Systeminterne Funktion „_InterlockedOr_rel“"
  - "Systeminterne Funktion „_InterlockedOr16“"
  - "Systeminterne Funktion „_InterlockedOr16_acq“"
  - "Systeminterne Funktion „_InterlockedOr16_nf“"
  - "Systeminterne Funktion „_InterlockedOr16_np“"
  - "Systeminterne Funktion „_InterlockedOr16_rel“"
  - "Systeminterne Funktion „_InterlockedOr64“"
  - "Systeminterne Funktion „_InterlockedOr64_acq“"
  - "Systeminterne Funktion „_InterlockedOr64_HLEAcquire“"
  - "Systeminterne Funktion „_InterlockedOr64_HLERelease“"
  - "Systeminterne Funktion „_InterlockedOr64_nf“"
  - "Systeminterne Funktion „_InterlockedOr64_np“"
  - "Systeminterne Funktion „_InterlockedOr64_rel“"
  - "Systeminterne Funktion „_InterlockedOr8“"
  - "Systeminterne Funktion „_InterlockedOr8_acq“"
  - "Systeminterne Funktion „_InterlockedOr8_nf“"
  - "Systeminterne Funktion „_InterlockedOr8_np“"
  - "Systeminterne Funktion „_InterlockedOr8_rel“"
  - "Systeminterne Funktion „InterlockedOr“"
  - "Systeminterne Funktion „InterlockedOr64“"
ms.assetid: 5f265240-7af8-44b7-b952-19f3a9c56186
caps.latest.revision: 19
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# Systeminterne Funktionen „_InterlockedOr“
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Führen Sie eine atomarische bitweise OR\-Operation für eine Variable durch, die von mehreren Threads genutzt wird.  
  
## Syntax  
  
```  
long _InterlockedOr(    long volatile * Value,    long Mask ); long _InterlockedOr_acq(    long volatile * Value,    long Mask ); long _InterlockedOr_HLEAcquire(    long volatile * Value,    long Mask ); long _InterlockedOr_HLERelease(    long volatile * Value,    long Mask ); long _InterlockedOr_nf(    long volatile * Value,    long Mask ); long _InterlockedOr_np(    long volatile * Value,    long Mask ); long _InterlockedOr_rel(    long volatile * Value,    long Mask ); char _InterlockedOr8(    char volatile * Value,    long Mask ); char _InterlockedOr8_acq(    char volatile * Value,    char Mask ); char _InterlockedOr8_nf(    char volatile * Value,    char Mask ); char _InterlockedOr8_np(    char volatile * Value,    char Mask ); char _InterlockedOr8_rel(    char volatile * Value,    char Mask ); short _InterlockedOr16(    short volatile * Value,    short Mask ); short _InterlockedOr16_acq(    short volatile * Value,    short Mask ); short _InterlockedOr16_nf(    short volatile * Value,    short Mask ); short _InterlockedOr16_np(    short volatile * Value,    short Mask ); short _InterlockedOr16_rel(    short volatile * Value,    short Mask ); __int64 _InterlockedOr64(    __int64 volatile * Value,    __int64 Mask ); __int64 _InterlockedOr64_acq(    __int64 volatile * Value,    __int64 Mask );  __int64 _InterlockedOr64_HLEAcquire(    __int64 volatile * Value,    __int64 Mask ); __int64 _InterlockedOr64_HLERelease(    __int64 volatile * Value,    __int64 Mask );  __int64 _InterlockedOr64_nf(    __int64 volatile * Value,    __int64 Mask ); __int64 _InterlockedOr64_np(    __int64 volatile * Value,    __int64 Mask ); __int64 _InterlockedOr64_rel(    __int64 volatile * Value,    __int64 Mask );  
```  
  
#### Parameter  
 \[in, out\] `Value`  
 Ein Zeiger auf den ersten Operanden, der durch das Ergebnis ersetzt werden soll.  
  
 \[in\] `Mask`  
 Der zweite Operand.  
  
## Rückgabewert  
 Der ursprüngliche Wert, auf den der erste Parameter zeigt.  
  
## Anforderungen  
  
|Systemintern|Architektur|Header|  
|------------------|-----------------|------------|  
|`_InterlockedOr`, `_InterlockedOr8`, `_InterlockedOr16`, `_InterlockedOr64`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedOr_acq`, `_InterlockedOr_nf`, `_InterlockedOr_rel`, `_InterlockedOr8_acq`, `_InterlockedOr8_nf`, `_InterlockedOr8_rel`, `_InterlockedOr16_acq`, `_InterlockedOr16_nf`, `_InterlockedOr16_rel`, `_InterlockedOr64_acq`, `_InterlockedOr64_nf`, `_InterlockedOr64_rel`|ARM|\<intrin.h\>|  
|`_InterlockedOr_np`, `_InterlockedOr8_np`, `_InterlockedOr16_np`, `_InterlockedOr64_np`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedOr_HLEAcquire`, `_InterlockedOr_HLERelease`, `_InterlockedOr64_HLEAcquire`, `_InterlockedOr64_HLERelease`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h\>|  
  
## Hinweise  
 Die Nummer im Namen jeder Funktion gibt die Bitgröße der Argumente an.  
  
 Verwenden Sie auf ARM\-Plattformen die systeminternen Funktionen mit den Suffixen `_acq` und `_rel`, wenn Sie Semantiken zum Abrufen bzw. Freigeben benötigen, wie am Anfang und Ende eines kritischen Abschnitts.  Die systeminternen ARM\-Funktionen mit dem Suffix `_nf` \(„keine Umgrenzung“\) fungieren nicht als Arbeitsspeicherbarriere.  
  
 Die systeminternen Funktionen mit dem Suffix `_np` \(„kein Vorabrufen“\) verhindern, dass ein möglicher Vorabrufvorgang vom Compiler eingefügt wird.  
  
 Auf Intel\-Plattformen, die Hardware Lock Elision \(HLE\)\-Anweisungen unterstützen, enthalten die systeminternen Funktionen mit den Suffixen `_HLEAcquire` und `_HLERelease` einen Hinweis auf den Prozessor, der die Leistung durch Beseitigen einer Schreibsperre in der Hardware beschleunigen kann.  Wenn diese systeminternen Funktionen auf Plattformen aufgerufen werden, die HLE nicht unterstützen, wird der Hinweis ignoriert.  
  
## Beispiel  
  
```  
// _InterlockedOr.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_InterlockedOr)  
  
int main()  
{  
        long data1 = 0xFF00FF00;  
        long data2 = 0x00FFFF00;  
        long retval;  
        retval = _InterlockedOr(&data1, data2);  
        printf_s("0x%x 0x%x 0x%x", data1, data2, retval);   
}  
```  
  
  **0xffffff00 0xffff00 0xff00ff00**   
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [Konflikt mit dem x86\-Compiler](../build/conflicts-with-the-x86-compiler.md)