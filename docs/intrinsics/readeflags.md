---
title: __readeflags
ms.date: 09/02/2019
f1_keywords:
- __readeflags
helpviewer_keywords:
- __readeflags intrinsic
ms.assetid: f9d2f4d8-c428-491f-b8de-04d0566b2b6b
ms.openlocfilehash: fe2365c2837b6c583810bb9fc908fe98486a2d38
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221229"
---
# <a name="__readeflags"></a>__readeflags

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

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__readeflags`|x86, x64|

**Header Datei** \<intrin. h->

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[__writeeflags](../intrinsics/writeeflags.md)
