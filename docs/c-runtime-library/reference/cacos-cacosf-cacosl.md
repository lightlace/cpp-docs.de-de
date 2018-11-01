---
title: cacos, cacosf, cacosl
ms.date: 11/04/2016
apiname:
- cacos
- cacosf
- cacosl
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
- cacos
- cacosf
- cacosl
- complex/cacos
- complex/cacosf
- complex/cacosl
helpviewer_keywords:
- cacos function
- cacosf function
- cacosl function
ms.assetid: 78118c00-0a07-49c1-8a13-4bf19ce3aea8
ms.openlocfilehash: 18757ecd30f399ca3d1fdb77e8bff8213a265e74
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543194"
---
# <a name="cacos-cacosf-cacosl"></a>cacos, cacosf, cacosl

Ruft den Arkuskosinus einer komplexen Zahl mit achsenabschnitten außerhalb des Intervalls [-1, + 1] auf der reellen Achse ab.

## <a name="syntax"></a>Syntax

```C
_Dcomplex cacos( _Dcomplex z );
_Fcomplex cacosf( _Fcomplex z );
_Lcomplex cacosl( _Lcomplex z );
```

```cpp
_Fcomplex cacos( _Fcomplex z );  // C++ only
_Lcomplex cacos( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>Parameter

*z*<br/>
Eine komplexe Zahl, die einen Winkel als Bogenmaß darstellt

## <a name="return-value"></a>Rückgabewert

Der Arkuskosinus der *z*, im Bogenmaß zurück. Das Ergebnis ist unbegrenzt, auf der imaginären Achse, und klicken Sie in der im Intervall [0, π] auf der reellen Achse. Domänenfehler werden auftreten, wenn *z* liegt außerhalb des Intervalls [-1, + 1].

## <a name="remarks"></a>Hinweise

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Cacos** verwenden und zurückgeben **_Fcomplex** und **_Lcomplex** Werte. In einem C-Programm **Cacos** immer Double und gibt eine **_Dcomplex** Wert.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|C-Header|C++-Header|
|-------------|--------------|------------------|
|**Cacos**, **Cacosf**, **Cacosl**|\<complex.h>|\<ccomplex>|

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
[ctan, ctanf, ctanl](ctan-ctanf-ctanl.md)<br/>
[csin, csinf, csinl](csin-csinf-csinl.md)<br/>
[casin, casinf, casinl](casin-casinf-casinl.md)<br/>
[ccos, ccosf, ccosl](ccos-ccosf-ccosl.md)<br/>
[csqrt, csqrtf, csqrtl](csqrt-csqrtf-csqrtl.md)<br/>
