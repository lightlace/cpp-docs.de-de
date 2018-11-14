---
title: __readfsbyte, __readfsdword, __readfsqword, __readfsword
ms.date: 11/04/2016
f1_keywords:
- __readfsword
- __readfsdword
- __readfsbyte
- __readfsqword
helpviewer_keywords:
- __readfsword intrinsic
- readfsword intrinsic
- __readfsdword intrinsic
- readfsbyte intrinsic
- __readfsbyte intrinsic
- readfsdword intrinsic
- readfsqword intrinsic
- __readfsqword intrinsic
ms.assetid: f6ee7203-4179-402c-a464-0746c84ce6ac
ms.openlocfilehash: e5610fcd9be369718875f2f7a7bd358e7c2b07dc
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51327680"
---
# <a name="readfsbyte-readfsdword-readfsqword-readfsword"></a>__readfsbyte, __readfsdword, __readfsqword, __readfsword

**Microsoft-spezifisch**

Lesen Sie Arbeitsspeicher von einem Speicherort, ein Offset relativ zum Anfang des Segments FS angegeben wird.

## <a name="syntax"></a>Syntax

```
unsigned char __readfsbyte(
   unsigned long Offset
);
unsigned short __readfsword(
   unsigned long Offset
);
unsigned long __readfsdword(
   unsigned long Offset
);
unsigned __int64 __readfsqword(
   unsigned long Offset
);
```

#### <a name="parameters"></a>Parameter

*Offset*<br/>
[in] Der Offset vom Anfang des `FS` zum Lesen aus.

## <a name="return-value"></a>Rückgabewert

Der Speicherinhalt des Byte, Wort, zeigt Doppelwort oder Vierfachwort (wie durch den Namen der aufgerufenen Funktion angegeben wird) an der Position `FS:[Offset]`.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__readfsbyte`|x86|
|`__readfsdword`|x86|
|`__readfsqword`|x86|
|`__readfsword`|x86|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Diese Routinen sind nur als systeminterne Funktionen verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__writefsbyte, \__writefsdword, \__writefsqword, \__writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)<br/>
[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)