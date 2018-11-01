---
title: __outdword
ms.date: 11/04/2016
f1_keywords:
- __outdword
helpviewer_keywords:
- out instruction
- outdword instruction
- __outdword intrinsic
ms.assetid: ed1e4994-a84b-4759-8bf9-cd48fb073f4d
ms.openlocfilehash: 42507cec8932d3c6fa4482f4e296e76753cee896
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428170"
---
# <a name="outdword"></a>__outdword

**Microsoft-spezifisch**

Generiert die `out` Anweisung zum Senden einer zeigt Doppelwort `Data` der Port `Port`.

## <a name="syntax"></a>Syntax

```
void __outdword( 
   unsigned short Port, 
   unsigned long Data 
);
```

#### <a name="parameters"></a>Parameter

*Port*<br/>
[in] Der Port, der die Daten zu senden.

*Data*<br/>
[in] Die Doppelwort gesendet werden.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__outdword`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)