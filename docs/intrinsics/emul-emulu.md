---
title: __emul, __emulu
ms.date: 09/02/2019
f1_keywords:
- __emulu_cpp
- __emul
- __emul_cpp
- __emulu
helpviewer_keywords:
- __emul intrinsic
- __emulu intrinsic
ms.assetid: 79545236-cca2-40b8-a4e1-8abce9b26311
ms.openlocfilehash: 16b2b38f6f44b99c9f5b9370ba586342a860684e
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216742"
---
# <a name="__emul-__emulu"></a>__emul, __emulu

**Microsoft-spezifisch**

Führt Multiplikationen aus, die eine ganzzahlige 32-Bit-Ganzzahl enthalten.

## <a name="syntax"></a>Syntax

```C
__int64 __emul(
   int a,
   int b
);
unsigned __int64 __emulu(
   unsigned int a,
   unsigned int b
);
```

### <a name="parameters"></a>Parameter

*ein*\
in Der erste ganzzahlige Operand der Multiplikation.

*b*\
in Der zweite ganzzahlige Operand der Multiplikation.

## <a name="return-value"></a>Rückgabewert

Das Ergebnis der Multiplikation.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__emul`|x86, x64|
|`__emulu`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

`__emul`nimmt 2 32-Bit-signierte Werte an und gibt das Ergebnis der Multiplikation als 64-Bit-Ganzzahl mit Vorzeichen zurück.

`__emulu`nimmt ganzzahlige Werte von 2 32-Bit-Ganzzahl ohne Vorzeichen und gibt das Ergebnis der Multiplikation als 64-Bit-Ganzzahl ohne Vorzeichen zurück.

## <a name="example"></a>Beispiel

```cpp
// emul.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__emul)
#pragma intrinsic(__emulu)

int main()
{
   int a = -268435456;
   int b = 2;

   __int64 result = __emul(a, b);

   cout << a << " * " << b << " = " << result << endl;

   unsigned int ua = 0xFFFFFFFF; // Dec value: 4294967295
   unsigned int ub = 0xF000000;  // Dec value: 251658240

   unsigned __int64 uresult = __emulu(ua, ub);

   cout << ua << " * " << ub << " = " << uresult << endl;

}
```

## <a name="output"></a>Ausgabe

```Output
-268435456 * 2 = -536870912
4294967295 * 251658240 = 1080863910317260800
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
