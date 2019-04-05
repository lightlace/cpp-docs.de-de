---
title: __writedr
ms.date: 11/04/2016
f1_keywords:
- __writedr
helpviewer_keywords:
- __writedr intrinsic
ms.assetid: ac55c1ee-df2f-41d4-a429-6f369d2a934d
ms.openlocfilehash: c495e8c80029680512358198ca8fb0ce6e65414d
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59022480"
---
# <a name="writedr"></a>__writedr

Schreibt den angegebenen Wert dem angegebenen Debug-Register.

## <a name="syntax"></a>Syntax

```
void __writedr(unsigned DebugRegister, unsigned DebugValue);
void __writedr(unsigned DebugRegister, unsigned __int64 DebugValue);
```

#### <a name="parameters"></a>Parameter

*DebugRegister*<br/>
[in] Registrieren Sie eine Zahl von 0 bis 7, die das Debuggen identifiziert.

*DebugValue*<br/>
[in] Ein Wert zum Schreiben in das Debuggen registrieren.

## <a name="remarks"></a>Hinweise

Diese systeminternen Funktionen sind nur im Kernelmodus verfügbar, und die Routinen sind nur als systeminterne Funktionen verfügbar.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__writedr`|x86, x64|

**Headerdatei** \<intrin.h >

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[__readdr](../intrinsics/readdr.md)