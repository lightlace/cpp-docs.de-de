---
title: __readdr
ms.date: 09/02/2019
f1_keywords:
- __readdr
helpviewer_keywords:
- __readdr intrinsic
ms.assetid: 061b05da-c85e-4052-b392-106f14bb84f1
ms.openlocfilehash: fbaf9e761f9f1450ccd12dc378ab6e498aa0df08
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857878"
---
# <a name="__readdr"></a>__readdr

**Microsoft-spezifisch**

Liest den Wert des angegebenen debugregisters.

## <a name="syntax"></a>Syntax

```C
unsigned         __readdr(unsigned int DebugRegister); /* x86 */
unsigned __int64 __readdr(unsigned int DebugRegister); /* x64 */
```

### <a name="parameters"></a>Parameters

*Debugregister* -\
in Eine Konstante von 0 bis 7, die das debugregister identifiziert.

## <a name="return-value"></a>Rückgabewert

Der Wert des angegebenen debugregisters.

## <a name="remarks"></a>Hinweise

Diese systeminternen Funktionen sind nur im Kernel Modus verfügbar, und die Routinen sind nur als intrinsie verfügbar.

## <a name="requirements"></a>-Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__readdr`|x86, x64|

**Header Datei** \<"intrin. h" >

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

Systeminterne [Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[__readeflags](../intrinsics/readeflags.md)
