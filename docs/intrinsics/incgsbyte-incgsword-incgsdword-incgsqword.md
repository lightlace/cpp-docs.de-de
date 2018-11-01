---
title: __incgsbyte, __incgsword, __incgsdword, __incgsqword
ms.date: 11/04/2016
f1_keywords:
- __incgsdword
- __incgsqword_cpp
- __incgsword_cpp
- __incgsword
- __incgsbyte
- __incgsbyte_cpp
- __incgsqword
- __incgsdword_cpp
helpviewer_keywords:
- __incgsbyte intrinsic
- __incgsword intrinsic
- __incgsqword intrinsic
- __incgsdword intrinsic
ms.assetid: 06bfdf4f-7643-4fe0-8455-60ce3068073e
ms.openlocfilehash: a6e8307214f85ba376c539ac791c80ca688c619f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586081"
---
# <a name="incgsbyte-incgsword-incgsdword-incgsqword"></a>__incgsbyte, __incgsword, __incgsdword, __incgsqword

**Microsoft-spezifisch**

Fügen Sie eine auf den Wert an einer Speicheradresse, die durch ein Offset relativ zum Anfang des angegebenen die `GS` Segment.

## <a name="syntax"></a>Syntax

```
void __incgsbyte( 
   unsigned long Offset 
);
void __incgsword( 
   unsigned long Offset 
);
void __incgsdword( 
   unsigned long Offset
);
void __incgsqword( 
   unsigned long Offset 
);
```

#### <a name="parameters"></a>Parameter

*Offset*<br/>
[in] Der Offset vom Anfang des `GS`.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__incgsbyte`|x64|
|`__incgsword`|x64|
|`__incgsdword`|x64|
|`__incgsqword`|x64|

## <a name="remarks"></a>Hinweise

Diese systeminternen Funktionen sind nur im Kernelmodus verfügbar, und die Routinen sind nur als systeminterne Funktionen verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__addgsbyte, \__addgsword, \__addgsdword, \__addgsqword](../intrinsics/addgsbyte-addgsword-addgsdword-addgsqword.md)<br/>
[__readgsbyte, \__readgsdword, \__readgsqword, \__readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)<br/>
[__writegsbyte, \__writegsdword, \__writegsqword, \__writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)<br/>
[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)