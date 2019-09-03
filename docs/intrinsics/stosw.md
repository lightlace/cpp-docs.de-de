---
title: __stosw
ms.date: 09/02/2019
f1_keywords:
- __stosw
helpviewer_keywords:
- stosw instruction
- __stosw intrinsic
- rep stosw instruction
ms.assetid: 7620fd1d-dba5-40e3-8e07-01aa68895133
ms.openlocfilehash: 5fd29bbf1aebba115670fc1bc35e0d8cbe29c7ad
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219930"
---
# <a name="__stosw"></a>__stosw

**Microsoft-spezifisch**

Generiert eine Speicher Zeichen folgen Anweisung`rep stosw`().

## <a name="syntax"></a>Syntax

```C
void __stosw(
   unsigned short* Destination,
   unsigned short Data,
   size_t Count
);
```

### <a name="parameters"></a>Parameter

*Entwickelt*\
vorgenommen Das Ziel des Vorgangs.

*Vorrats*\
in Die Daten, die gespeichert werden sollen.

*Countdown*\
in Die Länge des zu schreibenden Wörter Blocks.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__stosw`|x86, x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Das Ergebnis ist, dass die Word- *Daten* in einen Block von *count* -Wörtern in der *Ziel* Zeichenfolge geschrieben werden.

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="example"></a>Beispiel

```C
// stosw.c
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__stosw)

int main()
{
    unsigned short val = 128;
    unsigned short a[100];
    memset(a, 0, sizeof(a));
    __stosw(a+10, val, 2);
    printf_s("%u %u %u %u", a[9], a[10], a[11], a[12]);
}
```

```Output
0 128 128 0
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
