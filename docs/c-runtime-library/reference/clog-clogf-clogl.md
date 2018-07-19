---
title: clog, clogf, clogl | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- clog
- clogf
- clogl
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
- clog
- clogf
- clogl
- complex/clog
- complex/clogf
- complex/clogl
dev_langs:
- C++
helpviewer_keywords:
- clog function
- clogf function
- clogl function
ms.assetid: 870b9b0b-6618-46f3-bfcf-da595cbd5e18
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ca1b5b917b48a0307b9bd2a362ac7eb6a21dca3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32394794"
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

Der natürliche Logarithmus des *z*. Das Ergebnis ist unbounded entlang der echte und im Intervall [-Iπ, + Iπ] der imaginäre Achse.

Die möglichen Rückgabewerte sind:

|z Parameter|Rückgabewert|
|-----------------|------------------|
|Positiv|Der Logarithmus zur Basis 10 von z|
|Zero|- ∞|
|Negativ|NaN|
|NaN|NaN|
|+ ∞|+ ∞|

## <a name="remarks"></a>Hinweise

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **clog** verwenden und zurückgeben **_Fcomplex** und **_Lcomplex** Werte. In einem C-Programm **clog** immer Double und gibt eine **_Dcomplex** Wert.

## <a name="requirements"></a>Anforderungen

|Routine|C-Header|C++-Header|
|-------------|--------------|------------------|
|**CLOG**, **Clogf**, **Clogl**|\<complex.h>|\<ccomplex>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[cexp, cexpf, cexpl](cexp-cexpf-cexpl.md)<br/>
[cpow, cpowf, cpowl](cpow-cpowf-cpowl.md)<br/>
[clog10, clog10f, clog10l](clog10-clog10f-clog10l.md)<br/>
