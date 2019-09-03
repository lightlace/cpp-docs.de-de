---
title: __lzcnt16, __lzcnt, __lzcnt64
ms.date: 09/02/2019
f1_keywords:
- __lzcnt64
- __lzcnt16
- __lzcnt
helpviewer_keywords:
- __lzcnt intrinsic
- lzcnt instruction
- lzcnt16 intrinsic
- lzcnt intrinsic
- __lzcnt16 intrinsic
- lzcnt64 intrinsic
- __lzcnt64 intrinsic
ms.assetid: 412113e7-052e-46e5-8bfa-d5ad72abc10e
ms.openlocfilehash: fcd801717974a230fbd19cc7802d8f6a011774f7
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221802"
---
# <a name="__lzcnt16-__lzcnt-__lzcnt64"></a>__lzcnt16, __lzcnt, __lzcnt64

**Microsoft-spezifisch**

Zählt die Anzahl führender Nullen in einer 16-, 32-oder 64-Bit-Ganzzahl.

## <a name="syntax"></a>Syntax

```C
unsigned short __lzcnt16(
   unsigned short value
);
unsigned int __lzcnt(
   unsigned int value
);
unsigned __int64 __lzcnt64(
   unsigned __int64 value
);
```

### <a name="parameters"></a>Parameter

*value*\
in Die 16-, 32-oder 64-Bit-Ganzzahl ohne Vorzeichen, die auf führende Nullen überprüft werden soll.

## <a name="return-value"></a>Rückgabewert

Die Anzahl der führenden Null Bits im `value` -Parameter. Wenn `value` 0 (null) ist, ist der Rückgabewert die Größe des Eingabe Operanden (16, 32 oder 64). Wenn das signifikanteste Bit `value` von 1 ist, ist der Rückgabewert 0 (null).

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__lzcnt16`|AMD Erweiterte Bitmanipulation (ABM)<br /><br /> Intel Haswell|
|`__lzcnt`|AMD Erweiterte Bitmanipulation (ABM)<br /><br /> Intel Haswell|
|`__lzcnt64`|AMD Erweiterte Bitmanipulation (ABM) im 64-Bit-Modus.<br /><br /> Intel Haswell|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Jede der intrinsie generiert die `lzcnt` -Anweisung.  Die Größe des von der `lzcnt` Anweisung zurückgegebenen Werts entspricht der Größe seines Arguments.  Im 32-Bit-Modus gibt es keine allgemeinen 64-Bit-Register, sodass das 64-Bit `lzcnt` nicht unterstützt wird.

Um die Hardwareunterstützung für die `lzcnt` -Anweisung zu ermitteln, müssen `InfoType=0x80000001` Sie die systeminterne Funktion `CPUInfo[2] (ECX)`mit und das `__cpuid` -Bit 5 von. Dieses Bit ist 1, wenn die Anweisung unterstützt wird, und andernfalls 0. Wenn Sie Code ausführen, der die systeminterne Funktion auf Hardware verwendet, `lzcnt` die die-Anweisung nicht unterstützt, sind die Ergebnisse unvorhersehbar.

Auf Intel-Prozessoren, die die `lzcnt` -Anweisung nicht unterstützen, wird die Anweisungs Byte Codierung als `bsr` (bitscan Reverse) ausgeführt. Wenn die Code Portabilität von Bedeutung ist, sollten Sie `_BitScanReverse` stattdessen die systeminterne Funktion verwenden. Weitere Informationen finden Sie unter [_BitScanReverse, _BitScanReverse64](../intrinsics/bitscanreverse-bitscanreverse64.md).

## <a name="example"></a>Beispiel

```cpp
// Compile this test with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

int main()
{
  unsigned short us[3] = {0, 0xFF, 0xFFFF};
  unsigned short usr;
  unsigned int   ui[4] = {0, 0xFF, 0xFFFF, 0xFFFFFFFF};
  unsigned int   uir;

  for (int i=0; i<3; i++) {
    usr = __lzcnt16(us[i]);
    cout << "__lzcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;
  }

  for (int i=0; i<4; i++) {
    uir = __lzcnt(ui[i]);
    cout << "__lzcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;
  }
}
```

```Output
__lzcnt16(0x0) = 16
__lzcnt16(0xff) = 8
__lzcnt16(0xffff) = 0
__lzcnt(0x0) = 32
__lzcnt(0xff) = 24
__lzcnt(0xffff) = 16
__lzcnt(0xffffffff) = 0
```

**Ende Microsoft-spezifisch**

Teile dieses Inhalts sind Copyright 2007 von Advanced Micro Devices, Inc. Alle Rechte vorbehalten. Mit Berechtigung von Advanced Micro Devices, Inc.

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
