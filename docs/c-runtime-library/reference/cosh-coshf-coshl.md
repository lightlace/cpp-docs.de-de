---
title: Cosh, Coshf, Coshl | Microsoft Docs
ms.custom: ''
ms.date: 04/11/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- cosh
- coshf
- coshl
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
- cosh
- coshf
- coshl
dev_langs:
- C++
helpviewer_keywords:
- cosh function
- coshf function
- coshl function
- trigonometric functions
- hyperbolic functions
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b2482a6e6e51efea50cac6a5a56154f5dc85663d
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="cosh-coshf-coshl"></a>Cosh, Coshf, coshl

Berechnet den hyperbolischen Cosinus.

## <a name="syntax"></a>Syntax

```C
double cosh( double x );
float coshf( float x );
long double coshl( long double x );
```

```cpp
float cosh( float x );  // C++ only
long double cosh( long double x );  // C++ only
```

### <a name="parameters"></a>Parameter

*w*<br/>
Winkel im Bogenmaß.

## <a name="return-value"></a>Rückgabewert

Der Hyperbelkosinus von *x*.

Standardmäßig ist das Ergebnis zu groß ist, in eine **Cosh**, **Coshf**, oder **Coshl** aufrufen, gibt die Funktion **HUGE_VAL** und legt **Errno** auf **ERANGE**.

|Eingabe|SEH-Ausnahme|Matherr-Ausnahme|
|-----------|-------------------|-----------------------|
|± **QNAN**, **IND**|Keine|**_DOMAIN**|
|*X* ≥ 7, 104760e + 002|**UNGENAUE**+**"ÜBERLAUF"**|**"ÜBERLAUF"**|

## <a name="remarks"></a>Hinweise

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Cosh** verwenden und zurückgeben **"float"** oder **lange** **doppelte** Werte. In einem C-Programm **Cosh** immer Double und gibt eine **doppelte**.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header (C)|Erforderlicher Header (C++)|
|-------------|---------------------|-|
|**Coshf**, **Cosl**, **Coshl**|\<math.h>|\<cmath> oder \<math.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel in [Sinh, Sinhf, Sinhl](sinh-sinhf-sinhl.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[acosh, acoshf, acoshl](acosh-acoshf-acoshl.md)<br/>
[asinh, asinhf, asinhl](asinh-asinhf-asinhl.md)<br/>
[atanh, atanhf, atanhl](atanh-atanhf-atanhl.md)<br/>
[_matherr](matherr.md)<br/>
[sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)<br/>
[tanh, tanhf, tanhl](tanh-tanhf-tanhl.md)<br/>
