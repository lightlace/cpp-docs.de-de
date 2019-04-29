---
title: copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl
ms.date: 04/05/2018
apiname:
- copysignf
- copysignl
- _copysignl
- _copysign
- _copysignf
- copysign
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _copysignl
- copysign
- copysignf
- _copysign
- copysignl
- _copysignf
helpviewer_keywords:
- copysignl function
- _copysignl function
- copysign function
- _copysignf function
- _copysign function
- copysignf function
ms.assetid: 009216d6-72a2-402d-aa6c-91d924b2c9e4
ms.openlocfilehash: 6f450da4a4391f94d1905beefdeca8e3f01fec51
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349055"
---
# <a name="copysign-copysignf-copysignl-copysign-copysignf-copysignl"></a>copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl

Gibt einen Wert zurück, der die Größe eines Arguments und das Zeichen eines anderen Arguments aufweist.

## <a name="syntax"></a>Syntax

```C
double copysign(
   double x,
   double y
);
float copysign(
   float x,
   float y
); // C++ only
long double copysign(
   long double x,
   long double y
); // C++ only
float copysignf(
   float x,
   float y
); // C++ only
long double copysignl(
   long double x,
   long double y
); // C++ only
double _copysign(
   double x,
   double y
);
long double _copysignl(
   long double x,
   long double y
);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Der Gleitkommawert, der als Betrag des Ergebnisses zurückgegeben wird.

*y*<br/>
Der Gleitkommawert, der als Zeichen des Ergebnisses zurückgegeben wird.

[Floating-Point Support Routines (Routinen für die Gleitkommaunterstützung)](../../c-runtime-library/floating-point-support.md)

## <a name="return-value"></a>Rückgabewert

Die **Copysign** Funktionen geben einen Gleitkommawert, der die Größe der kombiniert zurück *x* und das Vorzeichen von *y*. Es gibt keine Fehlerrückgabe.

## <a name="remarks"></a>Hinweise

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Copysign** verwenden und zurückgeben **"float"** oder **lange** **doppelte** Werte. In einem C-Programm **Copysign** immer Double und gibt eine **doppelte**.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_copysign**|\<float.h>|
|**copysign**, **copysignf**, **copysignl**, **_copysignf**, **_copysignl**|\<math.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)<br/>
[_chgsign, _chgsignf, _chgsignl](chgsign-chgsignf-chgsignl.md)<br/>
