---
title: __writecr8
ms.date: 11/04/2016
f1_keywords:
- _writecr8
helpviewer_keywords:
- _writecr8 intrinsic
ms.assetid: 6f8bd632-dddb-4335-971e-1acee24aa2b9
ms.openlocfilehash: d401673e7ee6cd18b8bc05140efc3b819e48a30f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471994"
---
# <a name="writecr8"></a>__writecr8

**Microsoft-spezifisch**

Schreibt den Wert `Data` dem CR8-Register.

## <a name="syntax"></a>Syntax

```
void writecr8( 
   unsigned __int64 Data 
);
```

#### <a name="parameters"></a>Parameter

*Data*<br/>
[in] Der Wert, der registriert wird, CR8 geschrieben werden soll.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__writecr8`|x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Diese systeminterne Funktion ist nur im Kernelmodus verfügbar, und die Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)