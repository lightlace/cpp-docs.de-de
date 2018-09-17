---
title: Funktionen "_InterlockedExchangePointer" | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _InterlockedExchangePointer_cpp
- _InterlockedExchangePointer_rel
- _InterlockedExchangePointer_nf
- _InterlockedExchangePointer_HLERelease
- _InterlockedExchangePointer_acq
- _InterlockedExchangePointer
- _InterlockedExchangePointer_acq_cpp
- _InterlockedExchangePointer_HLEAcquire
dev_langs:
- C++
helpviewer_keywords:
- _InterlockedExchangePointer_rel intrinsic
- _InterlockedExchangePointer_HLERelease intrinsic
- _InterlockedExchangePointer intrinsic
- _InterlockedExchangePointer_nf intrinsic
- _InterlockedExchangePointer_acq intrinsic
- _InterlockedExchangePointer_HLEAcquire intrinsic
- InterlockedExchangePointer_acq intrinsic
- InterlockedExchangePointer intrinsic
ms.assetid: 0eaca0b0-d79e-406b-892d-b3b462c50bbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fa2aa8fb79a0590c437699bcf887f2a7e1c1bb21
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705015"
---
# <a name="interlockedexchangepointer-intrinsic-functions"></a>Intrinsische Funktionen „_InterlockedExchangePointer“
**Microsoft-spezifisch**  
  
 Führen Sie einen unteilbaren Austauschvorgang durch, bei dem die übergebene Adresse als zweites Argument in das erste kopiert und die ursprüngliche Adresse des ersten Arguments zurückgegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
void * _InterlockedExchangePointer(  
   void * volatile * Target,  
   void * Value  
);   
void * _InterlockedExchangePointer_acq(  
   void * volatile * Target,  
   void * Value  
);   
void * _InterlockedExchangePointer_rel(  
   void * volatile * Target,  
   void * Value  
);   
void * _InterlockedExchangePointer_nf(  
   void * volatile * Target,  
   void * Value  
);   
void * _InterlockedExchangePointer_HLEAcquire(  
   void * volatile * Target,  
   void * Value  
);   
void * _InterlockedExchangePointer_HLERelease(  
   void * volatile * Target,  
   void * Value  
);  
```  
  
#### <a name="parameters"></a>Parameter  
*Target*<br/>
[in, out] Zeiger auf den Zeiger auf den auszutauschenden Wert. Die Funktion setzt den Wert auf `Value` und gibt den vorherigen Wert zurück.  
  
*Wert*<br/>
[in] Wert, der mit dem Wert ausgetauscht werden verweist `Target`.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Funktion gibt den Anfangswert zurück, auf den `Target` zeigt.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|Header|  
|---------------|------------------|------------|  
|`_InterlockedExchangePointer`|X86, ARM, x64|\<intrin.h>|  
|`_InterlockedExchangePointer_acq`, `_InterlockedExchangePointer_rel`, `_InterlockedExchangePointer_nf`|ARM|\<intrin.h>|  
|`_InterlockedExchangePointer_HLEAcquire`, `_InterlockedExchangePointer_HLERelease`|X64 mit HLE-Unterstützung|\<immintrin.h>|  
  
 In der x86-Architektur ist `_InterlockedExchangePointer` ein Makro, das `_InterlockedExchange` aufruft.  
  
## <a name="remarks"></a>Hinweise  
 In einem 64-Bit-System sind die Parameter 64 Bits und müssen auf 64-Bit-Grenzen ausgerichtet sein. Andernfalls schlägt die Funktion fehl. In einem 32-Bit-System sind die Parameter 32 Bits und müssen auf 32-Bit-Grenzen ausgerichtet sein. Weitere Informationen finden Sie unter [ausrichten](../cpp/align-cpp.md).  
  
 Verwenden Sie auf ARM-Plattformen die systeminternen Funktionen mit den Suffixen `_acq` und `_rel`, wenn Sie Semantiken zum Abrufen bzw. Freigeben benötigen, wie am Anfang und Ende eines kritischen Abschnitts. Die systeminternen Funktionen mit dem Suffix `_nf` („keine Umgrenzung“) fungieren nicht als Arbeitsspeicherbarriere.  
  
 Auf Intel-Plattformen, die Hardware Lock Elision (HLE)-Anweisungen unterstützen, enthalten die systeminternen Funktionen mit den Suffixen `_HLEAcquire` und `_HLERelease` einen Hinweis für den Prozessor, wie die Leistung durch den Wegfall der Schreibsperre in der Hardware beschleunigt werden kann. Wenn diese systeminternen Funktionen auf Plattformen aufgerufen werden, die HLE nicht unterstützen, wird der Hinweis ignoriert.  
  
 Diese Routinen sind nur als systeminterne Funktionen verfügbar.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [Konflikt mit dem x86-Compiler](../build/conflicts-with-the-x86-compiler.md)