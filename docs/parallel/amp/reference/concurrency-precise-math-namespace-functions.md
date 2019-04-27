---
title: 'Concurrency:: precise_math Namespace-Funktionen'
ms.date: 11/04/2016
f1_keywords:
- amp_math/Concurrency::precise_math::acos
- amp_math/Concurrency::precise_math::acosh
- amp_math/Concurrency::precise_math::acoshf
- amp_math/Concurrency::precise_math::asinf
- amp_math/Concurrency::precise_math::asinh
- amp_math/Concurrency::precise_math::atan
- amp_math/Concurrency::precise_math::atan2
- amp_math/Concurrency::precise_math::atanf
- amp_math/Concurrency::precise_math::atanh
- amp_math/Concurrency::precise_math::cbrt
- amp_math/Concurrency::precise_math::cbrtf
- amp_math/Concurrency::precise_math::ceilf
- amp_math/Concurrency::precise_math::copysign
- amp_math/Concurrency::precise_math::cos
- amp_math/Concurrency::precise_math::cosf
- amp_math/Concurrency::precise_math::coshf
- amp_math/Concurrency::precise_math::cospi
- amp_math/Concurrency::precise_math::erf
- amp_math/Concurrency::precise_math::erfc
- amp_math/Concurrency::precise_math::erfcinv
- amp_math/Concurrency::precise_math::erfcinvf
- amp_math/Concurrency::precise_math::erfinv
- amp_math/Concurrency::precise_math::erfinvf
- amp_math/Concurrency::precise_math::exp10
- amp_math/Concurrency::precise_math::exp10f
- amp_math/Concurrency::precise_math::exp2f
- amp_math/Concurrency::precise_math::expf
- amp_math/Concurrency::precise_math::expm1f
- amp_math/Concurrency::precise_math::fabs
- amp_math/Concurrency::precise_math::floor
- amp_math/Concurrency::precise_math::fdim
- amp_math/Concurrency::precise_math::floorf
- amp_math/Concurrency::precise_math::fmaf
- amp_math/Concurrency::precise_math::fmaxf
- amp_math/Concurrency::precise_math::fmin
- amp_math/Concurrency::precise_math::fmod
- amp_math/Concurrency::precise_math::fmodf
- amp_math/Concurrency::precise_math::frexp
- amp_math/Concurrency::precise_math::frexpf
- amp_math/Concurrency::precise_math::hypotf
- amp_math/Concurrency::precise_math::ilogb
- amp_math/Concurrency::precise_math::isfinite
- amp_math/Concurrency::precise_math::isinf
- amp_math/Concurrency::precise_math::isnormal
- amp_math/Concurrency::precise_math::ldexp
- amp_math/Concurrency::precise_math::lgamma
- amp_math/Concurrency::precise_math::lgammaf
- amp_math/Concurrency::precise_math::log10
- amp_math/Concurrency::precise_math::log10f
- amp_math/Concurrency::precise_math::log1pf
- amp_math/Concurrency::precise_math::log2
- amp_math/Concurrency::precise_math::logb
- amp_math/Concurrency::precise_math::logbf
- amp_math/Concurrency::precise_math::modf
- amp_math/Concurrency::precise_math::modff
- amp_math/Concurrency::precise_math::nanf
- amp_math/Concurrency::precise_math::nearbyint
- amp_math/Concurrency::precise_math::nextafter
- amp_math/Concurrency::precise_math::nextafterf
- amp_math/Concurrency::precise_math::phif
- amp_math/Concurrency::precise_math::pow
- amp_math/Concurrency::precise_math::probit
- amp_math/Concurrency::precise_math::probitf
- amp_math/Concurrency::precise_math::rcbrtf
- amp_math/Concurrency::precise_math::remainder
- amp_math/Concurrency::precise_math::remquo
- amp_math/Concurrency::precise_math::remquof
- amp_math/Concurrency::precise_math::roundf
- amp_math/Concurrency::precise_math::rsqrt
- amp_math/Concurrency::precise_math::scalb
- amp_math/Concurrency::precise_math::scalbf
- amp_math/Concurrency::precise_math::scalbnf
- amp_math/Concurrency::precise_math::signbit
- amp_math/Concurrency::precise_math::sin
- amp_math/Concurrency::precise_math::sincos
- amp_math/Concurrency::precise_math::sinf
- amp_math/Concurrency::precise_math::sinh
- amp_math/Concurrency::precise_math::sinpi
- amp_math/Concurrency::precise_math::sinpif
- amp_math/Concurrency::precise_math::sqrtf
- amp_math/Concurrency::precise_math::tan
- amp_math/Concurrency::precise_math::tanh
- amp_math/Concurrency::precise_math::tanhf
- amp_math/Concurrency::precise_math::tanpif
- amp_math/Concurrency::precise_math::tgamma
- amp_math/Concurrency::precise_math::trunc
- amp_math/Concurrency::precise_math::truncf
ms.assetid: fae53ab4-d1c5-45bb-a6a0-a74258e9aea3
ms.openlocfilehash: 7690c0629e7035d0130f0a7dbdcabf3e959ae7b6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180400"
---
# <a name="concurrencyprecisemath-namespace-functions"></a>Concurrency:: precise_math Namespace-Funktionen

||||
|-|-|-|
|[acos](#acos)|[acosf](#acosf)|[acosh](#acosh)|
|[acoshf](#acoshf)|[asin](#asin)|[asinf](#asinf)|
|[asinh](#asinh)|[asinhf](#asinhf)|[atan](#atan)|
|[atan2](#atan2)|[atan2f](#atan2f)|[atanf](#atanf)|
|[atanh](#atanh)|[atanhf](#atanhf)|[cbrt](#cbrt)|
|[cbrtf](#cbrtf)|[ceil](#ceil)|[ceilf](#ceilf)|
|[copysign](#copysign)|[copysignf](#copysignf)|[cos](#cos)|
|[cosf](#cosf)|[cosh](#cosh)|[coshf](#coshf)|
|[cospi](#cospi)|[cospif](#cospif)|[erf](#erf)|
|[erfc](#erfc)|[erfcf](#erfcf)|[erfcinv](#erfcinv)|
|[erfcinvf](#erfcinvf)|[erff](#erff)|[erfinv](#erfinv)|
|[erfinvf](#erfinvf)|[exp](#exp)|[exp10](#exp10)|
|[exp10f](#exp10f)|[exp2](#exp2)|[exp2f](#exp2f)|
|[expf](#expf)|[expm1](#expm1)|[expm1f](#expm1f)|
|[fabs](#fabs)|[fabsf](#fabsf)|[floor](#floor)|
|[fdim](#fdim)|[fdimf](#fdimf)||
|[floorf](#floorf)|[fma](#fma)|[fmaf](#fmaf)|
[fmax](#fmax)|[fmaxf](#fmaxf)||
|[fmin](#fmin)|[fminf](#fminf)|[fmod](#fmod)|
|[fmodf](#fmodf)|[fpclassify](#fpclassify)|[frexp](#frexp)|
|[frexpf](#frexpf)|[hypot](#hypot)|[hypotf](#hypotf)|
|[ilogb](#ilogb)|[ilogbf](#ilogbf)|[isfinite](#isfinite)|
|[isinf](#isinf)|[isnan](#isnan)|[isnormal](#isnormal)|
|[ldexp](#ldexp)|[ldexpf](#ldexpf)|[lgamma](#lgamma)|
|[lgammaf](#lgammaf)|[log](#log)|[log10](#log10)|
|[log10f](#log10f)|[log1p](#log1p)|[log1pf](#log1pf)|
|[log2](#log2)|[log2f](#log2f)|[logb](#logb)|
|[logbf](#logbf)|[logf](#logf)|[modf](#modf)|
|[modff](#modff)|[nan](#nan)|[nanf](#nanf)|
|[nearbyint](#nearbyint)|[nearbyintf](#nearbyintf)|[nextafter](#nextafter)|
|[nextafterf](#nextafterf)|[phi](#phi)|[phif](#phif)|
|[pow](#pow)|[powf](#powf)|[probit](#probit)|
|[probitf](#probitf)|[rcbrt](#rcbrt)|[rcbrtf](#rcbrtf)|
|[remainder](#remainder)|[remainderf](#remainderf)|[remquo](#remquo)|
|[remquof](#remquof)|[round](#round)|[roundf](#roundf)|
|[rsqrt](#rsqrt)|[rsqrtf](#rsqrtf)|[scalb](#scalb)|
|[scalbf](#scalbf)|[scalbn](#scalbn)|[scalbnf](#scalbnf)|
|[signbit](#signbit)|[signbitf](#signbitf)|[sin](#sin)|
|[sincos](#sincos)|[sincosf](#sincosf)|[sinf](#sinf)|
|[sinh](#sinh)|[sinhf](#sinhf)|[sinpi](#sinpi)|
|[sinpif](#sinpif)|[sqrt](#sqrt)|[sqrtf](#sqrtf)|
|[tan](#tan)|[tanf](#tanf)|[tanh](#tanh)|
|[tanhf](#tanhf)|[tanpi](#tanpi)|[tanpif](#tanpif)|
|[tgamma](#tgamma)|[tgammaf](#tgammaf)|[trunc](#trunc)|
|[truncf](#truncf)|

##  <a name="acos"></a> acos

Berechnet den Arkuskosinus des Arguments

```
inline float acos(float _X) restrict(amp);

inline double acos(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den arkuskosinuswert des Arguments zurück

##  <a name="acosf"></a>  acosf

Berechnet den Arkuskosinus des Arguments

```
inline float acosf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den arkuskosinuswert des Arguments zurück

##  <a name="acosh"></a>  Acosh

Berechnet den umgekehrten hyperbolischen Kosinus des Arguments

```
inline float acosh(float _X) restrict(amp);

inline double acosh(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Wert der umgekehrte hyperbolische Kosinus des Arguments zurück

##  <a name="acoshf"></a>  acoshf

Berechnet den umgekehrten hyperbolischen Kosinus des Arguments

```
inline float acoshf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Wert der umgekehrte hyperbolische Kosinus des Arguments zurück

##  <a name="asin"></a> asin

Berechnet den Arkussinus des Arguments

```
inline float asin(float _X) restrict(amp);

inline double asin(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den arkussinuswert des Arguments zurück

##  <a name="asinf"></a>  asinf

Berechnet den Arkussinus des Arguments

```
inline float asinf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den arkussinuswert des Arguments zurück

##  <a name="asinh"></a>  Asinh

Berechnet den umgekehrten hyperbolischen Sinus des Arguments

```
inline float asinh(float _X) restrict(amp);

inline double asinh(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Wert der umgekehrten hyperbolischen Sinus des Arguments zurück

##  <a name="asinhf"></a>  asinhf

Berechnet den umgekehrten hyperbolischen Sinus des Arguments

```
inline float asinhf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Wert der umgekehrten hyperbolischen Sinus des Arguments zurück

##  <a name="atan"></a> atan

Berechnet den Arkustangens des Arguments

```
inline float atan(float _X) restrict(amp);

inline double atan(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Arkustangens-Wert des Arguments zurück

##  <a name="atan2"></a> atan2

Berechnet den Arkustangens von _Y/_X

```
inline float atan2(
    float _Y,
    float _X) restrict(amp);

inline double atan2(
    double _Y,
    double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_Y*<br/>
Gleitkommawert

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Arkustangens-Wert von _Y/_X

##  <a name="atan2f"></a>  atan2f

Berechnet den Arkustangens von _Y/_X

```
inline float atan2f(
    float _Y,
    float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_Y*<br/>
Gleitkommawert

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Arkustangens-Wert von _Y/_X

##  <a name="atanf"></a>  atanf

Berechnet den Arkustangens des Arguments

```
inline float atanf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Arkustangens-Wert des Arguments zurück

##  <a name="atanh"></a>  Atanh

Berechnet den umgekehrten hyperbolischen Tangens des Arguments

```
inline float atanh(float _X) restrict(amp);

inline double atanh(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den umgekehrten hyperbolischen Tangenswert des Arguments

##  <a name="atanhf"></a>  atanhf

Berechnet den umgekehrten hyperbolischen Tangens des Arguments

```
inline float atanhf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den umgekehrten hyperbolischen Tangenswert des Arguments

##  <a name="cbrt"></a>  cbrt

Berechnet die Kubikwurzel real, des Arguments

```
inline float cbrt(float _X) restrict(amp);

inline double cbrt(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt zurück, die echte Kubikwurzel des Arguments

##  <a name="cbrtf"></a>  cbrtf

Berechnet die Kubikwurzel real, des Arguments

```
inline float cbrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt zurück, die echte Kubikwurzel des Arguments

##  <a name="ceil"></a>  ceil-

Berechnet die Höchstwert des Arguments

```
inline float ceil(float _X) restrict(amp);

inline double ceil(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Höchstwert des Arguments

##  <a name="ceilf"></a>  ceilf

Berechnet die Höchstwert des Arguments

```
inline float ceilf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Höchstwert des Arguments

##  <a name="copysign"></a>  copysign

Dieser Wert mit die Größe von _X und das Vorzeichen von _Y

```
inline float copysign(
    float _X,
    float _Y) restrict(amp);

inline double copysign(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_Y*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt einen Wert mit die Größe von _X und das Vorzeichen von _Y zurück

##  <a name="copysignf"></a>  copysignf

Dieser Wert mit die Größe von _X und das Vorzeichen von _Y

```
inline float copysignf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_Y*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt einen Wert mit die Größe von _X und das Vorzeichen von _Y zurück

##  <a name="cos"></a> cos

Berechnet den Kosinus des Arguments

```
inline float cos(float _X) restrict(amp);

inline double cos(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Kosinuswert des Arguments zurück

##  <a name="cosf"></a>  cosf

Berechnet den Kosinus des Arguments

```
inline float cosf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Kosinuswert des Arguments zurück

##  <a name="cosh"></a> cosh

Berechnet den Hyperbelkosinuswert des Arguments

```
inline float cosh(float _X) restrict(amp);

inline double cosh(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den hyperbolischen Kosinus-Wert des Arguments zurück

##  <a name="coshf"></a>  coshf

Berechnet den Hyperbelkosinuswert des Arguments

```
inline float coshf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den hyperbolischen Kosinus-Wert des Arguments zurück

##  <a name="cospi"></a>  cospi

Berechnet den Kosinus-Wert von Pi \* _X

```
inline float cospi(float _X) restrict(amp);

inline double cospi(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Kosinuswert von Pi zurück \* _X

##  <a name="cospif"></a>  cospif

Berechnet den Kosinus-Wert von Pi \* _X

```
inline float cospif(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Kosinuswert von Pi zurück \* _X

##  <a name="erf"></a>  Erf

Berechnet die Fehlerfunktion von _X

```
inline float erf(float _X) restrict(amp);

inline double erf(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die Error-Funktion von _X

##  <a name="erfc"></a>  ErfC

Berechnet die komplementäre Fehlerfunktion von _X

```
inline float erfc(float _X) restrict(amp);

inline double erfc(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt zurück, die komplementäre Fehlerfunktion von _X

##  <a name="erfcf"></a>  erfcf

Berechnet die komplementäre Fehlerfunktion von _X

```
inline float erfcf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt zurück, die komplementäre Fehlerfunktion von _X

##  <a name="erfcinv"></a>  erfcinv

Berechnet die inverse komplementäre Fehlerfunktion von _X

```
inline float erfcinv(float _X) restrict(amp);

inline double erfcinv(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die inverse komplementäre Fehlerfunktion von _X

##  <a name="erfcinvf"></a>  erfcinvf

Berechnet die inverse komplementäre Fehlerfunktion von _X

```
inline float erfcinvf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die inverse komplementäre Fehlerfunktion von _X

##  <a name="erff"></a>  erff

Berechnet die Fehlerfunktion von _X

```
inline float erff(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die Error-Funktion von _X

##  <a name="erfinv"></a>  erfinv

Berechnet die inverse Fehlerfunktion von _X

```
inline float erfinv(float _X) restrict(amp);

inline double erfinv(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die inverse Error-Funktion von _X

##  <a name="erfinvf"></a>  erfinvf

Berechnet die inverse Fehlerfunktion von _X

```
inline float erfinvf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die inverse Error-Funktion von _X

##  <a name="exp10"></a>  exp10

Berechnet die Basis-10-vom Argument exponential ist

```
inline float exp10(float _X) restrict(amp);

inline double exp10(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die Base-10-vom Argument exponential ist

##  <a name="exp10f"></a>  exp10f

Berechnet die Basis-10-vom Argument exponential ist

```
inline float exp10f(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die Base-10-vom Argument exponential ist

##  <a name="expm1"></a>  expm1

Berechnet die Basis-E, die vom Argument exponential ist, minus 1

```
inline float expm1(float exponent) restrict(amp);

inline double expm1(double exponent) restrict(amp);
```

### <a name="parameters"></a>Parameter

*exponent*<br/>
Der Exponent *n* des mathematischen Ausdrucks `e` <sup>n</sup>, wobei `e` ist die Basis des natürlichen Logarithmus.

### <a name="return-value"></a>Rückgabewert

Gibt die Basis-E, die vom Argument exponential ist, minus 1 zurück

##  <a name="expm1f"></a>  expm1f

Berechnet die Basis-E, die vom Argument exponential ist, minus 1

```
inline float expm1f(float exponent) restrict(amp);
```

### <a name="parameters"></a>Parameter

*exponent*<br/>
Der Exponent *n* des mathematischen Ausdrucks `e` <sup>n</sup>, wobei `e` ist die Basis des natürlichen Logarithmus.

### <a name="return-value"></a>Rückgabewert

Gibt die Basis-E, die vom Argument exponential ist, minus 1 zurück

##  <a name="exp"></a> exp

Berechnet die Basis-E, die vom Argument exponential ist

```
inline float exp(float _X) restrict(amp);

inline double exp(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die Basis-e-vom Argument exponential ist

##  <a name="expf"></a>  expf

Berechnet die Basis-E, die vom Argument exponential ist

```
inline float expf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die Basis-e-vom Argument exponential ist

##  <a name="exp2"></a>  EXP2

Berechnet die Basis-2, die vom Argument exponential ist

```
inline float exp2(float _X) restrict(amp);

inline double exp2(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die Basis-2-vom Argument exponential ist

##  <a name="exp2f"></a>  exp2f

Berechnet die Basis-2, die vom Argument exponential ist

```
inline float exp2f(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die Basis-2-vom Argument exponential ist

##  <a name="fabs"></a>  Fabs

Gibt den absoluten Wert des Arguments zurück.

```
inline float fabs(float _X) restrict(amp);

inline double fabs(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den absoluten Wert des Arguments zurück.

##  <a name="fabsf"></a>  fabsf

Gibt den absoluten Wert des Arguments zurück.

```
inline float fabsf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den absoluten Wert des Arguments zurück.

## <a name="fdim"></a> fdim

Berechnet den positiven Unterschied zwischen den Argumenten.
```
inline float fdim(
   float _X,
   float _Y
) restrict(amp);
inline double fdim(
   double _X,
   double _Y
) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert *_Y*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Der Unterschied zwischen _X und _Y, wenn _X größer als _Y ist; andernfalls, + 0.

## <a name="fdimf"></a> fdimf

Berechnet den positiven Unterschied zwischen den Argumenten.
```
inline float fdimf(
   float _X,
   float _Y
) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert *_Y*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Der Unterschied zwischen _X und _Y, wenn _X größer als _Y ist; andernfalls, + 0.

##  <a name="floor"></a>  Floor

Berechnet den Tiefstwert des Arguments

```
inline float floor(float _X) restrict(amp);

inline double floor(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Tiefstwert des Arguments

##  <a name="floorf"></a>  floorf

Berechnet den Tiefstwert des Arguments

```
inline float floorf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Tiefstwert des Arguments

## <a name="a-namefma-fma"></a><a name="fma"> fma

Berechnet das Produkt des ersten und zweiten angegebenen Arguments, fügt dann das dritte angegebene Argument dem Ergebnis hinzu. Die gesamte Berechnung wird als einzelner Vorgang ausgeführt.
```
inline float fma(
   float _X,
   float _Y,
   float _Z
) restrict(amp);

inline double fma(
   double _X,
   double _Y,
   double _Z
) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Das erste Gleitkommaargument.
*_Y*<br/>
Das zweite Gleitkommaargument.
*_Z*<br/>
Das dritte Gleitkommaargument.

### <a name="return-value"></a>Rückgabewert

Das Ergebnis des Ausdrucks (_X \* _Y) + _Z. Die gesamte Berechnung wird als einzelner Vorgang ausgeführt; das heißt, die Teilausdrücke werden mit unendlicher Genauigkeit berechnet und nur das Endergebnis wird gerundet.

## <a name="fmaf"></a> fmaf

Berechnet das Produkt des ersten und zweiten angegebenen Arguments, fügt dann das dritte angegebene Argument dem Ergebnis hinzu. Die gesamte Berechnung wird als einzelner Vorgang ausgeführt.
```
inline float fmaf(
   float _X,
   float _Y,
   float _Z
) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Das erste Gleitkommaargument.
*_Y*<br/>
Das zweite Gleitkommaargument.
*_Z*<br/>
Das dritte Gleitkommaargument.

### <a name="return-value"></a>Rückgabewert

Das Ergebnis des Ausdrucks (_X \* _Y) + _Z. Die gesamte Berechnung wird als einzelner Vorgang ausgeführt; das heißt, die Teilausdrücke werden mit unendlicher Genauigkeit berechnet und nur das Endergebnis wird gerundet.

##  <a name="fmax"></a>  Fmax

Festlegung des höchsten numerischen Werts der Argumente

```
inline float fmax(
    float _X,
    float _Y) restrict(amp);

inline double fmax(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_Y*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Rückgabe des höchsten numerischen Werts der Argumente

##  <a name="fmaxf"></a>  fmaxf

Festlegung des höchsten numerischen Werts der Argumente

```
inline float fmaxf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_Y*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Rückgabe des höchsten numerischen Werts der Argumente

##  <a name="fmin"></a>  fmin

Festlegung des niedrigsten numerischen Werts der Argumente

```
inline float fmin(
    float _X,
    float _Y) restrict(amp);

inline double fmin(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_Y*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Rückgabe des niedrigsten numerischen Werts der Argumente

##  <a name="fminf"></a>  fminf

Festlegung des niedrigsten numerischen Werts der Argumente

```
inline float fminf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_Y*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Rückgabe des niedrigsten numerischen Werts der Argumente

##  <a name="fmod"></a>  Fmod-Funktion (C++-AMP)

Berechnet den Rest des angegebenen ersten Arguments dividiert durch das zweite angegebene Argument.

```
inline float fmod(
    float _X,
    float _Y) restrict(amp);

inline double fmod(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Das erste Gleitkommaargument.

*_Y*<br/>
Das zweite Gleitkommaargument.

### <a name="return-value"></a>Rückgabewert

Die restlichen `_X` geteilt durch `_Y`; also den Wert der `_X`  -  `_Y` *n*, wobei *n* ist eine ganze Zahl, die Größe der `_X`  -  `_Y` *n* ist kleiner als die Größe der `_Y`.

##  <a name="fmodf"></a>  fmodf

Berechnet den Rest des angegebenen ersten Arguments dividiert durch das zweite angegebene Argument.

```
inline float fmodf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Das erste Gleitkommaargument.

*_Y*<br/>
Das zweite Gleitkommaargument.

### <a name="return-value"></a>Rückgabewert

Die restlichen `_X` geteilt durch `_Y`; also den Wert der `_X`  -  `_Y` *n*, wobei *n* ist eine ganze Zahl, die Größe der `_X`  -  `_Y` *n* ist kleiner als die Größe der `_Y`.

##  <a name="fpclassify"></a>  fpclassify

Klassifiziert den Wert des Arguments, wie NULL, NaN, unendlich, Normal, subnormal,

```
inline int fpclassify(float _X) restrict(amp);

inline int fpclassify(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Wert des Makros Klassifizierung Zahl auf den Wert des Arguments zurück.

##  <a name="frexp"></a>  frexp

Ruft die Mantisse und den Exponenten von _X ab

```
inline float frexp(
    float _X,
    _Out_ int* _Exp) restrict(amp);

inline double frexp(
    double _X,
    _Out_ int* _Exp) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_Exp*<br/>
Gibt den ganzzahligen Exponenten von _X in Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die Mantisse _X

##  <a name="frexpf"></a>  frexpf

Ruft die Mantisse und den Exponenten von _X ab

```
inline float frexpf(
    float _X,
    _Out_ int* _Exp) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_Exp*<br/>
Gibt den ganzzahligen Exponenten von _X in Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die Mantisse _X

##  <a name="hypot"></a>  hypot

Berechnet die Quadratwurzel der Summe der Quadrate von _X und _Y

```
inline float hypot(
    float _X,
    float _Y) restrict(amp);

inline double hypot(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_Y*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die Quadratwurzel der Summe der Quadrate von _X und _Y zurück

##  <a name="hypotf"></a>  hypotf

Berechnet die Quadratwurzel der Summe der Quadrate von _X und _Y

```
inline float hypotf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_Y*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die Quadratwurzel der Summe der Quadrate von _X und _Y zurück

##  <a name="ilogb"></a>  ilogb

Extrahieren Sie den Exponenten von _X als signierte Int-Wert

```
inline int ilogb(float _X) restrict(amp);

inline int ilogb(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Exponenten von _X als signierte Int-Wert

##  <a name="ilogbf"></a>  ilogbf

Extrahieren Sie den Exponenten von _X als signierte Int-Wert

```
inline int ilogbf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Exponenten von _X als signierte Int-Wert

##  <a name="isfinite"></a>  isFinite

Bestimmt, ob das Argument einen über begrenzten Wert verfügt

```
inline int isfinite(float _X) restrict(amp);

inline int isfinite(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt einen Wert ungleich NULL zurück, wenn das Argument einen über begrenzten Wert verfügt

##  <a name="isinf"></a>  isinf

Bestimmt, ob das Argument unendlich ist

```
inline int isinf(float _X) restrict(amp);

inline int isinf(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt einen Wert ungleich NULL zurück, wenn und nur wenn das Argument einen unendlichen Wert verfügt.

##  <a name="isnan"></a>  IsNaN

Bestimmt, ob das Argument ein NaN

```
inline int isnan(float _X) restrict(amp);

inline int isnan(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt einen Wert ungleich NULL zurück, wenn und nur wenn das Argument einen NaN-Wert verfügt.

##  <a name="isnormal"></a>  isnormal

Bestimmt, ob das Argument ein normaler

```
inline int isnormal(float _X) restrict(amp);

inline int isnormal(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt einen Wert ungleich NULL zurück, wenn das Argument einen normalen Wert verfügt

##  <a name="ldexp"></a>  ldexp

Berechnet eine reelle Zahl aus der angegebenen Mantisse und dem Exponent.

```
inline float ldexp(
    float _X,
    int _Exp) restrict(amp);

inline double ldexp(
    double _X,
    double _Exp) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert, Mantisse

*_Exp*<br/>
Ganze Zahl, Exponent

### <a name="return-value"></a>Rückgabewert

Gibt _X \* 2 ^ _EXP zurück

##  <a name="ldexpf"></a>  ldexpf

Berechnet eine reelle Zahl aus der angegebenen Mantisse und dem Exponent.

```
inline float ldexpf(
    float _X,
    int _Exp) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert, Mantisse

*_Exp*<br/>
Ganze Zahl, Exponent

### <a name="return-value"></a>Rückgabewert

Gibt _X \* 2 ^ _EXP zurück

##  <a name="lgamma"></a>  lgamma

Berechnet den natürlichen Logarithmus des absoluten Werts der Gammafunktion des Arguments

```
inline float lgamma(
    float _X,
    _Out_ int* _Sign) restrict(amp);

inline double lgamma(
    double _X,
    _Out_ int* _Sign) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_Sign*<br/>
Gibt das Vorzeichen

### <a name="return-value"></a>Rückgabewert

Gibt den natürlichen Logarithmus des absoluten Werts der Gammafunktion des Arguments

##  <a name="lgammaf"></a>  lgammaf

Berechnet den natürlichen Logarithmus des absoluten Werts der Gammafunktion des Arguments

```
inline float lgammaf(
    float _X,
    _Out_ int* _Sign) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_Sign*<br/>
Gibt das Vorzeichen

### <a name="return-value"></a>Rückgabewert

Gibt den natürlichen Logarithmus des absoluten Werts der Gammafunktion des Arguments

##  <a name="log"></a> log

Berechnet den Basis-E-Logarithmus des Arguments

```
inline float log(float _X) restrict(amp);

inline double log(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die Basis-e-Logarithmus des Arguments

##  <a name="log10"></a> log10

Berechnet den Basis-10-Logarithmus des Arguments

```
inline float log10(float _X) restrict(amp);

inline double log10(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die Base-10-Logarithmus des Arguments

##  <a name="log10f"></a>  log10f

Berechnet den Basis-10-Logarithmus des Arguments

```
inline float log10f(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die Base-10-Logarithmus des Arguments

##  <a name="log1p"></a>  log1p

Berechnet die Basis-e-Logarithmus von 1 plus das argument

```
inline float log1p(float _X) restrict(amp);

inline double log1p(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die Basis-e-Logarithmus von 1 plus das argument

##  <a name="log1pf"></a>  log1pf

Berechnet die Basis-e-Logarithmus von 1 plus das argument

```
inline float log1pf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die Basis-e-Logarithmus von 1 plus das argument

##  <a name="log2"></a>  Log2

Berechnet den Basis-2-Logarithmus des Arguments

```
inline float log2(float _X) restrict(amp);

inline double log2(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die Base-10-Logarithmus des Arguments

##  <a name="log2f"></a>  log2f

Berechnet den Basis-2-Logarithmus des Arguments

```
inline float log2f(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die Base-10-Logarithmus des Arguments

##  <a name="logb"></a>  logb

Extrahiert den Exponenten von _X, als eine Ganzzahl mit Vorzeichen im Gleitkommaformat

```
inline float logb(float _X) restrict(amp);

inline double logb(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt zurück, die mit Exponenten von _X

##  <a name="logbf"></a>  logbf

Extrahiert den Exponenten von _X, als eine Ganzzahl mit Vorzeichen im Gleitkommaformat

```
inline float logbf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt zurück, die mit Exponenten von _X

##  <a name="logf"></a>  logf

Berechnet den Basis-E-Logarithmus des Arguments

```
inline float logf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die Basis-e-Logarithmus des Arguments

##  <a name="modf"></a>  modf

Teilt das angegebene Argument in Brüche und ganzzahlige Teile.

```
inline float modf(
    float _X,
    _Out_ float* _Iptr) restrict(amp);

inline double modf(
    double _X,
    _Out_ double* _Iptr) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_Iptr*<br/>
[out] Der ganzzahlige Teil von `_X`, als Gleitkommawert.

### <a name="return-value"></a>Rückgabewert

Der Bruchteil von `_X` mit Vorzeichen.

##  <a name="modff"></a>  modff

Teilt das angegebene Argument in Brüche und ganzzahlige Teile.

```
inline float modff(
    float _X,
    _Out_ float* _Iptr) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_Iptr*<br/>
Der ganzzahlige Teil von `_X` als Gleitkommawert.

### <a name="return-value"></a>Rückgabewert

Gibt den Bruchteil mit Vorzeichen von `_X` zurück.

##  <a name="nan"></a>  NaN

Gibt ein stilles NaN

```
inline double nan(int _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Ganzzahliger Wert

### <a name="return-value"></a>Rückgabewert

Gibt ein stilles NaN, zurück, wenn verfügbar, mit dem Inhalt in _X

##  <a name="nanf"></a>  nanf

Gibt ein stilles NaN

```
inline float nanf(int _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Ganzzahliger Wert

### <a name="return-value"></a>Rückgabewert

Gibt ein stilles NaN, zurück, wenn verfügbar, mit dem Inhalt in _X

##  <a name="nearbyint"></a>  nearbyint

Rundet das Argument in einen ganzzahligen Wert im Gleitkommaformat, mit der aktuellen rundungsrichtung an.

```
inline float nearbyint(float _X) restrict(amp);

inline double nearbyint(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Der gerundete Ganzzahlwert zurückgegeben.

##  <a name="nearbyintf"></a>  nearbyintf

Rundet das Argument in einen ganzzahligen Wert im Gleitkommaformat, mit der aktuellen rundungsrichtung an.

```
inline float nearbyintf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Der gerundete Ganzzahlwert zurückgegeben.

##  <a name="nextafter"></a>  nextafter

Bestimmen Sie den nächsten darstellbaren Wert, im Typ der Funktion, nach _X in Richtung _Y

```
inline float nextafter(
    float _X,
    float _Y) restrict(amp);

inline double nextafter(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_Y*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den nächsten darstellbaren Wert, im Typ der Funktion, nach _X in Richtung _Y zurück

##  <a name="nextafterf"></a>  nextafterf

Bestimmen Sie den nächsten darstellbaren Wert, im Typ der Funktion, nach _X in Richtung _Y

```
inline float nextafterf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_Y*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den nächsten darstellbaren Wert, im Typ der Funktion, nach _X in Richtung _Y zurück

##  <a name="phi"></a>  Phi

Die kumulative Verteilungsfunktion des Arguments zurück

```
inline float phi(float _X) restrict(amp);

inline double phi(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Die kumulative Verteilungsfunktion des Arguments zurück

##  <a name="phif"></a>  phif

Die kumulative Verteilungsfunktion des Arguments zurück

```
inline float phif(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Die kumulative Verteilungsfunktion des Arguments zurück

##  <a name="pow"></a> pow

Berechnet _X potenziert mit _Y

```
inline float pow(
    float _X,
    float _Y) restrict(amp);

inline double pow(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert, Basis

*_Y*<br/>
Gleitkommawert, exponent

### <a name="return-value"></a>Rückgabewert

##  <a name="powf"></a>  powf

Berechnet _X potenziert mit _Y

```
inline float powf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert, Basis

*_Y*<br/>
Gleitkommawert, exponent

### <a name="return-value"></a>Rückgabewert

##  <a name="probit"></a>  probit

Gibt die inverse kumulative Verteilungsfunktion des Arguments

```
inline float probit(float _X) restrict(amp);

inline double probit(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die inverse kumulative Verteilungsfunktion des Arguments

##  <a name="probitf"></a>  probitf

Gibt die inverse kumulative Verteilungsfunktion des Arguments

```
inline float probitf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die inverse kumulative Verteilungsfunktion des Arguments

##  <a name="rcbrt"></a>  rcbrt

Gibt den Kehrwert der die Kubikwurzel des Arguments

```
inline float rcbrt(float _X) restrict(amp);

inline double rcbrt(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Kehrwert der die Kubikwurzel des Arguments

##  <a name="rcbrtf"></a>  rcbrtf

Gibt den Kehrwert der die Kubikwurzel des Arguments

```
inline float rcbrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Kehrwert der die Kubikwurzel des Arguments

##  <a name="remainder"></a>  Rest

Berechnet den Rest: _X REM _Y

```
inline float remainder(
    float _X,
    float _Y) restrict(amp);

inline double remainder(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_Y*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Returns _X REM _Y

##  <a name="remainderf"></a>  remainderf

Berechnet den Rest: _X REM _Y

```
inline float remainderf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_Y*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Returns _X REM _Y

##  <a name="remquo"></a>  remquo

Berechnet den Rest des angegebenen ersten Arguments dividiert durch das zweite angegebene Argument. Berechnet auch den Quotient der angegebenen Mantisse des ersten Arguments, dividiert durch die Mantisse des zweiten angegebenen Arguments und gibt den Quotient mithilfe der im dritten Argument angegebenen Position zurück.

```
inline float remquo(
    float _X,
    float _Y,
    _Out_ int* _Quo) restrict(amp);

inline double remquo(
    double _X,
    double _Y,
    _Out_ int* _Quo) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Das erste Gleitkommaargument.

*_Y*<br/>
Das zweite Gleitkommaargument.

*_Quo*<br/>
[out] Die Adresse einer ganzen Zahl, die verwendet wird, um den Quotient der bruchbytes von zurückzugeben `_X` geteilt durch die bruchbytes von `_Y`.

### <a name="return-value"></a>Rückgabewert

Gibt den Rest von `_X` dividiert durch `_Y` zurück.

##  <a name="remquof"></a>  remquof

Berechnet den Rest des angegebenen ersten Arguments dividiert durch das zweite angegebene Argument. Berechnet auch den Quotient der angegebenen Mantisse des ersten Arguments, dividiert durch die Mantisse des zweiten angegebenen Arguments und gibt den Quotient mithilfe der im dritten Argument angegebenen Position zurück.

```
inline float remquof(
    float _X,
    float _Y,
    _Out_ int* _Quo) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Das erste Gleitkommaargument.

*_Y*<br/>
Das zweite Gleitkommaargument.

*_Quo*<br/>
[out] Die Adresse einer ganzen Zahl, die verwendet wird, um den Quotient der bruchbytes von zurückzugeben `_X` geteilt durch die bruchbytes von `_Y`.

### <a name="return-value"></a>Rückgabewert

Gibt den Rest von `_X` dividiert durch `_Y` zurück.

##  <a name="round"></a>  Roundrobin

Rundet _X auf die nächste ganze Zahl

```
inline float round(float _X) restrict(amp);

inline double round(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die nächste ganze Zahl von _X

##  <a name="roundf"></a>  roundf

Rundet _X auf die nächste ganze Zahl

```
inline float roundf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die nächste ganze Zahl von _X

##  <a name="rsqrt"></a>  rsqrt

Gibt den Kehrwert der Quadratwurzel des Arguments zurück

```
inline float rsqrt(float _X) restrict(amp);

inline double rsqrt(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Kehrwert der Quadratwurzel des Arguments zurück

##  <a name="rsqrtf"></a>  rsqrtf

Gibt den Kehrwert der Quadratwurzel des Arguments zurück

```
inline float rsqrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Kehrwert der Quadratwurzel des Arguments zurück

##  <a name="scalb"></a>  scalb

Multipliziert _X von FLT_RADIX an die Power-_Y

```
inline float scalb(
    float _X,
    float _Y) restrict(amp);

inline double scalb(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_Y*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Returns _X \* (FLT_RADIX ^ _Y)

##  <a name="scalbf"></a>  scalbf

Multipliziert _X von FLT_RADIX an die Power-_Y

```
inline float scalbf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_Y*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Returns _X \* (FLT_RADIX ^ _Y)

##  <a name="scalbn"></a>  scalbn

Multipliziert _X von FLT_RADIX an die Power-_Y

```
inline float scalbn(
    float _X,
    int _Y) restrict(amp);

inline double scalbn(
    double _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_Y*<br/>
Ganzzahliger Wert

### <a name="return-value"></a>Rückgabewert

Returns _X \* (FLT_RADIX ^ _Y)

##  <a name="scalbnf"></a>  scalbnf

Multipliziert _X von FLT_RADIX an die Power-_Y

```
inline float scalbnf(
    float _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_Y*<br/>
Ganzzahliger Wert

### <a name="return-value"></a>Rückgabewert

Returns _X \* (FLT_RADIX ^ _Y)

##  <a name="signbit"></a>  signbit

Bestimmt, ob die Vorzeichen von _X negativ ist.

```
inline int signbit(float _X) restrict(amp);

inline int signbit(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt einen Wert ungleich NULL zurück, wenn die Vorzeichen von _X negativ ist.

##  <a name="signbitf"></a>  signbitf

Bestimmt, ob die Vorzeichen von _X negativ ist.

```
inline int signbitf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt einen Wert ungleich NULL zurück, wenn die Vorzeichen von _X negativ ist.

##  <a name="sin"></a> sin

Berechnet den Sinuswert des Arguments

```
inline float sin(float _X) restrict(amp);

inline double sin(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Sinuswert des Arguments

##  <a name="sinf"></a>  sinf

Berechnet den Sinuswert des Arguments

```
inline float sinf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Sinuswert des Arguments

##  <a name="sincos"></a>  sincos

Berechnet Sinus- und Kosinuswert von _X

```
inline void sincos(
    float _X,
    _Out_ float* _S,
    _Out_ float* _C) restrict(amp);

inline void sincos(
    double _X,
    _Out_ double* _S,
    _Out_ double* _C) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_S*<br/>
Gibt den Sinuswert von _X

*_C*<br/>
Gibt den Kosinuswert von _X

##  <a name="sincosf"></a>  sincosf

Berechnet Sinus- und Kosinuswert von _X

```
inline void sincosf(
    float _X,
    _Out_ float* _S,
    _Out_ float* _C) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

*_S*<br/>
Gibt den Sinuswert von _X

*_C*<br/>
Gibt den Kosinuswert von _X

##  <a name="sinh"></a> sinh

Berechnet den Hyperbelsinuswert des Arguments

```
inline float sinh(float _X) restrict(amp);

inline double sinh(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den hyperbolischen Sinus-Wert des Arguments zurück

##  <a name="sinhf"></a>  sinhf

Berechnet den Hyperbelsinuswert des Arguments

```
inline float sinhf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den hyperbolischen Sinus-Wert des Arguments zurück

##  <a name="sinpi"></a>  sinpi

Berechnet den Sinuswert von Pi \* _X

```
inline float sinpi(float _X) restrict(amp);

inline double sinpi(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Sinuswert von Pi zurück \* _X

##  <a name="sinpif"></a>  sinpif

Berechnet den Sinuswert von Pi \* _X

```
inline float sinpif(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Sinuswert von Pi zurück \* _X

##  <a name="sqrt"></a> sqrt

Berechnet den Squre Stamm des Arguments

```
inline float sqrt(float _X) restrict(amp);

inline double sqrt(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Stamm Squre des Arguments zurück

##  <a name="sqrtf"></a>  sqrtf

Berechnet den Squre Stamm des Arguments

```
inline float sqrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Stamm Squre des Arguments zurück

##  <a name="tan"></a> tan

Berechnet den Tangenswert des Arguments

```
inline float tan(float _X) restrict(amp);

inline double tan(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Tangenswert des Arguments

##  <a name="tanf"></a>  tanf

Berechnet den Tangenswert des Arguments

```
inline float tanf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Tangenswert des Arguments

##  <a name="tanh"></a> tanh

Berechnet den Hyperbeltangenswert des Arguments

```
inline float tanh(float _X) restrict(amp);

inline double tanh(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den hyperbeltangenswert des Arguments

##  <a name="tanhf"></a>  tanhf

Berechnet den Hyperbeltangenswert des Arguments

```
inline float tanhf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den hyperbeltangenswert des Arguments

##  <a name="tanpi"></a>  tanpi

Berechnet den Tangenswert von Pi \* _X

```
inline float tanpi(float _X) restrict(amp);

inline double tanpi(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Tangenswert des Pi \* _X

##  <a name="tanpif"></a>  tanpif

Berechnet den Tangenswert von Pi \* _X

```
inline float tanpif(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt den Tangenswert des Pi \* _X

##  <a name="tgamma"></a>  tgamma

Berechnet die Gammafunktion von _X

```
inline float tgamma(float _X) restrict(amp);

inline double tgamma(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt das Ergebnis der Gammafunktion von _X

##  <a name="tgammaf"></a>  tgammaf

Berechnet die Gammafunktion von _X

```
inline float tgammaf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt das Ergebnis der Gammafunktion von _X

##  <a name="trunc"></a>  kürzungs-LSN

Schneidet das Argument der ganzzahligen Komponente ab

```
inline float trunc(float _X) restrict(amp);

inline double trunc(double _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die ganzzahlige Komponente des Arguments zurück

##  <a name="truncf"></a>  truncf

Schneidet das Argument der ganzzahligen Komponente ab

```
inline float truncf(float _X) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_X*<br/>
Gleitkommawert

### <a name="return-value"></a>Rückgabewert

Gibt die ganzzahlige Komponente des Arguments zurück

## <a name="see-also"></a>Siehe auch

[Concurrency::precise_math Namespace](concurrency-precise-math-namespace.md)
