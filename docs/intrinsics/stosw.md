---
title: __stosw | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __stosw
dev_langs:
- C++
helpviewer_keywords:
- stosw instruction
- __stosw intrinsic
- rep stosw instruction
ms.assetid: 7620fd1d-dba5-40e3-8e07-01aa68895133
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41f086c2427d8147014bb6df25f3923d3ab4b84c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401328"
---
# <a name="stosw"></a>__stosw

**Microsoft-spezifisch**

Generiert eine Store-Zeichenfolge-Anweisung (`rep stosw`).

## <a name="syntax"></a>Syntax

```
void __stosw( 
   unsigned short* Dest, 
   unsigned short Data, 
   size_t Count 
);
```

#### <a name="parameters"></a>Parameter

*dest*<br/>
[out] Das Ziel des Vorgangs.

*Data*<br/>
[in] Die zu speichernden Daten.

*Anzahl*<br/>
[in] Die Länge des Blocks Wörter zu schreiben.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__stosw`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Das Ergebnis ist, die das Wort `Data` wird geschrieben, in einen Block von `Count` Wörter den `Dest` Zeichenfolge.

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="example"></a>Beispiel

```
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

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)