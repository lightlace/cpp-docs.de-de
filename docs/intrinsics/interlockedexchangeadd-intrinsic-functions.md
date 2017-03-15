---
title: "Systeminterne Funktionen „_InterlockedExchangeAdd“ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedExchangeAdd64_nf"
  - "_InterlockedExchangeAdd64_rel"
  - "_InterlockedExchangeAdd16_rel"
  - "_InterlockedExchangeAdd_acq"
  - "_InterlockedExchangeAdd_nf"
  - "_InterlockedExchangeAdd_rel"
  - "_InterlockedExchangeAdd8_acq"
  - "_InterlockedExchangeAdd16_nf"
  - "_InterlockedExchangeAdd_acq_cpp"
  - "_InterlockedExchangeAdd64_acq_cpp"
  - "_InterlockedExchangeAdd16_acq"
  - "_InterlockedExchangeAdd_HLERelease"
  - "_InterlockedExchangeAdd64_cpp"
  - "_InterlockedExchangeAdd64_HLERelease"
  - "_InterlockedExchangeAdd64_acq"
  - "_InterlockedExchangeAdd8"
  - "_InterlockedExchangeAdd64"
  - "_InterlockedExchangeAdd8_nf"
  - "_InterlockedExchangeAdd16"
  - "_InterlockedExchangeAdd64_rel_cpp"
  - "_InterlockedExchangeAdd_cpp"
  - "_InterlockedExchangeAdd8_rel"
  - "_InterlockedExchangeAdd_HLEAcquire"
  - "_InterlockedExchangeAdd64_HLEAcquire"
  - "_InterlockedExchangeAdd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Systeminterne Funktion „_InterlockedExchangeAdd“"
  - "Systeminterne Funktion „_InterlockedExchangeAdd_acq“"
  - "Systeminterne Funktion „_InterlockedExchangeAdd_HLEAcquire“"
  - "Systeminterne Funktion „_InterlockedExchangeAdd_HLERelease“"
  - "Systeminterne Funktion „_InterlockedExchangeAdd_nf“"
  - "Systeminterne Funktion „_InterlockedExchangeAdd_rel“"
  - "Systeminterne Funktion „_InterlockedExchangeAdd16“"
  - "Systeminterne Funktion „_InterlockedExchangeAdd16_acq“"
  - "Systeminterne Funktion „_InterlockedExchangeAdd16_nf“"
  - "Systeminterne Funktion „_InterlockedExchangeAdd16_rel“"
  - "Systeminterne Funktion „_InterlockedExchangeAdd64“"
  - "Systeminterne Funktion „_InterlockedExchangeAdd64_acq“"
  - "Systeminterne Funktion „_InterlockedExchangeAdd64_HLEAcquire“"
  - "Systeminterne Funktion „_InterlockedExchangeAdd64_HLERelease“"
  - "Systeminterne Funktion „_InterlockedExchangeAdd64_nf“"
  - "Systeminterne Funktion „_InterlockedExchangeAdd64_rel“"
  - "Systeminterne Funktion „_InterlockedExchangeAdd8“"
  - "Systeminterne Funktion „_InterlockedExchangeAdd8_acq“"
  - "Systeminterne Funktion „_InterlockedExchangeAdd8_nf“"
  - "Systeminterne Funktion „_InterlockedExchangeAdd8_rel“"
  - "Systeminterne Funktion „InterlockedExchangeAdd“"
  - "Systeminterne Funktion „InterlockedExchangeAdd_acq“"
  - "Systeminterne Funktion „InterlockedExchangeAdd_rel“"
  - "Systeminterne Funktion „InterlockedExchangeAdd64“"
  - "Systeminterne Funktion „InterlockedExchangeAdd64_acq“"
  - "Systeminterne Funktion „InterlockedExchangeAdd64_rel“"
ms.assetid: 25809e1f-9c60-4492-9f7c-0fb59c8d13d2
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# Systeminterne Funktionen „_InterlockedExchangeAdd“
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Bereitstellung von systeminterner Compiler\-Unterstützung für die Win32\-[!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] [\_InterlockedExchangeAdd Intrinsic Functions](../intrinsics/interlockedexchangeadd-intrinsic-functions.md)\-Funktion.  
  
## Syntax  
  
```  
long _InterlockedExchangeAdd(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_acq(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_rel(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_nf(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_HLEAcquire(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_HLERelease(    long volatile * Addend,    long Value ); char _InterlockedExchangeAdd8(    char volatile * Addend,    char Value ); char _InterlockedExchangeAdd8_acq(    char volatile * Addend,    char Value ); char _InterlockedExchangeAdd8_rel(    char volatile * Addend,    char Value ); char _InterlockedExchangeAdd8_nf(    char volatile * Addend,    char Value ); short _InterlockedExchangeAdd16(    short volatile * Addend,    short Value ); short _InterlockedExchangeAdd16_acq(    short volatile * Addend,    short Value ); short _InterlockedExchangeAdd16_rel(    short volatile * Addend,    short Value ); short _InterlockedExchangeAdd16_nf(    short volatile * Addend,    short Value ); __int64 _InterlockedExchangeAdd64(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_acq(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_rel(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_nf(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_HLEAcquire(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_HLERelease(    __int64 volatile * Addend,    __int64 Value );   
```  
  
#### Parameter  
 \[in, out\] `Addend`  
 Der hinzuzufügende Wert; ersetzt durch das Ergebnis der Addition.  
  
 \[in\] `Value`  
 Der hinzuzufügende Wert.  
  
## Rückgabewert  
 Der Rückgabewert ist der Anfangswert der Variablen, auf die der `Addend`\-Parameter zeigt.  
  
## Anforderungen  
  
|Systemintern|Architektur|Header|  
|------------------|-----------------|------------|  
|`_InterlockedExchangeAdd`, `_InterlockedExchangeAdd8`, `_InterlockedExchangeAdd16`, `_InterlockedExchangeAdd64`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedExchangeAdd_acq`, `_InterlockedExchangeAdd_rel`, `_InterlockedExchangeAdd_nf`, `_InterlockedExchangeAdd8_acq`, `_InterlockedExchangeAdd8_rel`, `_InterlockedExchangeAdd8_nf`,`_InterlockedExchangeAdd16_acq`, `_InterlockedExchangeAdd16_rel`, `_InterlockedExchangeAdd16_nf`, `_InterlockedExchangeAdd64_acq`, `_InterlockedExchangeAdd64_rel`, `_InterlockedExchangeAdd64_nf`|ARM|\<intrin.h\>|  
|`_InterlockedExchangeAdd_HLEAcquire`, `_InterlockedExchangeAdd_HLERelease`, `_InterlockedExchangeAdd64_HLEAcquire`, `_InterlockedExchangeAdd64_HLErelease`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h\>|  
  
## Hinweise  
 Es gibt mehrere Varianten auf `_InterlockedExchangeAdd`, die basierend auf den zugehörigen Datentypen variieren und davon abhängen, ob prozessorspezifische Semantiken zum Abrufen oder Freigeben verwendet werden.  
  
 Während die `_InterlockedExchangeAdd`\-Funktion mit 32\-Bit\-Ganzzahlwerten arbeitet, verwendet `_InterlockedExchangeAdd8` 8\-Bit\-Ganzzahlwerte, `_InterlockedExchangeAdd16` arbeitet mit 16\-Bit\-Ganzzahlwerten und `_InterlockedExchangeAdd64` mit 64\-Bit\-Ganzzahlwerten.  
  
 Verwenden Sie auf ARM\-Plattformen die systeminternen Funktionen mit den Suffixen `_acq` und `_rel`, wenn Sie Semantiken zum Abrufen bzw. Freigeben benötigen, wie am Anfang und Ende eines kritischen Abschnitts.  Die systeminternen Funktionen mit dem Suffix `_nf` \(„keine Umgrenzung“\) fungieren nicht als Arbeitsspeicherbarriere.  
  
 Auf Intel\-Plattformen, die Hardware Lock Elision \(HLE\)\-Anweisungen unterstützen, enthalten die systeminternen Funktionen mit den Suffixen `_HLEAcquire` und `_HLERelease` einen Hinweis auf den Prozessor, der die Leistung durch Beseitigen einer Schreibsperre in der Hardware beschleunigen kann.  Wenn diese systeminternen Funktionen auf Plattformen aufgerufen werden, die HLE nicht unterstützen, wird der Hinweis ignoriert.  
  
 Diese Routinen sind nur als systeminterne Funktionen verfügbar.  Folglich sind dies systeminterne Funktionen, unabhängig davon, ob [\/Oi](../build/reference/oi-generate-intrinsic-functions.md) oder [\#pragma intrinsic](../preprocessor/intrinsic.md) verwendet wird.  Die Verwendung von [\#pragma function](../preprocessor/function-c-cpp.md) für diese systeminternen Funktionen ist nicht möglich.  
  
## Beispiel  
 Ein Beispiel zum Verwenden von `_InterlockedExchangeAdd` finden Sie unter [\_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).  
  
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [Konflikt mit dem x86\-Compiler](../build/conflicts-with-the-x86-compiler.md)