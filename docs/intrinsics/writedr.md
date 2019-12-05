---
title: __writedr
ms.date: 09/02/2019
f1_keywords:
- __writedr
helpviewer_keywords:
- __writedr intrinsic
ms.assetid: ac55c1ee-df2f-41d4-a429-6f369d2a934d
ms.openlocfilehash: 473e7223e9974d0125e772c152ea85ae90b97342
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74858060"
---
# <a name="__writedr"></a>__writedr

**Microsoft-spezifisch**

Schreibt den angegebenen Wert in das angegebene debugregister.

## <a name="syntax"></a>Syntax

```C
void __writedr(unsigned DebugRegister, unsigned DebugValue); /* x86 */
void __writedr(unsigned DebugRegister, unsigned __int64 DebugValue); /* x64 */
```

### <a name="parameters"></a>Parameters

*Debugregister* -\
in Eine Zahl von 0 bis 7, die das debugregister identifiziert.

Debug *value* -\
in Ein Wert, der in das debugregister geschrieben werden soll.

## <a name="remarks"></a>Hinweise

Diese systeminternen Funktionen sind nur im Kernel Modus verfügbar, und die Routinen sind nur als intrinsie verfügbar.

## <a name="requirements"></a>-Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__writedr`|x86, x64|

**Header Datei** \<"intrin. h" >

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

Systeminterne [Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[__readdr](../intrinsics/readdr.md)
