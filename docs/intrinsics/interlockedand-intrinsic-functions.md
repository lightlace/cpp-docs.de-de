---
title: "Systeminterne Funktionen „_InterlockedAnd“ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedAnd_rel"
  - "_InterlockedAnd_cpp"
  - "_InterlockedAnd8_nf"
  - "_InterlockedAnd"
  - "_InterlockedAnd_HLERelease"
  - "_InterlockedAnd8_np"
  - "_InterlockedAnd16_rel"
  - "_InterlockedAnd64_np"
  - "_InterlockedAnd_np"
  - "_InterlockedAnd64_HLERelease"
  - "_InterlockedAnd64"
  - "_InterlockedAnd64_nf"
  - "_InterlockedAnd64_HLEAcquire"
  - "_InterlockedAnd16"
  - "_InterlockedAnd16_nf"
  - "_InterlockedAnd8"
  - "_InterlockedAnd_HLEAcquire"
  - "_InterlockedAnd_acq"
  - "_InterlockedAnd16_np"
  - "_InterlockedAnd64_cpp"
  - "_InterlockedAnd64_acq"
  - "_InterlockedAnd16_acq"
  - "_InterlockedAnd8_acq"
  - "_InterlockedAnd64_rel"
  - "_InterlockedAnd_nf"
  - "_InterlockedAnd8_rel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Systeminterne Funktion „_InterlockedAnd“"
  - "Systeminterne Funktion „_InterlockedAnd_acq“"
  - "Systeminterne Funktion „_InterlockedAnd_HLEAcquire“"
  - "Systeminterne Funktion „_InterlockedAnd_HLERelease“"
  - "Systeminterne Funktion „_InterlockedAnd_nf“"
  - "Systeminterne Funktion „_InterlockedAnd_np“"
  - "Systeminterne Funktion „_InterlockedAnd_rel“"
  - "Systeminterne Funktion „_InterlockedAnd16“"
  - "Systeminterne Funktion „_InterlockedAnd16_acq“"
  - "Systeminterne Funktion „_InterlockedAnd16_nf“"
  - "Systeminterne Funktion „_InterlockedAnd16_np“"
  - "Systeminterne Funktion „_InterlockedAnd16_rel“"
  - "Systeminterne Funktion „_InterlockedAnd64“"
  - "Systeminterne Funktion „_InterlockedAnd64_acq“"
  - "Systeminterne Funktion „_InterlockedAnd64_HLEAcquire“"
  - "Systeminterne Funktion „_InterlockedAnd64_HLERelease“"
  - "Systeminterne Funktion „_InterlockedAnd64_nf“"
  - "Systeminterne Funktion „_InterlockedAnd64_np“"
  - "Systeminterne Funktion „_InterlockedAnd64_rel“"
  - "Systeminterne Funktion „_InterlockedAnd8“"
  - "Systeminterne Funktion „_InterlockedAnd8_acq“"
  - "Systeminterne Funktion „_InterlockedAnd8_nf“"
  - "Systeminterne Funktion „_InterlockedAnd8_np“"
  - "Systeminterne Funktion „_InterlockedAnd8_rel“"
  - "Systeminterne Funktion „InterlockedAnd“"
  - "Systeminterne Funktion „InterlockedAnd64“"
ms.assetid: ad271dc3-42cd-47d0-9f65-30d5cfeb66fc
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# Systeminterne Funktionen „_InterlockedAnd“
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Zum Ausführen einer atomarischen bitweisen AND\-Operation für eine Variable, die von mehreren Threads genutzt wird.  
  
## Syntax  
  
```  
long _InterlockedAnd(    long volatile * value,    long mask ); long _InterlockedAnd_acq(    long volatile * value,    long mask ); long _InterlockedAnd_HLEAcquire(    long volatile * value,    long mask ); long _InterlockedAnd_HLERelease(    long volatile * value,    long mask ); long _InterlockedAnd_nf(    long volatile * value,    long mask ); long _InterlockedAnd_np(    long volatile * value,    long mask ); long _InterlockedAnd_rel(    long volatile * value,    long mask ); char _InterlockedAnd8(    char volatile * value,    char mask ); char _InterlockedAnd8_acq(    char volatile * value,    char mask ); char _InterlockedAnd8_nf(    char volatile * value,    char mask ); char _InterlockedAnd8_np(    char volatile * value,    char mask ); char _InterlockedAnd8_rel(    char volatile * value,    char mask ); short _InterlockedAnd16(    short volatile * value,    short mask ); short _InterlockedAnd16_acq(    short volatile * value,    short mask ); short _InterlockedAnd16_nf(    short volatile * value,    short mask ); short _InterlockedAnd16_np(    short volatile * value,    short mask ); short _InterlockedAnd16_rel(    short volatile * value,    short mask ); __int64 _InterlockedAnd64(    __int64 volatile* value,    __int64 mask ); __int64 _InterlockedAnd64_acq(    __int64 volatile* value,    __int64 mask );  __int64 _InterlockedAnd64_HLEAcquire(    __int64 volatile* value,    __int64 mask ); __int64 _InterlockedAnd64_HLERelease(    __int64 volatile* value,    __int64 mask ); __int64 _InterlockedAnd64_nf(    __int64 volatile* value,    __int64 mask ); __int64 _InterlockedAnd64_np(    __int64 volatile* value,    __int64 mask ); __int64 _InterlockedAnd64_rel(    __int64 volatile* value,    __int64 mask );  
```  
  
#### Parameter  
 \[in, out\] `value`  
 Ein Zeiger auf den ersten Operanden, der durch das Ergebnis ersetzt werden soll.  
  
 \[in\] `mask`  
 Der zweite Operand.  
  
## Rückgabewert  
 Der ursprüngliche Wert des ersten Operanden.  
  
## Anforderungen  
  
|Systemintern|Architektur|Header|  
|------------------|-----------------|------------|  
|`_InterlockedAnd`, `_InterlockedAnd8`, `_InterlockedAnd16`, `_InterlockedAnd64`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedAnd_acq`, `_InterlockedAnd_nf`, `_InterlockedAnd_rel`, `_InterlockedAnd8_acq`, `_InterlockedAnd8_nf`, `_InterlockedAnd8_rel`, `_InterlockedAnd16_acq`, `_InterlockedAnd16_nf`, `_InterlockedAnd16_rel`, `_InterlockedAnd64_acq`, `_InterlockedAnd64_nf`, `_InterlockedAnd64_rel`|ARM|\<intrin.h\>|  
|`_InterlockedAnd_np`, `_InterlockedAnd8_np`, `_InterlockedAnd16_np`, `_InterlockedAnd64_np`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedAnd_HLEAcquire`, `_InterlockedAnd_HLERelease`, `_InterlockedAnd64_HLEAcquire`, `_InterlockedAnd64_HLERelease`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h\>|  
  
## Hinweise  
 Die Nummer im Namen jeder Funktion gibt die Bitgröße der Argumente an.  
  
 Verwenden Sie auf ARM\-Plattformen die systeminternen Funktionen mit den Suffixen `_acq` und `_rel`, wenn Sie Semantiken zum Abrufen bzw. Freigeben benötigen, wie am Anfang und Ende eines kritischen Abschnitts.  Die systeminternen Funktionen mit dem Suffix `_nf` \(„keine Umgrenzung“\) fungieren nicht als Arbeitsspeicherbarriere.  
  
 Die systeminternen Funktionen mit dem Suffix `_np` \(„kein Vorabrufen“\) verhindern, dass ein möglicher Vorabrufvorgang vom Compiler eingefügt wird.  
  
 Auf Intel\-Plattformen, die Hardware Lock Elision \(HLE\)\-Anweisungen unterstützen, enthalten die systeminternen Funktionen mit den Suffixen `_HLEAcquire` und `_HLERelease` einen Hinweis auf den Prozessor, der die Leistung durch Beseitigen einer Schreibsperre in der Hardware beschleunigen kann.  Wenn diese systeminternen Funktionen auf Plattformen aufgerufen werden, die HLE nicht unterstützen, wird der Hinweis ignoriert.  
  
## Beispiel  
  
```  
// InterlockedAnd.cpp  
// Compile with: /Oi  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_InterlockedAnd)  
  
int main()  
{  
        long data1 = 0xFF00FF00;  
        long data2 = 0x00FFFF00;  
        long retval;  
        retval = _InterlockedAnd(&data1, data2);  
        printf_s("0x%x 0x%x 0x%x", data1, data2, retval);   
}  
```  
  
  **0xff00 0xffff00 0xff00ff00**   
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [Konflikt mit dem x86\-Compiler](../build/conflicts-with-the-x86-compiler.md)