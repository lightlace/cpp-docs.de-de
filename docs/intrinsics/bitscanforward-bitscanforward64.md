---
title: _BitScanForward, _BitScanForward64
ms.date: 11/04/2016
f1_keywords:
- _BitScanForward
- _BitScanForward_cpp
- _BitScanForward64_cpp
- _BitScanForward64
helpviewer_keywords:
- _BitScanForward intrinsic
- bsf instruction
- BitScanForward intrinsic
ms.assetid: 405e60fb-0815-42a7-9b02-6fc035122203
ms.openlocfilehash: 8b09aeee485611ddd20d51b4c1e36ec98c03c26e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62264217"
---
# <a name="bitscanforward-bitscanforward64"></a>_BitScanForward, _BitScanForward64

**Microsoft-spezifisch**

Suchen Sie die Maskendaten vom niedrigstwertigen Bit (LSB) bis zum höchstwertigen Bit (MSB) für ein festgelegtes Bit (1).

## <a name="syntax"></a>Syntax

```
unsigned char _BitScanForward(
   unsigned long * Index,
   unsigned long Mask
);
unsigned char _BitScanForward64(
   unsigned long * Index,
   unsigned __int64 Mask
);
```

#### <a name="parameters"></a>Parameter

*Index*<br/>
[out] Geladen mit der Bitposition des ersten festgelegten Bits (1) wurde gefunden.

*Maske*<br/>
[in] Der 32-Bit oder 64-Bit-Wert zu suchen.

## <a name="return-value"></a>Rückgabewert

0, wenn die Maske null ist; andernfalls ungleich null.

## <a name="remarks"></a>Hinweise

Wenn ein festgelegtes Bit gefunden wird, wird die Bitposition des ersten festgelegten gefundenen Bits in den ersten Parameter zurückgegeben. Wenn kein festgelegtes Bit gefunden wird, wird 0 zurückgegeben; andernfalls wird 1 zurückgegeben.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_BitScanForward`|x86, ARM, x64|
|`_BitScanForward64`|ARM, x64|

**Headerdatei** \<intrin.h >

## <a name="example"></a>Beispiel

```
// BitScanForward.cpp
// compile with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(_BitScanForward)

int main()
{
   unsigned long mask = 0x1000;
   unsigned long index;
   unsigned char isNonzero;

   cout << "Enter a positive integer as the mask: " << flush;
   cin >> mask;
   isNonzero = _BitScanForward(&index, mask);
   if (isNonzero)
   {
      cout << "Mask: " << mask << " Index: " << index << endl;
   }
   else
   {
      cout << "No set bits found.  Mask is zero." << endl;
   }
}
```

## <a name="input"></a>Eingabe

```
12
```

## <a name="sample-output"></a>Beispielausgabe

```
Enter a positive integer as the mask:
Mask: 12 Index: 2
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)