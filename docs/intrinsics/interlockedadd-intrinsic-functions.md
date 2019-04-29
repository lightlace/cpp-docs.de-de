---
title: Intrinsische Funktionen „_InterlockedAdd“
ms.date: 12/17/2018
f1_keywords:
- _InterlockedAdd64_acq_cpp
- _InterlockedAdd64_acq
- _InterlockedAdd_acq
- _InterlockedAdd_nf
- _InterlockedAdd64_rel
- _InterlockedAdd64
- _InterlockedAdd_cpp
- _InterlockedAdd_rel_cpp
- _InterlockedAdd_rel
- _InterlockedAdd64_rel_cpp
- _InterlockedAdd64_cpp
- _InterlockedAdd_acq_cpp
- _InterlockedAdd64_nf
- _InterlockedAdd
helpviewer_keywords:
- _InterlockedAdd_nf intrinsic
- _InterlockedAdd_rel intrinsic
- _InterlockedAdd intrinsic
- _InterlockedAdd64 intrinsic
- _InterlockedAdd64_acq intrinsic
- _InterlockedAdd64_nf intrinsic
- _InterlockedAdd_acq intrinsic
- _InterlockedAdd64_rel intrinsic
ms.assetid: 3d319603-ea9c-4fdd-ae61-e52430ccc3b1
ms.openlocfilehash: 348e936bb05796e36ae45095f25b943076cec464
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349516"
---
# <a name="interlockedadd-intrinsic-functions"></a>Intrinsische Funktionen „_InterlockedAdd“

**Microsoft-spezifisch**

Diese Funktionen führen atomarische Addition aus, um sicherzustellen, dass der Vorgang erfolgreich abgeschlossen ist, wenn mehr als einem Thread auf eine freigegebene Variable zugreifen.

## <a name="syntax"></a>Syntax

```
long _InterlockedAdd(
   long volatile * Addend,
   long Value
);
long _InterlockedAdd_acq(
   long volatile * Addend,
   long Value
);
long _InterlockedAdd_nf(
   long volatile * Addend,
   long Value
);
long _InterlockedAdd_rel(
   long volatile * Addend,
   long Value
);
__int64 _InterlockedAdd64(
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedAdd64_acq(
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedAdd64_nf (
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedAdd64_rel(
   __int64 volatile * Addend,
   __int64 Value
);
```

#### <a name="parameters"></a>Parameter

*Addend*<br/>
[in, out] Zeiger auf die ganze Zahl, die hinzugefügt werden; ersetzt durch das Ergebnis der Addition.

*Wert*<br/>
[in] Der hinzuzufügende Wert.

## <a name="return-value"></a>Rückgabewert

Beide Funktionen geben das Ergebnis der Addition zurück.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_InterlockedAdd`|ARM|
|`_InterlockedAdd_acq`|ARM|
|`_InterlockedAdd_nf`|ARM|
|`_InterlockedAdd_rel`|ARM|
|`_InterlockedAdd64`|ARM|
|`_InterlockedAdd64_acq`|ARM|
|`_InterlockedAdd64_nf`|ARM|
|`_InterlockedAdd64_rel`|ARM|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Die Versionen dieser Funktionen mit den Suffixen `_acq` oder `_rel` führen eine ineinander greifende Addition gemäß der Semantiken zum Abrufen oder Freigeben durch. *Acquire-Semantik* bedeutet, dass das Ergebnis des Vorgangs für alle Threads und Prozessoren sichtbar gemacht wird, bevor alle späteren speicherlese- und-Schreibvorgänge. „Acquire“ ist bei der Eingabe eines kritischen Abschnitts nützlich. *Release-Semantik* bedeutet, die alle speicherlese- und-Schreibvorgänge für alle Threads und Prozessoren sichtbar gemacht werden, bevor das Ergebnis des Vorgangs sichtbar, selbst gemacht wird erzwungen werden. „Release“ ist beim Verlassen eines kritischen Abschnitts nützlich. Die systeminternen Funktionen mit einer `_nf` ("no Fence")-Suffix nicht als Arbeitsspeicherbarriere fungieren.

Diese Routinen sind nur als systeminterne Funktionen verfügbar.

## <a name="example"></a>Beispiel

```cpp
// interlockedadd.cpp
// Compile with: /Oi /EHsc
// processor: ARM
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_InterlockedAdd)

int main()
{
        long data1 = 0xFF00FF00;
        long data2 = 0x00FF0000;
        long retval;
        retval = _InterlockedAdd(&data1, data2);
        printf("0x%x 0x%x 0x%x", data1, data2, retval);
}
```

## <a name="output"></a>Output

```Output
0xffffff00 0xff0000 0xffffff00
```

## <a name="example"></a>Beispiel

```cpp
// interlockedadd64.cpp
// compile with: /Oi /EHsc
// processor: ARM
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(_InterlockedAdd64)

int main()
{
        __int64 data1 = 0x0000FF0000000000;
        __int64 data2 = 0x00FF0000FFFFFFFF;
        __int64 retval;
        cout << hex << data1 << " + " << data2 << " = " ;
        retval = _InterlockedAdd64(&data1, data2);
        cout << data1 << endl;
        cout << "Return value: " << retval << endl;
}
```

## <a name="output"></a>Output

```Output
ff0000000000 + ff0000ffffffff = ffff00ffffffff
Return value: ffff00ffffffff
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[Konflikt mit dem x86-Compiler](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)