---
title: __lzcnt16, __lzcnt, __lzcnt64
ms.date: 11/04/2016
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
ms.openlocfilehash: 7b1e499eff8c8c7de59dc6f96cb1060ce845e27d
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523454"
---
# <a name="lzcnt16-lzcnt-lzcnt64"></a>__lzcnt16, __lzcnt, __lzcnt64

**Microsoft-spezifisch**

Anzahl Nullen die Anzahl der führenden in eine 16, 32 oder 64-Bit-Ganzzahl.

## <a name="syntax"></a>Syntax

```
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

#### <a name="parameters"></a>Parameter

*Wert*<br/>
[in] Die 16, 32 oder 64-Bit-Ganzzahl ohne Vorzeichen so, dass führende Nullen.

## <a name="return-value"></a>Rückgabewert

Die Anzahl führender Nullbits in der `value` Parameter. Wenn `value` 0 (null), ist der Rückgabewert ist die Größe der eingabeoperand (16, 32 oder 64). Wenn das wichtigste Bit der `value` , ist der Rückgabewert ist 0 (null).

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__lzcnt16`|AMD: Advanced Bitmanipulation (abm wird)<br /><br /> Intel: Haswell|
|`__lzcnt`|AMD: Advanced Bitmanipulation (abm wird)<br /><br /> Intel: Haswell|
|`__lzcnt64`|AMD: Advanced Bit Manipulation (abm wird) im 64-Bit-Modus.<br /><br /> Intel: Haswell|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Jede von diesen systeminternen Funktionen generiert der `lzcnt` Anweisung.  Die Größe des Werts, der die `lzcnt` Anweisung zurückgibt, ist die Größe des Arguments identisch.  In 32-Bit-Modus sind keine 64-Bit-Allzweckregister, daher keine 64-Bit- `lzcnt`.

Um zu bestimmen, Hardware-Unterstützung für die `lzcnt` Anweisungsaufruf der `__cpuid` systeminternen Funktionen mit `InfoType=0x80000001` und überprüfen Sie wenig 5 `CPUInfo[2] (ECX)`. Dieses Bit wird 1, wenn die Anweisung unterstützt wird und 0 andernfalls. Wenn Sie Code, verwendet dieser systeminternen Funktion auf Hardware ausgeführt, die nicht unterstützt. die `lzcnt` -Anweisung, die die Ergebnisse sind unvorhersehbar.

Auf Intel-Prozessoren, die nicht unterstützen die `lzcnt` -Anweisung, die bytecodierung Anweisung ausgeführt wird, als `bsr` (-bit-Überprüfung umgekehrt). Wenn Codeportabilität relevant ist, stellen die `_BitScanReverse` systeminterne stattdessen. Weitere Informationen finden Sie unter [_BitScanReverse, _BitScanReverse64](../intrinsics/bitscanreverse-bitscanreverse64.md).

## <a name="example"></a>Beispiel

```
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

Teile dieses Inhalts sind erweiterte Micro-Geräte, Inc. Copyright 2007 Alle Rechte vorbehalten. Reproduziert werden, mit der Berechtigung, die von erweiterten Micro-Geräte, Inc.

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
