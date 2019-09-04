---
title: __popcnt16, __popcnt, __popcnt64
ms.date: 09/02/2019
f1_keywords:
- __popcnt64
- __popcnt
- __popcnt16
helpviewer_keywords:
- popcnt instruction
- __popcnt16
- __popcnt64
- __popcnt
ms.assetid: e525b236-adc8-42df-9b9b-8b7d8c245d3b
ms.openlocfilehash: 3e5ae7f897500775671f8bd2563028874579a627
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221361"
---
# <a name="__popcnt16-__popcnt-__popcnt64"></a>__popcnt16, __popcnt, __popcnt64

**Microsoft-spezifisch**

Zählt die Anzahl der `1` Bits (Population count) in einer 16-, 32-oder 64-Bit-Ganzzahl ohne Vorzeichen.

## <a name="syntax"></a>Syntax

```C
unsigned short __popcnt16(
   unsigned short value
);
unsigned int __popcnt(
   unsigned int value
);
unsigned __int64 __popcnt64(
   unsigned __int64 value
);
```

### <a name="parameters"></a>Parameter

*value*\
in Die 16-, 32-oder 64-Bit-Ganzzahl ohne Vorzeichen, für die wir die Anzahl der Auffüllungen benötigen.

## <a name="return-value"></a>Rückgabewert

Die Anzahl der `1` Bits im *value* -Parameter.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__popcnt16`|Erweiterte Bitmanipulation|
|`__popcnt`|Erweiterte Bitmanipulation|
|`__popcnt64`|Erweiterte bitbearbeitung im 64-Bit-Modus.|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Jede der intrinsie generiert die `popcnt` -Anweisung. Im 32-Bit-Modus gibt es keine allgemeinen 64-Bit-Register, sodass 64-Bit `popcnt` nicht unterstützt wird.

Um die Hardwareunterstützung für die `popcnt` -Anweisung zu ermitteln, müssen `InfoType=0x00000001` Sie die systeminterne Funktion `CPUInfo[2] (ECX)`mit und das `__cpuid` -Bit 23 von abrufen Dieses Bit ist 1, wenn die Anweisung unterstützt wird, und andernfalls 0. Wenn Sie Code ausführen, der diese systeminternen Funktionen auf Hardware verwendet, die `popcnt` die-Anweisung nicht unterstützt, sind die Ergebnisse unvorhersehbar.

## <a name="example"></a>Beispiel

```cpp
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
    usr = __popcnt16(us[i]);
    cout << "__popcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;
  }

  for (int i=0; i<4; i++) {
    uir = __popcnt(ui[i]);
    cout << "__popcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;
  }
}
```

```Output
__popcnt16(0x0) = 0
__popcnt16(0xff) = 8
__popcnt16(0xffff) = 16
__popcnt(0x0) = 0
__popcnt(0xff) = 8
__popcnt(0xffff) = 16
__popcnt(0xffffffff) = 32
```

**Ende Microsoft-spezifisch**

Teile Copyright 2007 von Advanced Micro Devices, Inc. Alle Rechte vorbehalten. Mit Berechtigung von Advanced Micro Devices, Inc.

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
