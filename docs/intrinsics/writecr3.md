---
title: __writecr3
ms.date: 11/04/2016
f1_keywords:
- _writecr3
helpviewer_keywords:
- _writecr3 intrinsic
ms.assetid: 959d49fa-69d5-47cf-88d2-7688367fe38f
ms.openlocfilehash: 2046e3b2014bd17e74e880e8dbd0fcdc0a65021c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50592558"
---
# <a name="writecr3"></a>__writecr3

**Microsoft-spezifisch**

Schreibt den Wert `Data` dem CR3-Register.

## <a name="syntax"></a>Syntax

```
void writecr3( 
   unsigned __int64 Data 
);
```

#### <a name="parameters"></a>Parameter

*Data*<br/>
[in] Der Wert, der registriert wird, CR3 geschrieben werden soll.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__writecr3`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Diese systeminterne Funktion ist nur im Kernelmodus verfügbar, und die Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)