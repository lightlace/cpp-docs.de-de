---
title: __readdr
ms.date: 09/02/2019
f1_keywords:
- __readdr
helpviewer_keywords:
- __readdr intrinsic
ms.assetid: 061b05da-c85e-4052-b392-106f14bb84f1
ms.openlocfilehash: 646330ca92af08903485fd4583eb2c217fe3e023
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216674"
---
# <a name="__readdr"></a>__readdr

Liest den Wert des angegebenen debugregisters.

## <a name="syntax"></a>Syntax

```C
unsigned         __readdr(unsigned int DebugRegister); /* x86 */
unsigned __int64 __readdr(unsigned int DebugRegister); /* x64 */
```

### <a name="parameters"></a>Parameter

*Debugregistrierung*\
in Eine Konstante von 0 bis 7, die das debugregister identifiziert.

## <a name="return-value"></a>Rückgabewert

Der Wert des angegebenen debugregisters.

## <a name="remarks"></a>Hinweise

Diese systeminternen Funktionen sind nur im Kernel Modus verfügbar, und die Routinen sind nur als intrinsie verfügbar.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__readdr`|x86, x64|

**Header Datei** \<intrin. h->

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[__readeflags](../intrinsics/readeflags.md)
