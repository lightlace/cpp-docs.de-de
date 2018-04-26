---
title: cexp, cexpf, cexpl | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- cexp
- cexpf
- cexpl
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
- cexp
- cexpf
- cexpl
- complex/cepx
- complex/cexpf
- complex/cexpl
dev_langs:
- C++
helpviewer_keywords:
- cexp function
- cexpl function
- cexpf function
ms.assetid: f27fd5a9-70c7-4957-a7ee-5256d19bd1da
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 85e46762b769bd4afcbfe9887d730faedfafa0f3
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="cexp-cexpf-cexpl"></a>cexp, cexpf, cexpl

Berechnet die Exponentialzahl zur Basis e einer komplexen Zahl.

## <a name="syntax"></a>Syntax

```C
_Dcomplex cexp( _Dcomplex z );
_Fcomplex cexpf( _Fcomplex z );
_Lcomplex cexpl( _Lcomplex z );
```

```cpp
_Fcomplex cexp( _Fcomplex z );  // C++ only
_Lcomplex cexp( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>Parameter

*z*<br/>
Eine komplexe Zahl, die den Exponenten darstellt.

## <a name="return-value"></a>Rückgabewert

Der Wert der **e** potenziert mit der *z*.

## <a name="remarks"></a>Hinweise

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Cexp** verwenden und zurückgeben **_Fcomplex** und **_Lcomplex** Werte. In einem C-Programm **Cexp** immer Double und gibt eine **_Dcomplex** Wert.

## <a name="requirements"></a>Anforderungen

|Routine|C-Header|C++-Header|
|-------------|--------------|------------------|
|**Cexp**, **Cexpf**, **Cexpl**|\<complex.h>|\<complex.h>|

Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[cpow, cpowf, cpowl](cpow-cpowf-cpowl.md)<br/>
[clog10, clog10f, clog10l](clog10-clog10f-clog10l.md)<br/>
[clog, clogf, clogl](clog-clogf-clogl.md)<br/>
