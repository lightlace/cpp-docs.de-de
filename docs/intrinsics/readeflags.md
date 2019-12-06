---
title: __readeflags
ms.date: 09/02/2019
f1_keywords:
- __readeflags
helpviewer_keywords:
- __readeflags intrinsic
ms.assetid: f9d2f4d8-c428-491f-b8de-04d0566b2b6b
ms.openlocfilehash: 6afdc0f20a3ae72865a80ba2eb7f896f79f63171
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857904"
---
# <a name="__readeflags"></a>__readeflags

**Microsoft-spezifisch**

Liest das Register Programmstatus und-Steuerung (EFLAGS).

## <a name="syntax"></a>Syntax

```C
unsigned     int __readeflags(void); /* x86 */
unsigned __int64 __readeflags(void); /* x64 */
```

## <a name="return-value"></a>Rückgabewert

Der Wert der EFLAGS-Registrierung. Der Rückgabewert ist 32 Bits lang auf einer 32-Bit-Plattform und 64 Bits auf einer 64-Bit-Plattform.

## <a name="remarks"></a>Hinweise

Diese Routinen sind nur als systeminterne Funktionen verfügbar.

## <a name="requirements"></a>-Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__readeflags`|x86, x64|

**Header Datei** \<"intrin. h" >

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

Systeminterne [Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[__writeeflags](../intrinsics/writeeflags.md)
