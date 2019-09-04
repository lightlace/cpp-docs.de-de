---
title: __writedr
ms.date: 09/02/2019
f1_keywords:
- __writedr
helpviewer_keywords:
- __writedr intrinsic
ms.assetid: ac55c1ee-df2f-41d4-a429-6f369d2a934d
ms.openlocfilehash: 715ef7432d506c2758c9c3da913e9c0ebb24e13f
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219226"
---
# <a name="__writedr"></a>__writedr

Schreibt den angegebenen Wert in das angegebene debugregister.

## <a name="syntax"></a>Syntax

```C
void __writedr(unsigned DebugRegister, unsigned DebugValue); /* x86 */
void __writedr(unsigned DebugRegister, unsigned __int64 DebugValue); /* x64 */
```

### <a name="parameters"></a>Parameter

*Debugregistrierung*\
in Eine Zahl von 0 bis 7, die das debugregister identifiziert.

*Debug-Wert*\
in Ein Wert, der in das debugregister geschrieben werden soll.

## <a name="remarks"></a>Hinweise

Diese systeminternen Funktionen sind nur im Kernel Modus verfügbar, und die Routinen sind nur als intrinsie verfügbar.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__writedr`|x86, x64|

**Header Datei** \<intrin. h->

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[__readdr](../intrinsics/readdr.md)
