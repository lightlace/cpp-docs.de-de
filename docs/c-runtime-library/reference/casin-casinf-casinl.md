---
title: casin, casinf, casinl
ms.date: 11/04/2016
apiname:
- casin
- casinf
- casinl
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
- casin
- casinf
- casinl
- complex/casin
- complex/casinf
- complex/casinl
helpviewer_keywords:
- casin function
- casinf function
- casinl function
ms.assetid: b75d1455-7b1e-43b0-bd46-c530be190be9
ms.openlocfilehash: 209c3da6d6ed03cb5a5b129003c999b002a1a6b7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539619"
---
# <a name="casin-casinf-casinl"></a>casin, casinf, casinl

Ruft den Arkussinus einer komplexen Zahl mit achsenabschnitten außerhalb des Intervalls [-1, + 1] auf der reellen Achse ab.

## <a name="syntax"></a>Syntax

```C
_Dcomplex casin(
   _Dcomplex z
);
_Fcomplex casin(
   _Fcomplex z
);  // C++ only
_Lcomplex casin(
   _Lcomplex z
);  // C++ only
_Fcomplex casinf(
   _Fcomplex z
);
_Lcomplex casinl(
   _Lcomplex z
);
```

### <a name="parameters"></a>Parameter

*z*<br/>
Eine komplexe Zahl, die einen Winkel als Bogenmaß darstellt

## <a name="return-value"></a>Rückgabewert

Der Arkussinus von *z*, im Bogenmaß zurück. Das Ergebnis ist unbegrenzt, auf der imaginären Achse, und klicken Sie im Intervall [-π/2 + π/2] auf der reellen Achse.

## <a name="remarks"></a>Hinweise

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Casin** verwenden und zurückgeben **_Fcomplex** und **_Lcomplex** Werte. In einem C-Programm **Casin** immer Double und gibt eine **_Dcomplex** Wert.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|C-Header|C++-Header|
|-------------|--------------|------------------|
|**Casin**, **Casinf**, **Casinl**|\<complex.h>|\<ccomplex>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[catanh, catanhf, catanhl](catanh-catanhf-catanhl.md)<br/>
[ctanh, ctanhf, ctanhl](ctanh-ctanhf-ctanhl.md)<br/>
[catan, catanf, catanl](catan-catanf-catanl.md)<br/>
[csinh, csinhf, csinhl](csinh-csinhf-csinhl.md)<br/>
[casinh, casinhf, casinhl](casinh-casinhf-casinhl.md)<br/>
[ccosh, ccoshf, ccoshl](ccosh-ccoshf-ccoshl.md)<br/>
[cacosh, cacoshf, cacoshl](cacosh-cacoshf-cacoshl.md)<br/>
[cacos, cacosf, cacosl](cacos-cacosf-cacosl.md)<br/>
[ctan, ctanf, ctanl](ctan-ctanf-ctanl.md)<br/>
[csin, csinf, csinl](csin-csinf-csinl.md)<br/>
[ccos, ccosf, ccosl](ccos-ccosf-ccosl.md)<br/>
[csqrt, csqrtf, csqrtl](csqrt-csqrtf-csqrtl.md)<br/>
