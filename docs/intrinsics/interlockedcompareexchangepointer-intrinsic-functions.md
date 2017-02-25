---
title: "Systeminterne Funktionen „_InterlockedCompareExchangePointer“ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedCompareExchangePointer_HLERelease"
  - "_InterlockedCompareExchangePointer_rel"
  - "_InterlockedCompareExchangePointer_acq_cpp"
  - "_InterlockedCompareExchangePointer"
  - "_InterlockedCompareExchangePointer_cpp"
  - "_InterlockedCompareExchangePointer_np"
  - "_InterlockedCompareExchangePointer_rel_cpp"
  - "_InterlockedCompareExchangePointer_HLEAcquire"
  - "_InterlockedCompareExchangePointer_acq"
  - "_InterlockedCompareExchangePointer_nf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Systeminterne Funktion „_InterlockedCompareExchangePointer“"
  - "Systeminterne Funktion „_InterlockedCompareExchangePointer_acq“"
  - "Systeminterne Funktion „_InterlockedCompareExchangePointer_HLEAcquire“"
  - "Systeminterne Funktion „_InterlockedCompareExchangePointer_HLERelease“"
  - "Systeminterne Funktion „_InterlockedCompareExchangePointer_nf“"
  - "Systeminterne Funktion „_InterlockedCompareExchangePointer_np“"
  - "Systeminterne Funktion „_InterlockedCompareExchangePointer_rel“"
  - "Systeminterne Funktion „InterlockedCompareExchangePointer“"
  - "Systeminterne Funktion „InterlockedCompareExchangePointer_acq“"
  - "Systeminterne Funktion „InterlockedCompareExchangePointer_rel“"
ms.assetid: 97fde59d-2bf9-42aa-a0fe-a5b6befdd44b
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# Systeminterne Funktionen „_InterlockedCompareExchangePointer“
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Führt einen atomarischen Vorgang durch, bei dem die `Exchange`\-Adresse in der `Destination`\-Adresse gespeichert wird, wenn die `Comparand`\- und die `Destination`\-Adresse gleich sind.  
  
## Syntax  
  
```  
void * _InterlockedCompareExchangePointer (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_acq (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_HLEAcquire (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_HLERelease (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_nf (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_np (    void * volatile * Destination,    void * Exchange,    void * Comparand ); long _InterlockedCompareExchangePointer_rel (    void * volatile * Destination,    void * Exchange,    void * Comparand );  
```  
  
#### Parameter  
 \[in, out\] `Destination`  
 Zeiger auf einen Zeiger auf den Zielwert.  Das Zeichen wird ignoriert.  
  
 \[in\] `Exchange`  
 Exchange\-Zeiger.  Das Zeichen wird ignoriert.  
  
 \[in\] `Comparand`  
 Zeiger zum Vergleich mit dem Ziel.  Das Zeichen wird ignoriert.  
  
## Rückgabewert  
 Der Rückgabewert ist der Anfangswert des Ziels.  
  
## Anforderungen  
  
|Systemintern|Architektur|Header|  
|------------------|-----------------|------------|  
|`_InterlockedCompareExchangePointer`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedCompareExchangePointer_acq`, `_InterlockedCompareExchangePointer_nf`, `_InterlockedCompareExchangePointer_rel`|ARM|\<iiintrin.h\>|  
|`_InterlockedCompareExchangePointer_HLEAcquire`, `_InterlockedCompareExchangePointer_HLERelease`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h\>|  
  
## Hinweise  
 `_InterlockedCompareExchangePointer` führt einen atomarischen Vergleich der `Destination`\-Adresse mit der `Comparand`\-Adresse durch.  Wenn die `Destination`\-Adresse der `Comparand`\-Adresse entspricht, wird die `Exchange`\-Adresse an der durch `Destination` definierten Adresse gespeichert.  Andernfalls wird kein Vorgang ausgeführt.  
  
 `_InterlockedCompareExchangePointer` bietet systeminterne Compiler\-Unterstützung für die Win32\-Funktion [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)][\_InterlockedCompareExchangePointer](http://msdn.microsoft.com/library/ff547863.aspx).  
  
 Ein Beispiel für die Verwendung von `_InterlockedCompareExchangePointer` finden Sie unter [\_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).  
  
 Verwenden Sie auf ARM\-Plattformen die systeminternen Funktionen mit den Suffixen `_acq` und `_rel`, wenn Sie Semantiken zum Abrufen bzw. Freigeben benötigen, wie am Anfang und Ende eines kritischen Abschnitts.  Die systeminternen ARM\-Funktionen mit dem Suffix `_nf` \(„keine Umgrenzung“\) fungieren nicht als Arbeitsspeicherbarriere.  
  
 Die systeminternen Funktionen mit dem Suffix `_np` \(„kein Vorabrufen“\) verhindern, dass ein möglicher Vorabrufvorgang vom Compiler eingefügt wird.  
  
 Auf Intel\-Plattformen, die Hardware Lock Elision \(HLE\)\-Anweisungen unterstützen, enthalten die systeminternen Funktionen mit den Suffixen `_HLEAcquire` und `_HLERelease` einen Hinweis auf den Prozessor, der die Leistung durch Beseitigen einer Schreibsperre in der Hardware beschleunigen kann.  Wenn diese systeminternen Funktionen auf Plattformen aufgerufen werden, die HLE nicht unterstützen, wird der Hinweis ignoriert.  
  
 Diese Routinen sind nur als systeminterne Funktionen verfügbar.  
  
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)