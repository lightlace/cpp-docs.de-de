---
title: Funktionen "_InterlockedCompareExchangePointer" | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _InterlockedCompareExchangePointer_HLERelease
- _InterlockedCompareExchangePointer_rel
- _InterlockedCompareExchangePointer_acq_cpp
- _InterlockedCompareExchangePointer
- _InterlockedCompareExchangePointer_cpp
- _InterlockedCompareExchangePointer_np
- _InterlockedCompareExchangePointer_rel_cpp
- _InterlockedCompareExchangePointer_HLEAcquire
- _InterlockedCompareExchangePointer_acq
- _InterlockedCompareExchangePointer_nf
dev_langs:
- C++
helpviewer_keywords:
- InterlockedCompareExchangePointer_acq intrinsic
- _InterlockedCompareExchangePointer_rel intrinsic
- _InterlockedCompareExchangePointer_acq intrinsic
- InterlockedCompareExchangePointer_rel intrinsic
- InterlockedCompareExchangePointer intrinsic
- _InterlockedCompareExchangePointer_HLERelease intrinsic
- _InterlockedCompareExchangePointer_HLEAcquire intrinsic
- _InterlockedCompareExchangePointer intrinsic
- _InterlockedCompareExchangePointer_nf intrinsic
- _InterlockedCompareExchangePointer_np intrinsic
ms.assetid: 97fde59d-2bf9-42aa-a0fe-a5b6befdd44b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8ea3976a510817e183271921c6730692e5b0b3c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45711059"
---
# <a name="interlockedcompareexchangepointer-intrinsic-functions"></a>Intrinsische Funktionen „_InterlockedCompareExchangePointer“
**Microsoft-spezifisch**  
  
 Führt einen atomarischen Vorgang durch, bei dem die `Exchange`-Adresse in der `Destination`-Adresse gespeichert wird, wenn die `Comparand`- und die `Destination`-Adresse gleich sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
void * _InterlockedCompareExchangePointer (  
   void * volatile * Destination,  
   void * Exchange,  
   void * Comparand  
);  
void * _InterlockedCompareExchangePointer_acq (  
   void * volatile * Destination,  
   void * Exchange,  
   void * Comparand  
);  
void * _InterlockedCompareExchangePointer_HLEAcquire (  
   void * volatile * Destination,  
   void * Exchange,  
   void * Comparand  
);  
void * _InterlockedCompareExchangePointer_HLERelease (  
   void * volatile * Destination,  
   void * Exchange,  
   void * Comparand  
);  
void * _InterlockedCompareExchangePointer_nf (  
   void * volatile * Destination,  
   void * Exchange,  
   void * Comparand  
);  
void * _InterlockedCompareExchangePointer_np (  
   void * volatile * Destination,  
   void * Exchange,  
   void * Comparand  
);  
long _InterlockedCompareExchangePointer_rel (  
   void * volatile * Destination,  
   void * Exchange,  
   void * Comparand  
);  
```  
  
#### <a name="parameters"></a>Parameter  
*Ziel*<br/>
[in, out] Zeiger auf einen Zeiger auf den Zielwert. Die Zeichen wird ignoriert.  
  
*Exchange*<br/>
[in] Exchange-Zeiger. Die Zeichen wird ignoriert.  
  
*Comparand-Parameter*<br/>
[in] Zeiger auf den Vergleich mit dem Ziel. Die Zeichen wird ignoriert.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert ist der Anfangswert des Ziels.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|Header|  
|---------------|------------------|------------|  
|`_InterlockedCompareExchangePointer`|X86, ARM, x64|\<intrin.h>|  
|`_InterlockedCompareExchangePointer_acq`, `_InterlockedCompareExchangePointer_nf`, `_InterlockedCompareExchangePointer_rel`|ARM|\<iiintrin.h>|  
|`_InterlockedCompareExchangePointer_HLEAcquire`, `_InterlockedCompareExchangePointer_HLERelease`|x86, x64|\<immintrin.h>|  
  
## <a name="remarks"></a>Hinweise  
 `_InterlockedCompareExchangePointer` führt einen atomarischen Vergleich der `Destination`-Adresse mit der `Comparand`-Adresse durch. Wenn die `Destination`-Adresse der `Comparand`-Adresse entspricht, wird die `Exchange`-Adresse an der durch `Destination` definierten Adresse gespeichert. Andernfalls wird kein Vorgang ausgeführt.  
  
 `_InterlockedCompareExchangePointer` bietet systeminterne compilerunterstützung für die Win32-Windows-SDK [_InterlockedCompareExchangePointer](https://msdn.microsoft.com/library/ff547863.aspx) Funktion.  
  
 Ein Beispiel zur Verwendung `_InterlockedCompareExchangePointer`, finden Sie unter [_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).  
  
 Verwenden Sie auf ARM-Plattformen die systeminternen Funktionen mit den Suffixen `_acq` und `_rel`, wenn Sie Semantiken zum Abrufen bzw. Freigeben benötigen, wie am Anfang und Ende eines kritischen Abschnitts. Die systeminternen ARM-Funktionen mit dem Suffix `_nf` („keine Umgrenzung“) fungieren nicht als Arbeitsspeicherbarriere.  
  
 Die systeminternen Funktionen mit dem Suffix `_np` („kein Vorabrufen“) verhindern, dass ein möglicher Vorabrufvorgang vom Compiler eingefügt wird.  
  
 Auf Intel-Plattformen, die Hardware Lock Elision (HLE)-Anweisungen unterstützen, enthalten die systeminternen Funktionen mit den Suffixen `_HLEAcquire` und `_HLERelease` einen Hinweis für den Prozessor, wie die Leistung durch den Wegfall der Schreibsperre in der Hardware beschleunigt werden kann. Wenn diese systeminternen Funktionen auf Plattformen aufgerufen werden, die HLE nicht unterstützen, wird der Hinweis ignoriert.  
  
 Diese Routinen sind nur als systeminterne Funktionen verfügbar.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)