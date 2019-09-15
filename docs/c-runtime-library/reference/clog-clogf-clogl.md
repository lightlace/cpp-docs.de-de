---
title: clog, clogf, clogl
ms.date: 11/04/2016
api_name:
- clog
- clogf
- clogl
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- clog
- clogf
- clogl
- complex/clog
- complex/clogf
- complex/clogl
helpviewer_keywords:
- clog function
- clogf function
- clogl function
ms.assetid: 870b9b0b-6618-46f3-bfcf-da595cbd5e18
ms.openlocfilehash: 76ee6e4e81c275c8cbed0f74914521c0b44499bb
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942921"
---
# <a name="clog-clogf-clogl"></a>clog, clogf, clogl

Ruft den natürlichen Logarithmus einer komplexen Zahl mit einem Achsenabschnitt auf der negativen reellen Achse ab.

## <a name="syntax"></a>Syntax

```C
_Dcomplex clog(
   _Dcomplex z
);
_Fcomplex clog(
   _Fcomplex z
);  // C++ only
_Lcomplex clog(
   _Lcomplex z
);  // C++ only
_Fcomplex clogf(
   _Fcomplex z
);
_Lcomplex clogl(
   _Lcomplex z
);
```

### <a name="parameters"></a>Parameter

*z*<br/>
Die Basis des Logarithmus.

## <a name="return-value"></a>Rückgabewert

Der natürliche Logarithmus von *z*. Das Ergebnis wird an der realen Achse und im Intervall [-ID, + iy] entlang der imaginären Achse gebunden.

Die möglichen Rückgabewerte sind:

|z Parameter|Rückgabewert|
|-----------------|------------------|
|Positiv|Der Logarithmus zur Basis 10 von z|
|Zero|- ∞|
|Negativ|NaN|
|NaN|NaN|
|+ ∞|+ ∞|

## <a name="remarks"></a>Hinweise

Da C++ das überladen zulässt, können Sie über Ladungen von **Clog** aufzurufen, die **_Fcomplex** -und **_Lcomplex** -Werte verwenden und zurückgeben. In einem C-Programm nimmt **Clog** immer einen **_Dcomplex** -Wert an und gibt diesen zurück.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|C-Header|C++-Header|
|-------------|--------------|------------------|
|**clog**,               **clogf**, **clogl**|\<complex.h>|\<ccomplex>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[cexp, cexpf, cexpl](cexp-cexpf-cexpl.md)<br/>
[cpow, cpowf, cpowl](cpow-cpowf-cpowl.md)<br/>
[clog10, clog10f, clog10l](clog10-clog10f-clog10l.md)<br/>
