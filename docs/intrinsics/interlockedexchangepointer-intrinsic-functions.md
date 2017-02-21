---
title: "Systeminterne Funktionen „_InterlockedExchangePointer“ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedExchangePointer_cpp"
  - "_InterlockedExchangePointer_rel"
  - "_InterlockedExchangePointer_nf"
  - "_InterlockedExchangePointer_HLERelease"
  - "_InterlockedExchangePointer_acq"
  - "_InterlockedExchangePointer"
  - "_InterlockedExchangePointer_acq_cpp"
  - "_InterlockedExchangePointer_HLEAcquire"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Systeminterne Funktion „_InterlockedExchangePointer“"
  - "Systeminterne Funktion „_InterlockedExchangePointer_acq“"
  - "Systeminterne Funktion „_InterlockedExchangePointer_HLEAcquire“"
  - "Systeminterne Funktion „_InterlockedExchangePointer_HLERelease“"
  - "Systeminterne Funktion „_InterlockedExchangePointer_nf“"
  - "Systeminterne Funktion „_InterlockedExchangePointer_rel“"
  - "Systeminterne Funktion „InterlockedExchangePointer“"
  - "Systeminterne Funktion „InterlockedExchangePointer_acq“"
ms.assetid: 0eaca0b0-d79e-406b-892d-b3b462c50bbb
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# Systeminterne Funktionen „_InterlockedExchangePointer“
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Führen Sie einen unteilbaren Austauschvorgang durch, bei dem die übergebene Adresse als zweites Argument in das erste kopiert und die ursprüngliche Adresse des ersten Arguments zurückgegeben wird.  
  
## Syntax  
  
```  
void * _InterlockedExchangePointer(    void * volatile * Target,    void * Value );  void * _InterlockedExchangePointer_acq(    void * volatile * Target,    void * Value );  void * _InterlockedExchangePointer_rel(    void * volatile * Target,    void * Value );  void * _InterlockedExchangePointer_nf(    void * volatile * Target,    void * Value );  void * _InterlockedExchangePointer_HLEAcquire(    void * volatile * Target,    void * Value );  void * _InterlockedExchangePointer_HLERelease(    void * volatile * Target,    void * Value );  
```  
  
#### Parameter  
 \[in, out\]`Target`  
 Zeiger auf den Zeiger auf den auszutauschenden Wert.  Die Funktion setzt den Wert auf `Value` und gibt den vorherigen Wert zurück.  
  
 \[in\] `Value`  
 Wert wird mit dem Wert ausgetauscht, auf den `Target` zeigt.  
  
## Rückgabewert  
 Die Funktion gibt den Anfangswert zurück, auf den `Target` zeigt.  
  
## Anforderungen  
  
|Systemintern|Architektur|Header|  
|------------------|-----------------|------------|  
|`_InterlockedExchangePointer`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedExchangePointer_acq`, `_InterlockedExchangePointer_rel`, `_InterlockedExchangePointer_nf`|ARM|\<intrin.h\>|  
|`_InterlockedExchangePointer_HLEAcquire`, `_InterlockedExchangePointer_HLERelease`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] mit HLE\-Unterstützung|\<immintrin.h\>|  
  
 In der x86\-Architektur ist `_InterlockedExchangePointer` ein Makro, das `_InterlockedExchange` aufruft.  
  
## Hinweise  
 In einem 64\-Bit\-System sind die Parameter 64 Bits und müssen auf 64\-Bit\-Grenzen ausgerichtet sein. Andernfalls schlägt die Funktion fehl.  In einem 32\-Bit\-System sind die Parameter 32 Bits und müssen auf 32\-Bit\-Grenzen ausgerichtet sein.  Weitere Informationen finden Sie unter [ausrichten](../cpp/align-cpp.md).  
  
 Verwenden Sie auf ARM\-Plattformen die systeminternen Funktionen mit den Suffixen `_acq` und `_rel`, wenn Sie Semantiken zum Abrufen bzw. Freigeben benötigen, wie am Anfang und Ende eines kritischen Abschnitts.  Die systeminternen Funktionen mit dem Suffix `_nf` \(„keine Umgrenzung“\) fungieren nicht als Arbeitsspeicherbarriere.  
  
 Auf Intel\-Plattformen, die Hardware Lock Elision \(HLE\)\-Anweisungen unterstützen, enthalten die systeminternen Funktionen mit den Suffixen `_HLEAcquire` und `_HLERelease` einen Hinweis auf den Prozessor, der die Leistung durch Beseitigen einer Schreibsperre in der Hardware beschleunigen kann.  Wenn diese systeminternen Funktionen auf Plattformen aufgerufen werden, die HLE nicht unterstützen, wird der Hinweis ignoriert.  
  
 Diese Routinen sind nur als systeminterne Funktionen verfügbar.  
  
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [Konflikt mit dem x86\-Compiler](../build/conflicts-with-the-x86-compiler.md)