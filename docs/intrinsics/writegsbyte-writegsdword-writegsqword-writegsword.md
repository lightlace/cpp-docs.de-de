---
title: __writegsbyte, __writegsdword, __writegsqword, __writegsword
ms.date: 11/04/2016
f1_keywords:
- __writegsbyte
- __writegsqword
- __writegsdword
- __writegsword
helpviewer_keywords:
- __writegsqword intrinsic
- __writegsbyte intrinsic
- __writegsword intrinsic
- __writegsdword intrinsic
ms.assetid: 7746cf6d-2259-4139-9aab-c07dd75c8037
ms.openlocfilehash: d0de62333500a7ced2c953d86502b4dfb08f5a04
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632465"
---
# <a name="writegsbyte-writegsdword-writegsqword-writegsword"></a>__writegsbyte, __writegsdword, __writegsqword, __writegsword

**Microsoft-spezifisch**

Schreibvorgänge im Speicher an einem Speicherort, ein Offset relativ zum Beginn der GS-Segment angegeben wird.

## <a name="syntax"></a>Syntax

```
void __writegsbyte( 
   unsigned long Offset, 
   unsigned char Data 
);
void __writegsword( 
   unsigned long Offset, 
   unsigned short Data 
);
void __writegsdword( 
   unsigned long Offset, 
   unsigned long Data 
);
void __writegsqword( 
   unsigned long Offset, 
   unsigned __int64 Data 
);
```

#### <a name="parameters"></a>Parameter

*Offset*<br/>
[in] Der Offset vom Anfang des GS zu schreiben.

*Data*<br/>
[in] Der zu schreibende Wert.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__writegsbyte`|x64|
|`__writegsdword`|x64|
|`__writegsqword`|x64|
|`__writegsword`|x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Diese systeminternen Funktionen sind im Kernel-Modus ist nur verfügbar, und diese Routinen sind nur als systeminterne Funktionen verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__readgsbyte, \__readgsdword, \__readgsqword, \__readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)<br/>
[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)