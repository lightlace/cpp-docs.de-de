---
title: Intrinsische Funktionen „_InterlockedIncrement“
ms.date: 11/04/2016
f1_keywords:
- _InterlockedIncrement_acq
- _InterlockedIncrement16_rel_cpp
- _InterlockedIncrement16_cpp
- _InterlockedIncrement64_rel
- _InterlockedIncrement_rel
- _InterlockedIncrement64_nf
- _InterlockedIncrement16_acq_cpp
- _InterlockedIncrement_rel_cpp
- _InterlockedIncrement64
- _InterlockedIncrement64_rel_cpp
- _InterlockedIncrement16_nf
- _InterlockedIncrement16_rel
- _InterlockedIncrement16_acq
- _InterlockedIncrement_nf
- _InterlockedIncrement_acq_cpp
- _InterlockedIncrement64_cpp
- _InterlockedIncrement64_acq_cpp
- _InterlockedIncrement
- _InterlockedIncrement_cpp
- _InterlockedIncrement64_acq
- _InterlockedIncrement16
helpviewer_keywords:
- _InterlockedIncrement64_rel intrinsic
- _InterlockedIncrement16_rel intrinsic
- InterlockedIncrement64_acq intrinsic
- _InterlockedIncrement16 intrinsic
- _InterlockedIncrement16_acq intrinsic
- _InterlockedIncrement_nf intrinsic
- _InterlockedIncrement_rel intrinsic
- _InterlockedIncrement64_nf intrinsic
- InterlockedIncrement_rel intrinsic
- InterlockedIncrement_acq intrinsic
- _InterlockedIncrement64_acq intrinsic
- _InterlockedIncrement16_nf intrinsic
- _InterlockedIncrement intrinsic
- _InterlockedIncrement64 intrinsic
- InterlockedIncrement64_rel intrinsic
- InterlockedIncrement64 intrinsic
- InterlockedIncrement16 intrinsic
- _InterlockedIncrement_acq intrinsic
- InterlockedIncrement intrinsic
ms.assetid: 37700615-f372-438b-bcef-d76e11839482
ms.openlocfilehash: aaa5918862c75c20fd6271109b3e8975709712b0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509082"
---
# <a name="interlockedincrement-intrinsic-functions"></a>Intrinsische Funktionen „_InterlockedIncrement“

**Microsoft-spezifisch**

Geben Sie die systeminterne Compiler-Unterstützung für das Win32-Windows-SDK [InterlockedIncrement](/windows/desktop/api/winbase/nf-winbase-interlockedincrement) Funktion.

## <a name="syntax"></a>Syntax

```
long _InterlockedIncrement(
   long * lpAddend
);
long _InterlockedIncrement_acq(
   long * lpAddend
);
long _InterlockedIncrement_rel(
   long * lpAddend
);
long _InterlockedIncrement_nf(
   long * lpAddend
);
short _InterlockedIncrement16(
   short * lpAddend
);
short _InterlockedIncrement16_acq(
   short * lpAddend
);
short _InterlockedIncrement16_rel(
   short * lpAddend
);
short _InterlockedIncrement16_nf (
   short * lpAddend
);
__int64 _InterlockedIncrement64(
   __int64 * lpAddend
);
__int64 _InterlockedIncrement64_acq(
   __int64 * lpAddend
);
__int64 _InterlockedIncrement64_rel(
   __int64 * lpAddend
);
__int64 _InterlockedIncrement64_nf(
   __int64 * lpAddend
);
```

#### <a name="parameters"></a>Parameter

*lpAddend*<br/>
[in, out] Zeiger auf die Variable inkrementiert werden soll.

## <a name="return-value"></a>Rückgabewert

Der Rückgabewert ist der resultierende erhöhte Wert.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|Header|
|---------------|------------------|------------|
|`_InterlockedIncrement`, `_InterlockedIncrement16`, `_InterlockedIncrement64`|X86, ARM, x64|\<intrin.h>|
|`_InterlockedIncrement_acq`, `_InterlockedIncrement_rel`, `_InterlockedIncrement_nf`, `_InterlockedIncrement16_acq`, `_InterlockedIncrement16_rel`, `_InterlockedIncrement16_nf`, `_InterlockedIncrement64_acq`, `_InterlockedIncrement64_rel`, `_InterlockedIncrement64_nf`|ARM|\<intrin.h>|

## <a name="remarks"></a>Hinweise

Es gibt mehrere Varianten von `_InterlockedIncrement`, die sich basierend auf den beinhalteten Datentypen und in Abhängigkeit davon unterscheiden, ob prozessorspezifische Semantiken zum Abrufen bzw. Freigeben verwendet werden.

Während die `_InterlockedIncrement`-Funktion mit 32-Bit-Ganzzahlwerten arbeitet, verwendet `_InterlockedIncrement16`16-Bit-Ganzzahlwerte und `_InterlockedIncrement64` 64-Bit-Ganzzahlwerte.

Verwenden Sie auf ARM-Plattformen die systeminternen Funktionen mit den Suffixen `_acq` und `_rel`, wenn Sie Semantiken abrufen und freigeben müssen, beispielsweise am Anfang und Ende eines kritischen Abschnitts. Die systeminternen Funktionen mit dem Suffix `_nf` („keine Umgrenzung“) fungieren nicht als Arbeitsspeicherbarriere.

Die Variable, auf die der `lpAddend`-Parameter zeigt, muss an einer 32-Bit-Grenze ausgerichtet sein; andernfalls schlägt diese Funktion auf x86-Multiprozessorsystemen und allen Nicht-x86-Systemen fehl. Weitere Informationen finden Sie unter [ausrichten](../cpp/align-cpp.md).

Die Win32-Funktion wird in `Wdm.h` oder `Ntddk.h` deklariert.

Diese Routinen sind nur als systeminterne Funktionen verfügbar.

## <a name="example"></a>Beispiel

Ein Beispiel zur Verwendung `_InterlockedIncrement`, finden Sie unter [_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[Konflikt mit dem x86-Compiler](../build/conflicts-with-the-x86-compiler.md)