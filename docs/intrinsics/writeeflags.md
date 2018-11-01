---
title: __writeeflags
ms.date: 11/04/2016
f1_keywords:
- __writeeflags
helpviewer_keywords:
- __writeeflags intrinsics
ms.assetid: a62a522c-d7fa-4f10-a620-a3b32bdf3f17
ms.openlocfilehash: 8509bf37019d1525cdaca33bf1819d85ace7d75a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50600043"
---
# <a name="writeeflags"></a>__writeeflags

Schreibt den angegebenen Wert in das Programm Status und -Steuerelement (EFLAGS) zu registrieren.

## <a name="syntax"></a>Syntax

```
void __writeeflags(unsigned Value);
void __writeeflags(unsigned __int64 Value);
```

#### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Wert*|[in] Der Wert, der registriert wird, EFLAGS geschrieben werden soll. Die `Value` Parameter ist 32 Bits lang für eine 32-Bit-Plattform und 64 Bit lang für eine 64-Bit-Plattform.|

## <a name="remarks"></a>Hinweise

Diese Routinen sind nur als systeminterne Funktionen verfügbar.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__writeeflags`|x86, x64|

**Headerdatei** \<intrin.h >

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[__readeflags](../intrinsics/readeflags.md)