---
title: Gleitkomma-primitive
ms.date: 01/31/2019
apiname:
- _dclass
- _ldclass
- _fdclass
- _dsign
- _ldsign
- _fdsign
- _dpcomp
- _ldpcomp
- _fdpcomp
- _dtest
- _ldtest
- _fdtest
- _d_int
- _ld_int
- _fd_int
- _dscale
- _ldscale
- _fdscale
- _dunscale
- _ldunscale
- _fdunscale
- _dexp
- _ldexp
- _fdexp
- _dnorm
- _fdnorm
- _dpoly
- _ldpoly
- _fdpoly
- _dlog
- _ldlog
- _fdlog
- _dsin
- _ldsin
- _fdsin
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
- _dclass
- _ldclass
- _fdclass
- _dsign
- _ldsign
- _fdsign
- _dpcomp
- _ldpcomp
- _fdpcomp
- _dtest
- _ldtest
- _fdtest
- _d_int
- _ld_int
- _fd_int
- _dscale
- _ldscale
- _fdscale
- _dunscale
- _ldunscale
- _fdunscale
- _dexp
- _ldexp
- _fdexp
- _dnorm
- _fdnorm
- _dpoly
- _ldpoly
- _fdpoly
- _dlog
- _ldlog
- _fdlog
- _dsin
- _ldsin
- _fdsin
helpviewer_keywords:
- _dclass
- _ldclass
- _fdclass
- _dsign
- _ldsign
- _fdsign
- _dpcomp
- _ldpcomp
- _fdpcomp
- _dtest
- _ldtest
- _fdtest
- _d_int
- _ld_int
- _fd_int
- _dscale
- _ldscale
- _fdscale
- _dunscale
- _ldunscale
- _fdunscale
- _dexp
- _ldexp
- _fdexp
- _dnorm
- _fdnorm
- _dpoly
- _ldpoly
- _fdpoly
- _dlog
- _ldlog
- _fdlog
- _dsin
- _ldsin
- _fdsin
ms.openlocfilehash: 230d0def145bcb443437b59303b2b36e348da2bb
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2019
ms.locfileid: "55703438"
---
# <a name="floating-point-primitives"></a>Gleitkomma-primitive

Microsoft-spezifischen primitiven Funktionen, die verwendet werden, um einige standardmäßige C Runtime Library (CRT) Gleitkomma-Funktionen zu implementieren. Sie sind aus Gründen der Vollständigkeit hier dokumentiert, jedoch werden nicht empfohlen. Einige dieser Funktionen sind als nicht verwendet werden, gekennzeichnet werden, da sie bekannt sind, um Probleme mit einfacher Genauigkeit, Ausnahmebehandlung und Konformität mit IEEE-754-Verhalten zu erhalten. Damit sind sie in der Bibliothek nur für Abwärtskompatibilität vorhanden. Ziehen Sie für das korrekte Verhalten, Portabilität und Einhaltung von Standards die standardmäßigen Gleitkommafunktionen diese Funktionen vor.

## <a name="dclass-ldclass-fdclass"></a>_dclass, _ldclass, _fdclass

### <a name="syntax"></a>Syntax

```C
short __cdecl _dclass(double x);
short __cdecl _ldclass(long double x);
short __cdecl _fdclass(float x);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Gleitkomma Funktionsargument.

### <a name="remarks"></a>Hinweise

Diese Gleitkomma-primitive Typen implementieren die C-Versionen der CRT-Makros [Fpclassify](fpclassify.md) für Gleitkomma-Datentypen. Die Klassifizierung des Arguments *x* als eines der folgenden Konstanten, die in math.h definiert zurückgegeben wird:

|Wert|Beschreibung|
|-----------|-----------------|
| **FP_NAN** | Ein stiller, signalisierender oder unbestimmter NaN |
| **FP_INFINITE** | Eine positive oder negative Unendlichkeit |
| **FP_NORMAL** | Ein positiver oder negativer ungleich null normalisierter Wert |
| **FP_SUBNORMAL** | Ein positiver oder negativer subnormal (denormalisierten) Wert |
| **FP_ZERO** | Ein positiver oder negativer Nullwert |

Weitere Informationen können Sie die Microsoft-spezifischen [_fpclass, _fpclassf](fpclass-fpclassf.md) Funktionen. Verwenden der [Fpclassify](fpclassify.md) Makro oder die Funktion zur Portabilität.

## <a name="dsign-ldsign-fdsign"></a>_dsign, _ldsign, _fdsign

### <a name="syntax"></a>Syntax

```C
int __cdecl _dsign(double x);
int __cdecl _ldsign(long double x);
int __cdecl _fdsign(float x);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Gleitkomma Funktionsargument.

### <a name="remarks"></a>Hinweise

Diese Gleitkomma-primitive Typen implementieren die [Signbit](signbit.md) Makro oder in der CRT-Funktion. Sie einen Wert ungleich NULL zurückgeben, wenn das signierte Bit, in der Mantisse (Mantisse) des Arguments festgelegt ist *x*, und 0, wenn das signierte Bit nicht festgelegt ist.

## <a name="dpcomp-ldpcomp-fdpcomp"></a>_dpcomp, _ldpcomp, _fdpcomp

### <a name="syntax"></a>Syntax

```C
int __cdecl _dpcomp(double x, double y);
int __cdecl _ldpcomp(long double x, long double y);
int __cdecl _fdpcomp(float x, float y);
```

### <a name="parameters"></a>Parameter

*x*, *y*<br/>
Gleitkomma-Funktionsargumente.

### <a name="remarks"></a>Hinweise

Diese Gleitkomma-primitive werden zwei Argumente, *x* und *y*, und geben Sie einen Wert, der zeigt, deren Sortierung Beziehungen, ausgedrückt als dem bitweisen oder der folgenden Konstanten, die in math.h definiert zurück:

| Wert | Beschreibung |
|------------|-----------------|
| **_FP_LT** | *X* kann betrachtet werden weniger als *y* |
| **_FP_EQ** | *X* können als gleich betrachtet werden *y* |
| **_FP_GT** | *X* können als größer betrachtet werden *y* |

Diese primitiven implementieren die [Isgreater, Isgreaterequal, Isless, Islessequal, Islessgreater, und Isunordered](floating-point-ordering.md) Makros und Funktionen in der CRT.

## <a name="dtest-ldtest-fdtest"></a>_dtest, _ldtest, _fdtest

### <a name="syntax"></a>Syntax

```C
short __cdecl _dtest(double* px);
short __cdecl _ldtest(long double* px);
short __cdecl _fdtest(float* px);
```

### <a name="parameters"></a>Parameter

*px*<br/>
Zeiger auf ein Gleitkommaargument.

### <a name="remarks"></a>Hinweise

Diese Gleitkomma-primitive implementieren, die C++-Versionen der CRT-Funktion [Fpclassify](fpclassify.md) für Gleitkomma-Datentypen. Das Argument *x* wird ausgewertet, und die Klassifizierung wird zurückgegeben, als eine der folgenden Konstanten, die in math.h definiert sind:

|Wert|Beschreibung|
|-----------|-----------------|
| **FP_NAN** | Ein stiller, signalisierender oder unbestimmter NaN |
| **FP_INFINITE** | Eine positive oder negative Unendlichkeit |
| **FP_NORMAL** | Ein positiver oder negativer ungleich null normalisierter Wert |
| **FP_SUBNORMAL** | Ein positiver oder negativer subnormal (denormalisierten) Wert |
| **FP_ZERO** | Ein positiver oder negativer Nullwert |

Weitere Informationen können Sie die Microsoft-spezifischen [_fpclass, _fpclassf](fpclass-fpclassf.md) Funktionen. Verwenden der [Fpclassify](fpclassify.md) -Funktion für Portabilität.

## <a name="dint-ldint-fdint"></a>_d_int, _ld_int, _fd_int

### <a name="syntax"></a>Syntax

```C
short __cdecl _d_int(double* px, short exp);
short __cdecl _ld_int(long double* px, short exp);
short __cdecl _fd_int(float* px, short exp);
```

### <a name="parameters"></a>Parameter

*px*<br/>
Zeiger auf ein Gleitkommaargument.

*exp*<br/>
Ein Exponent als ganzzahliger Typ.

### <a name="remarks"></a>Hinweise

Diese Gleitkomma-primitive nutzen, einen Zeiger auf einen Gleitkommawert *px* und einen Wert für den Exponenten *"exp"*, und entfernen Sie die Nachkommastellen des Gleitkommawerts unter dem angegebenen Exponenten, falls möglich . Der zurückgegebene Wert ist das Ergebnis des **Fpclassify** auf den Eingabewert in *px* Wenn es sich um NaN oder unendlich ist, und auf den Ausgabewert in *px* andernfalls.

## <a name="dscale-ldscale-fdscale"></a>_dscale, _ldscale, _fdscale

### <a name="syntax"></a>Syntax

```C
short __cdecl _dscale(double* px, long exp);
short __cdecl _ldscale(long double* px, long exp);
short __cdecl _fdscale(float* px, long exp);
```

### <a name="parameters"></a>Parameter

*px*<br/>
Zeiger auf ein Gleitkommaargument.

*exp*<br/>
Ein Exponent als ganzzahliger Typ.

### <a name="remarks"></a>Hinweise

Diese Gleitkomma-primitive nutzen, einen Zeiger auf einen Gleitkommawert *px* und einen Wert für den Exponenten *"exp"*, und skalieren Sie den Wert in *px* durch 2<sup> *"exp"*</sup>, sofern möglich. Der zurückgegebene Wert ist das Ergebnis des **Fpclassify** auf den Eingabewert in *px* Wenn es sich um NaN oder unendlich ist, und auf den Ausgabewert in *px* andernfalls. Zur Portabilität bevorzugen die [Ldexp, Ldexpf, und Ldexpl](ldexp.md) Funktionen.

## <a name="dunscale-ldunscale-fdunscale"></a>_dunscale, _ldunscale, _fdunscale

### <a name="syntax"></a>Syntax

```C
short __cdecl _dunscale(short* pexp, double* px);
short __cdecl _ldunscale(short* pexp, long double* px);
short __cdecl _fdunscale(short* pexp, float* px);
```

### <a name="parameters"></a>Parameter

*pexp*<br/>
Ein Zeiger auf ein Exponent als ganzzahliger Typ.

*px*<br/>
Zeiger auf ein Gleitkommaargument.

### <a name="remarks"></a>Hinweise

Diese Gleitkomma-primitive unterteilen den Gleitkommawert an, auf die von *px* in einer Mantisse (Mantisse) und einen Exponenten, falls möglich. Die Mantisse wird skaliert, sodass der Absolute Wert größer als oder gleich 0,5 und kleiner als 1,0 ist. Der Exponent ist der Wert *n*, wobei die ursprüngliche Gleitkommawert gleich die skalierte Mantisse Mal 2 ist<sup>*n*</sup>. Diese ganzzahlexponent *n* befindet sich in den Speicherort verweist *Pexp*. Der zurückgegebene Wert ist das Ergebnis des **Fpclassify** auf den Eingabewert in *px* Wenn es sich um NaN oder unendlich ist, und auf den Ausgabewert, der andernfalls. Zur Portabilität bevorzugen die [Frexp, Frexpf, Frexpl](frexp.md) Funktionen.

## <a name="dexp-ldexp-fdexp"></a>_dexp, _ldexp, _fdexp

### <a name="syntax"></a>Syntax

```C
short __cdecl _dexp(double* px, double y, long exp);
short __cdecl _ldexp(long double* px, long double y, long exp);
short __cdecl _fdexp(float* px, float y, long exp);
```

### <a name="parameters"></a>Parameter

*y*<br/>
Gleitkomma Funktionsargument.

*px*<br/>
Zeiger auf ein Gleitkommaargument.

*exp*<br/>
Ein Exponent als ganzzahliger Typ.

### <a name="remarks"></a>Hinweise

Erstellen Sie einen Gleitkommawert in den Speicherort an, auf die von dieser Gleitkomma-primitive *px* gleich *y* * 2<sup>*"exp"*</sup>. Der zurückgegebene Wert ist das Ergebnis des **Fpclassify** auf den Eingabewert in *y* Wenn es sich um NaN oder unendlich ist, und auf den Ausgabewert in *px* andernfalls. Zur Portabilität bevorzugen die [Ldexp, Ldexpf, und Ldexpl](ldexp.md) Funktionen.

## <a name="dnorm-fdnorm"></a>_dnorm, _fdnorm

### <a name="syntax"></a>Syntax

```C
short __cdecl _dnorm(unsigned short* ps);
short __cdecl _fdnorm(unsigned short* ps);
```

### <a name="parameters"></a>Parameter

*ps*<br/>
Zeiger auf die bitweise-Darstellung ein Gleitkommawert, ausgedrückt als ein Array von **ohne Vorzeichen** **kurze**.

### <a name="remarks"></a>Hinweise

Diese Gleitkomma-primitive den Bruchteil einer underflowed Gleitkommawert zu normalisieren, und passen Sie die *Merkmal*, oder gewichtete Exponent, übereinstimmen. Der Wert wird übergeben, als die bitweise-Darstellung an der Gleitkommatyp konvertiert in ein Array von **ohne Vorzeichen** **kurze** über die `_double_val`, `_ldouble_val`, oder `_float_val` Typ punning Union, die in math.h deklariert werden. Der Rückgabewert ist das Ergebnis des **Fpclassify** auf der Eingabe Gleitkommawert, wenn es sich um ein NaN oder unendlich ist, und klicken Sie auf der Ausgabewert, der andernfalls.

## <a name="dpoly-ldpoly-fdpoly"></a>_dpoly, _ldpoly, _fdpoly

### <a name="syntax"></a>Syntax

```C
double __cdecl _dpoly(double x, double const* table, int n);
long double __cdecl _ldpoly(long double x, long double const* table, int n);
float __cdecl _fdpoly(float x, _float const* table, int n);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Gleitkomma Funktionsargument.

*table*<br/>
Zeiger auf eine Tabelle mit Konstanten Koeffizienten für eine Polynom.

*n*<br/>
Die Reihenfolge des Polynoms ausgewertet.

### <a name="remarks"></a>Hinweise

Diese Gleitkomma-primitive zurück, die Auswertung von *x* in der Reihenfolge Polynoms *n* , deren Koeffizienten werden durch die entsprechenden Konstanten Werte im dargestellt *Tabelle*. Z. B. wenn *Tabelle*\[0] = 3.0, *Tabelle*\[1] =-4.0 *Tabelle*\[2] = 5.0 und *n* = 2, es stellt die polynomische 5.0 x<sup>2</sup> + 4.0 X + 3.0. Wenn dieser Polynom ausgewertet wird, für die *x* von 2.0, ist das Ergebnis 31,0. Diese Funktionen sind nicht intern verwendet.

## <a name="dlog-dlog-dlog"></a>_dlog, _dlog, _dlog

### <a name="syntax"></a>Syntax

```C
double __cdecl _dlog(double x, int base_flag);
long double __cdecl _ldlog(long double x, int base_flag);
float __cdecl _fdlog(float x, int base_flag);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Gleitkomma Funktionsargument.

*base_flag*<br/>
Flag, das die Basis zu verwenden, 0 für Basis steuert *e* und ungleich NULL für die Basis 10.

### <a name="remarks"></a>Hinweise

Diese Gleitkomma-primitive zurückgeben den natürlichen Logarithmus von *x*, "ln" (*x*) oder<sub>*e*</sub>(*x*), Wenn *Base_flag* ist 0. Sie geben das Protokoll Basis 10 zurück *x*, oder<sub>10</sub>(*x*), wenn *Base_flag* ungleich NULL ist. Diese Funktionen sind nicht intern verwendet. Möchten Sie die Funktionen zur Portabilität [Log, Logf, Logl, log10, log10f und log10l](log-logf-log10-log10f.md).

## <a name="dsin-ldsin-fdsin"></a>_dsin, _ldsin, _fdsin

### <a name="syntax"></a>Syntax

```C
double __cdecl _dsin(double x, unsigned int quadrant);
long double __cdecl _ldsin(long double x, unsigned int quadrant);
float __cdecl _fdsin(float x, unsigned int quadrant);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Gleitkomma Funktionsargument.

*quadrant*<br/>
Quadrant Offset von 0, 1, 2 oder 3 zu verwenden, um zu erzeugen `sin`, `cos`, `-sin`, und `-cos` Ergebnisse.

### <a name="remarks"></a>Hinweise

Diese Gleitkomma-primitive zurück, den Sinus des *x* Offset von der *Quadrant* modulo 4. Effektiv, geben sie den Sinus zurück Kosinus, -Sinus "und"-Kosinus *x* beim *Quadrant* modulo 4 ist 0, 1, 2 oder 3, bzw. Diese Funktionen sind nicht intern verwendet. Zur Portabilität bevorzugen die [sin, Sinf, Sinl](sin-sinf-sinl.md), [cos, Cosf, Cosl, und](cos-cosf-cosl.md) Funktionen.

## <a name="requirements"></a>Anforderungen

Header: \<math.h>

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[frexp, frexpf, frexpl](frexp.md)<br/>
[ldexp, ldexpf, and ldexpl](ldexp.md)<br/>
[log, logf, logl, log10, log10f, log10l](log-logf-log10-log10f.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
