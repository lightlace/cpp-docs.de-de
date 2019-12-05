---
title: __writeeflags
ms.date: 09/02/2019
f1_keywords:
- __writeeflags
helpviewer_keywords:
- __writeeflags intrinsics
ms.assetid: a62a522c-d7fa-4f10-a620-a3b32bdf3f17
ms.openlocfilehash: 6b9b6976369ed810789e5749a2e30029cad4c2d7
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74858047"
---
# <a name="__writeeflags"></a>__writeeflags

**Microsoft-spezifisch**

Schreibt den angegebenen Wert in das Register Programmstatus und-Steuerung (EFLAGS).

## <a name="syntax"></a>Syntax

```C
void __writeeflags(unsigned Value); /* x86 */
void __writeeflags(unsigned __int64 Value); /* x64 */
```

### <a name="parameters"></a>Parameters

*Wert*\
in Der Wert, der in das EFLAGS-Register geschrieben werden soll. Der `Value`-Parameter für eine 32-Bit-Plattform und 64 Bits ist für eine 64-Bit-Plattform 32 Bit lang.

## <a name="remarks"></a>Hinweise

Diese Routinen sind nur als systeminterne Funktionen verfügbar.

## <a name="requirements"></a>-Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__writeeflags`|x86, x64|

**Header Datei** \<"intrin. h" >

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

Systeminterne [Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
[__readeflags](../intrinsics/readeflags.md)
