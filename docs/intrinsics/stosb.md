---
title: __stosb | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __stosb
dev_langs:
- C++
helpviewer_keywords:
- rep stosb instruction
- __stosb intrinsic
- stosb instruction
ms.assetid: 634589ed-2da3-439b-a381-a214d89bf10c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 61050f8fc1924f6d2a143893af5bd1918df94394
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43895187"
---
# <a name="stosb"></a>__stosb

**Microsoft-spezifisch**

Generiert eine Store-Zeichenfolge-Anweisung (`rep stosb`).

## <a name="syntax"></a>Syntax

```
void __stosb(
   unsigned char* Dest,
   unsigned char Data,
   size_t Count
);
```

#### <a name="parameters"></a>Parameter

[out] `Dest`  
Das Ziel des Vorgangs.

[in] `Data`  
Die zu speichernden Daten.

[in] `Count`  
Die Länge des Blocks des zu schreibenden Bytes kennzeichnet.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__stosb`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Das Ergebnis ist, die das Zeichen `Data` wird geschrieben, in einen Block von `Count` Bytes in den `Dest` Zeichenfolge.

Diese Routine ist nur als systeminterne Funktion verfügbar.

## <a name="example"></a>Beispiel

```C
// stosb.c
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__stosb)  

int main()  
{
    unsigned char c = 0x40; /* '@' character */
    unsigned char s[] = "*********************************";

    printf_s("%s\n", s);
    __stosb((unsigned char*)s+1, c, 6);
    printf_s("%s\n", s);

}
```  

```Output
*********************************  
*@@@@@@**************************  
```  

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)