---
title: __writecr0
ms.date: 11/04/2016
f1_keywords:
- _writecr0
helpviewer_keywords:
- _writecr0 intrinsic
ms.assetid: a143d08d-0333-4e1b-91b4-4acb2ae91b5a
ms.openlocfilehash: 8e36aa1c1e7299c1de5cba26acb8a4ae8165ad6b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547146"
---
# <a name="writecr0"></a>__writecr0

**Microsoft-spezifisch**

Schreibt den Wert `Data` dem CR0-Register.

## <a name="syntax"></a>Syntax

```
void writecr0( 
   unsigned __int64 Data 
);
```

#### <a name="parameters"></a>Parameter

*Data*<br/>
[in] Der Wert zum Schreiben in das CR0-Register.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__writecr0`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Diese systeminterne Funktion ist nur im Kernelmodus verfügbar, und die Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)