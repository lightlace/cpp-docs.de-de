---
title: 'Concurrency:: precise_math-Namespace Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fae53ab4-d1c5-45bb-a6a0-a74258e9aea3
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 73273a58f73860c77810a6ab59def560962f9539
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencyprecisemath-namespace-functions"></a>Concurrency:: precise_math-Namespace-Funktionen
||||  
|-|-|-|  
|[ACOS-Funktion](#acos)|[Acosf-Funktion](#acosf)|[Acosh-Funktion](#acosh)|  
|[Acoshf-Funktion](#acoshf)|[ASIN-Funktion](#asin)|[Asinf-Funktion](#asinf)|  
|[Asinh-Funktion](#asinh)|[Asinhf-Funktion](#asinhf)|[ATAN-Funktion](#atan)|  
|[atan2-Funktion](#atan2)|[atan2f-Funktion](#atan2f)|[Atanf-Funktion](#atanf)|  
|[Atanh-Funktion](#atanh)|[Atanhf-Funktion](#atanhf)|[Cbrt-Funktion](#cbrt)|  
|[Cbrtf-Funktion](#cbrtf)|[ceil-Funktion](#ceil)|[Ceilf-Funktion](#ceilf)|  
|[Copysign-Funktion](#copysign)|[Copysignf-Funktion](#copysignf)|[cos Funktion](#cos)|  
|[Cosf-Funktion](#cosf)|[cosh-Funktion](#cosh)|[Coshf-Funktion](#coshf)|  
|[Cospi-Funktion](#cospi)|[Cospif-Funktion](#cospif)|[Erf-Funktion](#erf)|  
|[ErfC-Funktion](#erfc)|[Erfcf-Funktion](#erfcf)|[Erfcinv-Funktion](#erfcinv)|  
|[Erfcinvf-Funktion](#erfcinvf)|[Erff-Funktion](#erff)|[Erfinv-Funktion](#erfinv)|  
|[Erfinvf-Funktion](#erfinvf)|[EXP-Funktion](#exp)|[exp10-Funktion](#exp10)|  
|[exp10f-Funktion](#exp10f)|[EXP2-Funktion](#exp2)|[exp2f-Funktion](#exp2f)|  
|[Expf-Funktion](#expf)|[expm1-Funktion](#expm1)|[expm1f-Funktion](#expm1f)|  
|[Fabs-Funktion](#fabs)|[Fabsf-Funktion](#fabsf)|[Floor-Funktion](#floor)| 
|[Fdim-Funktion](#fdim)|[Fdimf-Funktion](#fdimf)|| 
|[Floorf-Funktion](#floorf)|[FMA-Funktion](#fma)|[Fmaf-Funktion](#fmaf)|
[Fmax-Funktion](#fmax)|[Fmaxf-Funktion](#fmaxf)|| 
|[Fmin-Funktion](#fmin)|[Fminf-Funktion](#fminf)|[fmod-Funktion](#fmod)|  
|[Fmodf-Funktion](#fmodf)|[Fpclassify-Funktion](#fpclassify)|[Frexp-Funktion](#frexp)|  
|[Frexpf-Funktion](#frexpf)|[Hypot-Funktion](#hypot)|[Hypotf-Funktion](#hypotf)|  
|[Ilogb-Funktion](#ilogb)|[Ilogbf-Funktion](#ilogbf)|[IsFinite-Funktion](#isfinite)|  
|[Isinf-Funktion](#isinf)|[IsNaN-Funktion](#isnan)|[Isnormal-Funktion](#isnormal)|  
|[Ldexp-Funktion](#ldexp)|[Ldexpf-Funktion](#ldexpf)|[Lgamma-Funktion](#lgamma)|  
|[Lgammaf-Funktion](#lgammaf)|[log-Funktion](#log)|[LOG10-Funktion](#log10)|  
|[log10f-Funktion](#log10f)|[log1p-Funktion](#log1p)|[log1pf-Funktion](#log1pf)|  
|[log2-Funktion](#log2)|[log2f-Funktion](#log2f)|[Logb-Funktion](#logb)|  
|[Logbf-Funktion](#logbf)|[Logf-Funktion](#logf)|[Modf-Funktion](#modf)|  
|[Modff-Funktion](#modff)|[NaN-Funktion](#nan)|[Nanf-Funktion](#nanf)|  
|[Nearbyint-Funktion](#nearbyint)|[Nearbyintf-Funktion](#nearbyintf)|[Nextafter-Funktion](#nextafter)|  
|[Nextafterf-Funktion](#nextafterf)|[Phi-Funktion](#phi)|[Phif-Funktion](#phif)|  
|[Pow-Funktion](#pow)|[Powf-Funktion](#powf)|[probit-Funktion](#probit)|  
|[Probitf-Funktion](#probitf)|[Rcbrt-Funktion](#rcbrt)|[Rcbrtf-Funktion](#rcbrtf)|  
|[Restfunktion](#remainder)|[Remainderf-Funktion](#remainderf)|[Remquo-Funktion](#remquo)|  
|[Remquof-Funktion](#remquof)|[Round-Funktion](#round)|[Roundf-Funktion](#roundf)|  
|[Rsqrt-Funktion](#rsqrt)|[Rsqrtf-Funktion](#rsqrtf)|[Scalb-Funktion](#scalb)|  
|[Scalbf-Funktion](#scalbf)|[Scalbn-Funktion](#scalbn)|[Scalbnf-Funktion](#scalbnf)|  
|[Signbit-Funktion](#signbit)|[Signbitf-Funktion](#signbitf)|[SIN-Funktion](#sin)|  
|[Sincos-Funktion](#sincos)|[Sincosf-Funktion](#sincosf)|[Sinf-Funktion](#sinf)|  
|[Sinh-Funktion](#sinh)|[Sinhf-Funktion](#sinhf)|[Sinpi-Funktion](#sinpi)|  
|[Sinpif-Funktion](#sinpif)|[Sqrt-Funktion](#sqrt)|[Sqrtf-Funktion](#sqrtf)|  
|[Tan-Funktion](#tan)|[Tanf-Funktion](#tanf)|[Tanh-Funktion](#tanh)|  
|[Tanhf-Funktion](#tanhf)|[Tanpi-Funktion](#tanpi)|[Tanpif-Funktion](#tanpif)|  
|[Tgamma-Funktion](#tgamma)|[Tgammaf-Funktion](#tgammaf)|[TRUNC-Funktion](#trunc)|  
|[Truncf-Funktion](#truncf)|  
  
##  <a name="a-nameacosa--acos-function"></a><a name="acos"></a>ACOS-Funktion  
 Berechnet den Arkuskosinus des Arguments  
  
```  
inline float acos(float _X) restrict(amp);

 
inline double acos(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Arkuskosinus-Wert des Arguments zurück  
  
##  <a name="a-nameacosfa--acosf-function"></a><a name="acosf"></a>Acosf-Funktion  
 Berechnet den Arkuskosinus des Arguments  
  
```  
inline float acosf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Arkuskosinus-Wert des Arguments zurück  
  
##  <a name="a-nameacosha--acosh-function"></a><a name="acosh"></a>Acosh-Funktion  
 Berechnet den umgekehrten hyperbolischen Kosinus des Arguments  
  
```  
inline float acosh(float _X) restrict(amp);

 
inline double acosh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den umgekehrten hyperbolischen Kosinus-Wert des Arguments zurück  
  
##  <a name="a-nameacoshfa--acoshf-function"></a><a name="acoshf"></a>Acoshf-Funktion  
 Berechnet den umgekehrten hyperbolischen Kosinus des Arguments  
  
```  
inline float acoshf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den umgekehrten hyperbolischen Kosinus-Wert des Arguments zurück  
  
##  <a name="a-nameasina--asin-function"></a><a name="asin"></a>ASIN-Funktion  
 Berechnet den Arkussinus des Arguments  
  
```  
inline float asin(float _X) restrict(amp);

 
inline double asin(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Arkussinus-Wert des Arguments zurück  
  
##  <a name="a-nameasinfa--asinf-function"></a><a name="asinf"></a>Asinf-Funktion  
 Berechnet den Arkussinus des Arguments  
  
```  
inline float asinf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Arkussinus-Wert des Arguments zurück  
  
##  <a name="a-nameasinha--asinh-function"></a><a name="asinh"></a>Asinh-Funktion  
 Berechnet den umgekehrten hyperbolischen Sinus des Arguments  
  
```  
inline float asinh(float _X) restrict(amp);

 
inline double asinh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Arkussinus-Wert des Arguments  
  
##  <a name="a-nameasinhfa--asinhf-function"></a><a name="asinhf"></a>Asinhf-Funktion  
 Berechnet den umgekehrten hyperbolischen Sinus des Arguments  
  
```  
inline float asinhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Arkussinus-Wert des Arguments  
  
##  <a name="a-nameatana--atan-function"></a><a name="atan"></a>ATAN-Funktion  
 Berechnet den Arkustangens des Arguments  
  
```  
inline float atan(float _X) restrict(amp);

 
inline double atan(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Arkustangens-Wert des Arguments zurück  
  
##  <a name="a-nameatan2a--atan2-function"></a><a name="atan2"></a>atan2-Funktion  
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
 `_Y`  
 Gleitkommawert  
  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Arkustangens-Wert von _Y/_X  
  
##  <a name="a-nameatan2fa--atan2f-function"></a><a name="atan2f"></a>atan2f-Funktion  
 Berechnet den Arkustangens von _Y/_X  
  
```  
inline float atan2f(
    float _Y,  
    float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_Y`  
 Gleitkommawert  
  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Arkustangens-Wert von _Y/_X  
  
##  <a name="a-nameatanfa--atanf-function"></a><a name="atanf"></a>Atanf-Funktion  
 Berechnet den Arkustangens des Arguments  
  
```  
inline float atanf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Arkustangens-Wert des Arguments zurück  
  
##  <a name="a-nameatanha--atanh-function"></a><a name="atanh"></a>Atanh-Funktion  
 Berechnet den umgekehrten hyperbolischen Tangens des Arguments  
  
```  
inline float atanh(float _X) restrict(amp);

 
inline double atanh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den umgekehrten hyperbolischen Tangenswert des Arguments zurück  
  
##  <a name="a-nameatanhfa--atanhf-function"></a><a name="atanhf"></a>Atanhf-Funktion  
 Berechnet den umgekehrten hyperbolischen Tangens des Arguments  
  
```  
inline float atanhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den umgekehrten hyperbolischen Tangenswert des Arguments zurück  
  
##  <a name="a-namecbrta--cbrt-function"></a><a name="cbrt"></a>Cbrt-Funktion  
 Berechnet die Kubikwurzel real des Arguments  
  
```  
inline float cbrt(float _X) restrict(amp);

 
inline double cbrt(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den realen Cube Stamm des Arguments zurück  
  
##  <a name="a-namecbrtfa--cbrtf-function"></a><a name="cbrtf"></a>Cbrtf-Funktion  
 Berechnet die Kubikwurzel real des Arguments  
  
```  
inline float cbrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den realen Cube Stamm des Arguments zurück  
  
##  <a name="a-nameceila--ceil-function"></a><a name="ceil"></a>ceil-Funktion  
 Berechnet den Höchstwert des Arguments  
  
```  
inline float ceil(float _X) restrict(amp);

 
inline double ceil(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Höchstwert des Arguments zurück  
  
##  <a name="a-nameceilfa--ceilf-function"></a><a name="ceilf"></a>Ceilf-Funktion  
 Berechnet den Höchstwert des Arguments  
  
```  
inline float ceilf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Höchstwert des Arguments zurück  
  
##  <a name="a-namecopysigna--copysign-function"></a><a name="copysign"></a>Copysign-Funktion  
 Produziert einen Wert mit der Größe von _X und das Zeichen _y  
  
```  
inline float copysign(
    float _X,  
    float _Y) restrict(amp);

 
inline double copysign(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
 `_Y`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert mit der Größe von _X und das Zeichen _y  
  
##  <a name="a-namecopysignfa--copysignf-function"></a><a name="copysignf"></a>Copysignf-Funktion  
 Produziert einen Wert mit der Größe von _X und das Zeichen _y  
  
```  
inline float copysignf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
 `_Y`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert mit der Größe von _X und das Zeichen _y  
  
##  <a name="a-namecosa--cos-function"></a><a name="cos"></a>cos Funktion  
 Berechnet den Kosinus des Arguments  
  
```  
inline float cos(float _X) restrict(amp);

 
inline double cos(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Kosinuswert des Arguments zurück  
  
##  <a name="a-namecosfa--cosf-function"></a><a name="cosf"></a>Cosf-Funktion  
 Berechnet den Kosinus des Arguments  
  
```  
inline float cosf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Kosinuswert des Arguments zurück  
  
##  <a name="a-namecosha--cosh-function"></a><a name="cosh"></a>cosh-Funktion  
 Berechnet den Hyperbelkosinuswert des Arguments  
  
```  
inline float cosh(float _X) restrict(amp);

 
inline double cosh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den hyperbolischen Kosinus-Wert des Arguments zurück  
  
##  <a name="a-namecoshfa--coshf-function"></a><a name="coshf"></a>Coshf-Funktion  
 Berechnet den Hyperbelkosinuswert des Arguments  
  
```  
inline float coshf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den hyperbolischen Kosinus-Wert des Arguments zurück  
  
##  <a name="a-namecospia--cospi-function"></a><a name="cospi"></a>Cospi-Funktion  
 Berechnet den Kosinuswert von Pi * _X  
  
```  
inline float cospi(float _X) restrict(amp);

 
inline double cospi(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Kosinus-Wert von Pi * _X  
  
##  <a name="a-namecospifa--cospif-function"></a><a name="cospif"></a>Cospif-Funktion  
 Berechnet den Kosinuswert von Pi * _X  
  
```  
inline float cospif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Kosinus-Wert von Pi * _X  
  
##  <a name="a-nameerfa--erf-function"></a><a name="erf"></a>Erf-Funktion  
 Berechnet die Fehlerfunktion von _X  
  
```  
inline float erf(float _X) restrict(amp);

 
inline double erf(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Fehlerfunktion von _X  
  
##  <a name="a-nameerfca--erfc-function"></a><a name="erfc"></a>ErfC-Funktion  
 Berechnet die komplementäre Fehlerfunktion von _X  
  
```  
inline float erfc(float _X) restrict(amp);

 
inline double erfc(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die komplementäre Fehlerfunktion von _X  
  
##  <a name="a-nameerfcfa--erfcf-function"></a><a name="erfcf"></a>Erfcf-Funktion  
 Berechnet die komplementäre Fehlerfunktion von _X  
  
```  
inline float erfcf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die komplementäre Fehlerfunktion von _X  
  
##  <a name="a-nameerfcinva--erfcinv-function"></a><a name="erfcinv"></a>Erfcinv-Funktion  
 Berechnet die inverse komplementäre Fehlerfunktion von _X  
  
```  
inline float erfcinv(float _X) restrict(amp);

 
inline double erfcinv(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die inverse komplementäre Fehlerfunktion von _X  
  
##  <a name="a-nameerfcinvfa--erfcinvf-function"></a><a name="erfcinvf"></a>Erfcinvf-Funktion  
 Berechnet die inverse komplementäre Fehlerfunktion von _X  
  
```  
inline float erfcinvf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die inverse komplementäre Fehlerfunktion von _X  
  
##  <a name="a-nameerffa--erff-function"></a><a name="erff"></a>Erff-Funktion  
 Berechnet die Fehlerfunktion von _X  
  
```  
inline float erff(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Fehlerfunktion von _X  
  
##  <a name="a-nameerfinva--erfinv-function"></a><a name="erfinv"></a>Erfinv-Funktion  
 Berechnet die inverse Error-Funktion von _X  
  
```  
inline float erfinv(float _X) restrict(amp);

 
inline double erfinv(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die inverse Error-Funktion von _X  
  
##  <a name="a-nameerfinvfa--erfinvf-function"></a><a name="erfinvf"></a>Erfinvf-Funktion  
 Berechnet die inverse Error-Funktion von _X  
  
```  
inline float erfinvf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die inverse Error-Funktion von _X  
  
##  <a name="a-nameexp10a--exp10-function"></a><a name="exp10"></a>exp10-Funktion  
 Berechnet die Basis&10; vom Argument exponential  
  
```  
inline float exp10(float _X) restrict(amp);

 
inline double exp10(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die vom Argument exponential Base-10  
  
##  <a name="a-nameexp10fa--exp10f-function"></a><a name="exp10f"></a>exp10f-Funktion  
 Berechnet die Basis&10; vom Argument exponential  
  
```  
inline float exp10f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die vom Argument exponential Base-10  
  
##  <a name="a-nameexpm1a--expm1-function"></a><a name="expm1"></a>expm1-Funktion  
 Berechnet die Basis-E, die vom Argument exponential ist, minus 1  
  
```  
inline float expm1(float exponent) restrict(amp);

 
inline double expm1(double exponent) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `exponent`  
 Der Exponent *n* des mathematischen Ausdrucks `e` <sup>n</sup>, wobei `e` ist die Basis des natürlichen Logarithmus.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Basis-E, die vom Argument exponential ist, minus 1 zurück  
  
##  <a name="a-nameexpm1fa--expm1f-function"></a><a name="expm1f"></a>expm1f-Funktion  
 Berechnet die Basis-E, die vom Argument exponential ist, minus 1  
  
```  
inline float expm1f(float exponent) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `exponent`  
 Der Exponent *n* des mathematischen Ausdrucks `e` <sup>n</sup>, wobei `e` ist die Basis des natürlichen Logarithmus.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Basis-E, die vom Argument exponential ist, minus 1 zurück  
  
##  <a name="a-nameexpa--exp-function"></a><a name="exp"></a>EXP-Funktion  
 Berechnet die Basis-E, die vom Argument exponential ist  
  
```  
inline float exp(float _X) restrict(amp);

 
inline double exp(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die vom Argument exponential Basis-e  
  
##  <a name="a-nameexpfa--expf-function"></a><a name="expf"></a>Expf-Funktion  
 Berechnet die Basis-E, die vom Argument exponential ist  
  
```  
inline float expf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die vom Argument exponential Basis-e  
  
##  <a name="a-nameexp2a--exp2-function"></a><a name="exp2"></a>EXP2-Funktion  
 Berechnet die Basis-2, die vom Argument exponential ist  
  
```  
inline float exp2(float _X) restrict(amp);

 
inline double exp2(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die vom Argument exponential Basis-2  
  
##  <a name="a-nameexp2fa--exp2f-function"></a><a name="exp2f"></a>exp2f-Funktion  
 Berechnet die Basis-2, die vom Argument exponential ist  
  
```  
inline float exp2f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die vom Argument exponential Basis-2  
  
##  <a name="a-namefabsa--fabs-function"></a><a name="fabs"></a>Fabs-Funktion  
 Gibt den absoluten Wert des Arguments zurück.  
  
```  
inline float fabs(float _X) restrict(amp);

 
inline double fabs(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den absoluten Wert des Arguments zurück.  
  
##  <a name="a-namefabsfa--fabsf-function"></a><a name="fabsf"></a>Fabsf-Funktion  
 Gibt den absoluten Wert des Arguments zurück.  
  
```  
inline float fabsf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den absoluten Wert des Arguments zurück.  

## <a name="a-namefdima-fdim-function"></a><a name="fdim"></a>Fdim-Funktion  
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
`_X`Gleitkommawert `_Y` Gleitkommawert


### <a name="return-value"></a>Rückgabewert
Der Unterschied zwischen _X und _Y, wenn _X größer als _Y ist; andernfalls, +&0;.
 
## <a name="a-namefdimfa-fdimf-function"></a><a name="fdimf"></a>Fdimf-Funktion
Berechnet den positiven Unterschied zwischen den Argumenten.
```
inline float fdimf(
   float _X,
   float _Y
) restrict(amp);
```
### <a name="parameters"></a>Parameter
`_X`Gleitkommawert `_Y` Gleitkommawert

### <a name="return-value"></a>Rückgabewert
Der Unterschied zwischen _X und _Y, wenn _X größer als _Y ist; andernfalls, +&0;. 
  
##  <a name="a-namefloora--floor-function"></a><a name="floor"></a>Floor-Funktion  
 Berechnet den Tiefstwert des Arguments  
  
```  
inline float floor(float _X) restrict(amp);

 
inline double floor(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Untergrenze des Arguments  
  
##  <a name="a-namefloorfa--floorf-function"></a><a name="floorf"></a>Floorf-Funktion  
 Berechnet den Tiefstwert des Arguments  
  
```  
inline float floorf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Untergrenze des Arguments  

## <a name="a-namefma-fma-function"></a><a name="fma">FMA-Funktion  
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
`_X`Das erste Gleitkommaargument.
`_Y`Das zweite Gleitkommaargument.
`_Z`Das dritte Gleitkommaargument.

### <a name="return-value"></a>Rückgabewert
Das Ergebnis des Ausdrucks (_X * _Y) + _Z. Die gesamte Berechnung wird als einzelner Vorgang ausgeführt; das heißt, die Teilausdrücke werden mit unendlicher Genauigkeit berechnet und nur das Endergebnis wird gerundet. 

## <a name="a-namefmafa-fmaf-function"></a><a name="fmaf"></a>Fmaf-Funktion  
Berechnet das Produkt des ersten und zweiten angegebenen Arguments, fügt dann das dritte angegebene Argument dem Ergebnis hinzu. Die gesamte Berechnung wird als einzelner Vorgang ausgeführt.
```
inline float fmaf(
   float _X,
   float _Y,
   float _Z
) restrict(amp);
```  
### <a name="parameters"></a>Parameter
`_X`Das erste Gleitkommaargument.
`_Y`Das zweite Gleitkommaargument.
`_Z`Das dritte Gleitkommaargument.

### <a name="return-value"></a>Rückgabewert
Das Ergebnis des Ausdrucks (_X * _Y) + _Z. Die gesamte Berechnung wird als einzelner Vorgang ausgeführt; das heißt, die Teilausdrücke werden mit unendlicher Genauigkeit berechnet und nur das Endergebnis wird gerundet.
  
##  <a name="a-namefmaxa--fmax-function"></a><a name="fmax"></a>Fmax-Funktion  
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
 `_X`  
 Gleitkommawert  
  
 `_Y`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Rückgabe des höchsten numerischen Werts der Argumente  
  
##  <a name="a-namefmaxfa--fmaxf-function"></a><a name="fmaxf"></a>Fmaxf-Funktion  
 Festlegung des höchsten numerischen Werts der Argumente  
  
```  
inline float fmaxf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
 `_Y`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Rückgabe des höchsten numerischen Werts der Argumente  
  
##  <a name="a-namefmina--fmin-function"></a><a name="fmin"></a>Fmin-Funktion  
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
 `_X`  
 Gleitkommawert  
  
 `_Y`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Rückgabe des niedrigsten numerischen Werts der Argumente  
  
##  <a name="a-namefminfa--fminf-function"></a><a name="fminf"></a>Fminf-Funktion  
 Festlegung des niedrigsten numerischen Werts der Argumente  
  
```  
inline float fminf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
 `_Y`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Rückgabe des niedrigsten numerischen Werts der Argumente  
  
##  <a name="a-namefmoda--fmod-function-c-amp"></a><a name="fmod"></a>Fmod-Funktion (C++-AMP)  
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
 `_X`  
 Das erste Gleitkommaargument.  
  
 `_Y`  
 Das zweite Gleitkommaargument.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rest des `_X` geteilt durch `_Y`; also den Wert der `_X`  -  `_Y` *n*, wobei *n* ist eine ganze Zahl, die Größe der `_X`  -  `_Y` *n* ist kleiner als die Größe der `_Y`.  
  
##  <a name="a-namefmodfa--fmodf-function"></a><a name="fmodf"></a>Fmodf-Funktion  
 Berechnet den Rest des angegebenen ersten Arguments dividiert durch das zweite angegebene Argument.  
  
```  
inline float fmodf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Das erste Gleitkommaargument.  
  
 `_Y`  
 Das zweite Gleitkommaargument.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rest des `_X` geteilt durch `_Y`; also den Wert der `_X`  -  `_Y` *n*, wobei *n* ist eine ganze Zahl, die Größe der `_X`  -  `_Y` *n* ist kleiner als die Größe der `_Y`.  
  
##  <a name="a-namefpclassifya--fpclassify-function"></a><a name="fpclassify"></a>Fpclassify-Funktion  
 Den Argumentwert klassifiziert, wie NaN, unendlich, Normal, subnormal,&0; (null)  
  
```  
inline int fpclassify(float _X) restrict(amp);

 
inline int fpclassify(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert der Zahl Klassifizierung Makros den Wert des Arguments zurück.  
  
##  <a name="a-namefrexpa--frexp-function"></a><a name="frexp"></a>Frexp-Funktion  
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
 `_X`  
 Gleitkommawert  
  
 `_Exp`  
 Gibt den ganzzahligen Exponenten von _X in Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Mantisse _X  
  
##  <a name="a-namefrexpfa--frexpf-function"></a><a name="frexpf"></a>Frexpf-Funktion  
 Ruft die Mantisse und den Exponenten von _X ab  
  
```  
inline float frexpf(
    float _X,  
    _Out_ int* _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
 `_Exp`  
 Gibt den ganzzahligen Exponenten von _X in Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Mantisse _X  
  
##  <a name="a-namehypota--hypot-function"></a><a name="hypot"></a>Hypot-Funktion  
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
 `_X`  
 Gleitkommawert  
  
 `_Y`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Quadratwurzel der Summe der Quadrate von _X und _Y zurück  
  
##  <a name="a-namehypotfa--hypotf-function"></a><a name="hypotf"></a>Hypotf-Funktion  
 Berechnet die Quadratwurzel der Summe der Quadrate von _X und _Y  
  
```  
inline float hypotf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
 `_Y`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Quadratwurzel der Summe der Quadrate von _X und _Y zurück  
  
##  <a name="a-nameilogba--ilogb-function"></a><a name="ilogb"></a>Ilogb-Funktion  
 Extrahieren Sie den Exponenten von _X als Wert mit Vorzeichen int  
  
```  
inline int ilogb(float _X) restrict(amp);

 
inline int ilogb(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Exponenten von _X als signierte Int-Wert  
  
##  <a name="a-nameilogbfa--ilogbf-function"></a><a name="ilogbf"></a>Ilogbf-Funktion  
 Extrahieren Sie den Exponenten von _X als Wert mit Vorzeichen int  
  
```  
inline int ilogbf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Exponenten von _X als signierte Int-Wert  
  
##  <a name="a-nameisfinitea--isfinite-function"></a><a name="isfinite"></a>IsFinite-Funktion  
 Bestimmt, ob das Argument einen über begrenzten Wert verfügt  
  
```  
inline int isfinite(float _X) restrict(amp);

 
inline int isfinite(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert ungleich NULL nur, wenn das Argument einen begrenzten Wert verfügt.  
  
##  <a name="a-nameisinfa--isinf-function"></a><a name="isinf"></a>Isinf-Funktion  
 Bestimmt, ob das Argument unendlich ist  
  
```  
inline int isinf(float _X) restrict(amp);

 
inline int isinf(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert ungleich NULL nur, wenn das Argument einen unendlichen Wert hat.  
  
##  <a name="a-nameisnana--isnan-function"></a><a name="isnan"></a>IsNaN-Funktion  
 Bestimmt, ob das Argument ein NaN  
  
```  
inline int isnan(float _X) restrict(amp);

 
inline int isnan(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert ungleich NULL nur, wenn das Argument einen NaN-Wert hat.  
  
##  <a name="a-nameisnormala--isnormal-function"></a><a name="isnormal"></a>Isnormal-Funktion  
 Bestimmt, ob das Argument ein normaler  
  
```  
inline int isnormal(float _X) restrict(amp);

 
inline int isnormal(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert ungleich NULL nur, wenn das Argument einen normalen Wert hat.  
  
##  <a name="a-nameldexpa--ldexp-function"></a><a name="ldexp"></a>Ldexp-Funktion  
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
 `_X`  
 Gleitkommawert, Mantisse  
  
 `_Exp`  
 Ganze Zahl, Exponent  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt _X * 2^_Exp zurück  
  
##  <a name="a-nameldexpfa--ldexpf-function"></a><a name="ldexpf"></a>Ldexpf-Funktion  
 Berechnet eine reelle Zahl aus der angegebenen Mantisse und dem Exponent.  
  
```  
inline float ldexpf(
    float _X,  
    int _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert, Mantisse  
  
 `_Exp`  
 Ganze Zahl, Exponent  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt _X * 2^_Exp zurück  
  
##  <a name="a-namelgammaa--lgamma-function"></a><a name="lgamma"></a>Lgamma-Funktion  
 Berechnet den natürlichen Logarithmus der Absolute Wert des Gamma des Arguments  
  
```  
inline float lgamma(
    float _X,  
    _Out_ int* _Sign) restrict(amp);

 
inline double lgamma(
    double _X,  
    _Out_ int* _Sign) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
 `_Sign`  
 Gibt das Vorzeichen  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den natürlichen Logarithmus des absoluten Werts von Gamma des Arguments  
  
##  <a name="a-namelgammafa--lgammaf-function"></a><a name="lgammaf"></a>Lgammaf-Funktion  
 Berechnet den natürlichen Logarithmus der Absolute Wert des Gamma des Arguments  
  
```  
inline float lgammaf(
    float _X,  
    _Out_ int* _Sign) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
 `_Sign`  
 Gibt das Vorzeichen  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den natürlichen Logarithmus des absoluten Werts von Gamma des Arguments  
  
##  <a name="a-nameloga--log-function"></a><a name="log"></a>log-Funktion  
 Berechnet den Basis-E-Logarithmus des Arguments  
  
```  
inline float log(float _X) restrict(amp);

 
inline double log(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Basis-e-Logarithmus des Arguments  
  
##  <a name="a-namelog10a--log10-function"></a><a name="log10"></a>LOG10-Funktion  
 Berechnet den Basis-10-Logarithmus des Arguments  
  
```  
inline float log10(float _X) restrict(amp);

 
inline double log10(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Base-10-Logarithmus des Arguments  
  
##  <a name="a-namelog10fa--log10f-function"></a><a name="log10f"></a>log10f-Funktion  
 Berechnet den Basis-10-Logarithmus des Arguments  
  
```  
inline float log10f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Base-10-Logarithmus des Arguments  
  
##  <a name="a-namelog1pa--log1p-function"></a><a name="log1p"></a>log1p-Funktion  
 Berechnet den Basis-e-Logarithmus des 1 plus das argument  
  
```  
inline float log1p(float _X) restrict(amp);

 
inline double log1p(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Logarithmus Basis-e-1 plus Arguments zurück  
  
##  <a name="a-namelog1pfa--log1pf-function"></a><a name="log1pf"></a>log1pf-Funktion  
 Berechnet den Basis-e-Logarithmus des 1 plus das argument  
  
```  
inline float log1pf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Logarithmus Basis-e-1 plus Arguments zurück  
  
##  <a name="a-namelog2a--log2-function"></a><a name="log2"></a>log2-Funktion  
 Berechnet den Basis-2-Logarithmus des Arguments  
  
```  
inline float log2(float _X) restrict(amp);

 
inline double log2(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Base-10-Logarithmus des Arguments  
  
##  <a name="a-namelog2fa--log2f-function"></a><a name="log2f"></a>log2f-Funktion  
 Berechnet den Basis-2-Logarithmus des Arguments  
  
```  
inline float log2f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Base-10-Logarithmus des Arguments  
  
##  <a name="a-namelogba--logb-function"></a><a name="logb"></a>Logb-Funktion  
 Extrahiert den Exponenten von _x ab, als eine Ganzzahl mit Vorzeichen im Gleitkommaformat  
  
```  
inline float logb(float _X) restrict(amp);

 
inline double logb(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den signierten Exponenten von _X  
  
##  <a name="a-namelogbfa--logbf-function"></a><a name="logbf"></a>Logbf-Funktion  
 Extrahiert den Exponenten von _x ab, als eine Ganzzahl mit Vorzeichen im Gleitkommaformat  
  
```  
inline float logbf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den signierten Exponenten von _X  
  
##  <a name="a-namelogfa--logf-function"></a><a name="logf"></a>Logf-Funktion  
 Berechnet den Basis-E-Logarithmus des Arguments  
  
```  
inline float logf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Basis-e-Logarithmus des Arguments  
  
##  <a name="a-namemodfa--modf-function"></a><a name="modf"></a>Modf-Funktion  
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
 `_X`  
 Gleitkommawert  
  
 `_Iptr` (Out-Parameter)  
 Der ganzzahlige Teil von `_X` als Gleitkommawert.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Bruchteil von `_X` mit Vorzeichen.  
  
##  <a name="a-namemodffa--modff-function"></a><a name="modff"></a>Modff-Funktion  
 Teilt das angegebene Argument in Brüche und ganzzahlige Teile.  
  
```  
inline float modff(
    float _X,  
    _Out_ float* _Iptr) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
 `_Iptr`  
 Der ganzzahlige Teil von `_X` als Gleitkommawert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Bruchteil mit Vorzeichen von `_X` zurück.  
  
##  <a name="a-namenana--nan-function"></a><a name="nan"></a>NaN-Funktion  
 Gibt ein stilles NaN zurück  
  
```  
inline double nan(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Ganzzahliger Wert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein stilles NaN, wenn verfügbar, mit dem Inhalt im _X  
  
##  <a name="a-namenanfa--nanf-function"></a><a name="nanf"></a>Nanf-Funktion  
 Gibt ein stilles NaN zurück  
  
```  
inline float nanf(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Ganzzahliger Wert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein stilles NaN, wenn verfügbar, mit dem Inhalt im _X  
  
##  <a name="a-namenearbyinta--nearbyint-function"></a><a name="nearbyint"></a>Nearbyint-Funktion  
 Rundet das Argument in einen ganzzahligen Wert im Gleitkommaformat mit dem aktuellen Rundung.  
  
```  
inline float nearbyint(float _X) restrict(amp);

 
inline double nearbyint(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Der gerundete Ganzzahlwert zurückgegeben.  
  
##  <a name="a-namenearbyintfa--nearbyintf-function"></a><a name="nearbyintf"></a>Nearbyintf-Funktion  
 Rundet das Argument in einen ganzzahligen Wert im Gleitkommaformat mit dem aktuellen Rundung.  
  
```  
inline float nearbyintf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Der gerundete Ganzzahlwert zurückgegeben.  
  
##  <a name="a-namenextaftera--nextafter-function"></a><a name="nextafter"></a>Nextafter-Funktion  
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
 `_X`  
 Gleitkommawert  
  
 `_Y`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den nächsten darstellbaren Wert, im Typ der Funktion, nach _X in Richtung _Y zurück  
  
##  <a name="a-namenextafterfa--nextafterf-function"></a><a name="nextafterf"></a>Nextafterf-Funktion  
 Bestimmen Sie den nächsten darstellbaren Wert, im Typ der Funktion, nach _X in Richtung _Y  
  
```  
inline float nextafterf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
 `_Y`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den nächsten darstellbaren Wert, im Typ der Funktion, nach _X in Richtung _Y zurück  
  
##  <a name="a-namephia--phi-function"></a><a name="phi"></a>Phi-Funktion  
 Gibt die kumulative Verteilungsfunktion des Arguments zurück  
  
```  
inline float phi(float _X) restrict(amp);

 
inline double phi(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die kumulative Verteilungsfunktion des Arguments zurück  
  
##  <a name="a-namephifa--phif-function"></a><a name="phif"></a>Phif-Funktion  
 Gibt die kumulative Verteilungsfunktion des Arguments zurück  
  
```  
inline float phif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die kumulative Verteilungsfunktion des Arguments zurück  
  
##  <a name="a-namepowa--pow-function"></a><a name="pow"></a>Pow-Funktion  
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
 `_X`  
 Gleitkommawert, Basis  
  
 `_Y`  
 Gleitkommawert, exponent  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="a-namepowfa--powf-function"></a><a name="powf"></a>Powf-Funktion  
 Berechnet _X potenziert mit _Y  
  
```  
inline float powf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert, Basis  
  
 `_Y`  
 Gleitkommawert, exponent  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="a-nameprobita--probit-function"></a><a name="probit"></a>probit-Funktion  
 Gibt die inverse kumulative Verteilungsfunktion des Arguments zurück  
  
```  
inline float probit(float _X) restrict(amp);

 
inline double probit(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die inverse kumulative Verteilungsfunktion des Arguments zurück  
  
##  <a name="a-nameprobitfa--probitf-function"></a><a name="probitf"></a>Probitf-Funktion  
 Gibt die inverse kumulative Verteilungsfunktion des Arguments zurück  
  
```  
inline float probitf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die inverse kumulative Verteilungsfunktion des Arguments zurück  
  
##  <a name="a-namercbrta--rcbrt-function"></a><a name="rcbrt"></a>Rcbrt-Funktion  
 Gibt den Kehrwert der die Kubikwurzel des Arguments zurück  
  
```  
inline float rcbrt(float _X) restrict(amp);

 
inline double rcbrt(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Kehrwert der die Kubikwurzel des Arguments zurück  
  
##  <a name="a-namercbrtfa--rcbrtf-function"></a><a name="rcbrtf"></a>Rcbrtf-Funktion  
 Gibt den Kehrwert der die Kubikwurzel des Arguments zurück  
  
```  
inline float rcbrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Kehrwert der die Kubikwurzel des Arguments zurück  
  
##  <a name="a-nameremaindera--remainder-function"></a><a name="remainder"></a>Restfunktion  
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
 `_X`  
 Gleitkommawert  
  
 `_Y`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt _X REM _Y  
  
##  <a name="a-nameremainderfa--remainderf-function"></a><a name="remainderf"></a>Remainderf-Funktion  
 Berechnet den Rest: _X REM _Y  
  
```  
inline float remainderf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
 `_Y`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt _X REM _Y  
  
##  <a name="a-nameremquoa--remquo-function"></a><a name="remquo"></a>Remquo-Funktion  
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
 `_X`  
 Das erste Gleitkommaargument.  
  
 `_Y`  
 Das zweite Gleitkommaargument.  
  
 `_Quo` (Out-Parameter)  
 Die Adresse einer ganzen Zahl, die verwendet wird, um den Quotient der Bruchbytes von `_X` zurückzugeben, dividiert durch die Bruchbytes von `_Y`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Rest von `_X` dividiert durch `_Y` zurück.  
  
##  <a name="a-nameremquofa--remquof-function"></a><a name="remquof"></a>Remquof-Funktion  
 Berechnet den Rest des angegebenen ersten Arguments dividiert durch das zweite angegebene Argument. Berechnet auch den Quotient der angegebenen Mantisse des ersten Arguments, dividiert durch die Mantisse des zweiten angegebenen Arguments und gibt den Quotient mithilfe der im dritten Argument angegebenen Position zurück.  
  
```  
inline float remquof(
    float _X,  
    float _Y,  
    _Out_ int* _Quo) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Das erste Gleitkommaargument.  
  
 `_Y`  
 Das zweite Gleitkommaargument.  
  
 `_Quo` (Out-Parameter)  
 Die Adresse einer ganzen Zahl, die verwendet wird, um den Quotient der Bruchbytes von `_X` zurückzugeben, dividiert durch die Bruchbytes von `_Y`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Rest von `_X` dividiert durch `_Y` zurück.  
  
##  <a name="a-namerounda--round-function"></a><a name="round"></a>Round-Funktion  
 Rundet _X auf die nächste ganze Zahl  
  
```  
inline float round(float _X) restrict(amp);

 
inline double round(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die nächste ganze Zahl von _X  
  
##  <a name="a-nameroundfa--roundf-function"></a><a name="roundf"></a>Roundf-Funktion  
 Rundet _X auf die nächste ganze Zahl  
  
```  
inline float roundf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die nächste ganze Zahl von _X  
  
##  <a name="a-namersqrta--rsqrt-function"></a><a name="rsqrt"></a>Rsqrt-Funktion  
 Gibt den Kehrwert der Quadratwurzel des Arguments zurück  
  
```  
inline float rsqrt(float _X) restrict(amp);

 
inline double rsqrt(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Kehrwert der Quadratwurzel des Arguments zurück  
  
##  <a name="a-namersqrtfa--rsqrtf-function"></a><a name="rsqrtf"></a>Rsqrtf-Funktion  
 Gibt den Kehrwert der Quadratwurzel des Arguments zurück  
  
```  
inline float rsqrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Kehrwert der Quadratwurzel des Arguments zurück  
  
##  <a name="a-namescalba--scalb-function"></a><a name="scalb"></a>Scalb-Funktion  
 Multipliziert _X von FLT_RADIX auf die Power-_Y  
  
```  
inline float scalb(
    float _X,  
    float _Y) restrict(amp);

 
inline double scalb(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
 `_Y`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt _X * (FLT_RADIX ^ _Y)  
  
##  <a name="a-namescalbfa--scalbf-function"></a><a name="scalbf"></a>Scalbf-Funktion  
 Multipliziert _X von FLT_RADIX auf die Power-_Y  
  
```  
inline float scalbf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
 `_Y`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt _X * (FLT_RADIX ^ _Y)  
  
##  <a name="a-namescalbna--scalbn-function"></a><a name="scalbn"></a>Scalbn-Funktion  
 Multipliziert _X von FLT_RADIX auf die Power-_Y  
  
```  
inline float scalbn(
    float _X,  
    int _Y) restrict(amp);

 
inline double scalbn(
    double _X,  
    int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
 `_Y`  
 Ganzzahliger Wert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt _X * (FLT_RADIX ^ _Y)  
  
##  <a name="a-namescalbnfa--scalbnf-function"></a><a name="scalbnf"></a>Scalbnf-Funktion  
 Multipliziert _X von FLT_RADIX auf die Power-_Y  
  
```  
inline float scalbnf(
    float _X,  
    int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
 `_Y`  
 Ganzzahliger Wert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt _X * (FLT_RADIX ^ _Y)  
  
##  <a name="a-namesignbita--signbit-function"></a><a name="signbit"></a>Signbit-Funktion  
 Bestimmt, ob die Vorzeichen von _X negativ ist.  
  
```  
inline int signbit(float _X) restrict(amp);

 
inline int signbit(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert ungleich NULL zurück, wenn die Vorzeichen des _X negativ ist  
  
##  <a name="a-namesignbitfa--signbitf-function"></a><a name="signbitf"></a>Signbitf-Funktion  
 Bestimmt, ob die Vorzeichen von _X negativ ist.  
  
```  
inline int signbitf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert ungleich NULL zurück, wenn die Vorzeichen des _X negativ ist  
  
##  <a name="a-namesina--sin-function"></a><a name="sin"></a>SIN-Funktion  
 Berechnet den Sinuswert des Arguments  
  
```  
inline float sin(float _X) restrict(amp);

 
inline double sin(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Sinuswert des Arguments zurück  
  
##  <a name="a-namesinfa--sinf-function"></a><a name="sinf"></a>Sinf-Funktion  
 Berechnet den Sinuswert des Arguments  
  
```  
inline float sinf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Sinuswert des Arguments zurück  
  
##  <a name="a-namesincosa--sincos-function"></a><a name="sincos"></a>Sincos-Funktion  
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
 `_X`  
 Gleitkommawert  
  
 `_S`  
 Gibt den Sinuswert des _X  
  
 `_C`  
 Gibt den Kosinuswert von _X  
  
##  <a name="a-namesincosfa--sincosf-function"></a><a name="sincosf"></a>Sincosf-Funktion  
 Berechnet Sinus- und Kosinuswert von _X  
  
```  
inline void sincosf(
    float _X,  
    _Out_ float* _S,  
    _Out_ float* _C) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
 `_S`  
 Gibt den Sinuswert des _X  
  
 `_C`  
 Gibt den Kosinuswert von _X  
  
##  <a name="a-namesinha--sinh-function"></a><a name="sinh"></a>Sinh-Funktion  
 Berechnet den Hyperbelsinuswert des Arguments  
  
```  
inline float sinh(float _X) restrict(amp);

 
inline double sinh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den hyperbolischen Sinus-Wert des Arguments zurück  
  
##  <a name="a-namesinhfa--sinhf-function"></a><a name="sinhf"></a>Sinhf-Funktion  
 Berechnet den Hyperbelsinuswert des Arguments  
  
```  
inline float sinhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den hyperbolischen Sinus-Wert des Arguments zurück  
  
##  <a name="a-namesinpia--sinpi-function"></a><a name="sinpi"></a>Sinpi-Funktion  
 Berechnet den Sinuswert von Pi * _X  
  
```  
inline float sinpi(float _X) restrict(amp);

 
inline double sinpi(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Sinuswert des Pi * _X  
  
##  <a name="a-namesinpifa--sinpif-function"></a><a name="sinpif"></a>Sinpif-Funktion  
 Berechnet den Sinuswert von Pi * _X  
  
```  
inline float sinpif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Sinuswert des Pi * _X  
  
##  <a name="a-namesqrta--sqrt-function"></a><a name="sqrt"></a>Sqrt-Funktion  
 Berechnet den Squre Stamm des Arguments  
  
```  
inline float sqrt(float _X) restrict(amp);

 
inline double sqrt(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Stamm Squre des Arguments zurück  
  
##  <a name="a-namesqrtfa--sqrtf-function"></a><a name="sqrtf"></a>Sqrtf-Funktion  
 Berechnet den Squre Stamm des Arguments  
  
```  
inline float sqrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Stamm Squre des Arguments zurück  
  
##  <a name="a-nametana--tan-function"></a><a name="tan"></a>Tan-Funktion  
 Berechnet den Tangenswert des Arguments  
  
```  
inline float tan(float _X) restrict(amp);

 
inline double tan(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Tangenswert des Arguments zurück  
  
##  <a name="a-nametanfa--tanf-function"></a><a name="tanf"></a>Tanf-Funktion  
 Berechnet den Tangenswert des Arguments  
  
```  
inline float tanf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Tangenswert des Arguments zurück  
  
##  <a name="a-nametanha--tanh-function"></a><a name="tanh"></a>Tanh-Funktion  
 Berechnet den Hyperbeltangenswert des Arguments  
  
```  
inline float tanh(float _X) restrict(amp);

 
inline double tanh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den hyperbeltangenswert des Arguments zurück  
  
##  <a name="a-nametanhfa--tanhf-function"></a><a name="tanhf"></a>Tanhf-Funktion  
 Berechnet den Hyperbeltangenswert des Arguments  
  
```  
inline float tanhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den hyperbeltangenswert des Arguments zurück  
  
##  <a name="a-nametanpia--tanpi-function"></a><a name="tanpi"></a>Tanpi-Funktion  
 Berechnet den Tangenswert von Pi * _X  
  
```  
inline float tanpi(float _X) restrict(amp);

 
inline double tanpi(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Tangenswert von Pi * _X  
  
##  <a name="a-nametanpifa--tanpif-function"></a><a name="tanpif"></a>Tanpif-Funktion  
 Berechnet den Tangenswert von Pi * _X  
  
```  
inline float tanpif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Tangenswert von Pi * _X  
  
##  <a name="a-nametgammaa--tgamma-function"></a><a name="tgamma"></a>Tgamma-Funktion  
 Berechnet die Gammafunktion von _X  
  
```  
inline float tgamma(float _X) restrict(amp);

 
inline double tgamma(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Ergebnis der Gammafunktion von _X  
  
##  <a name="a-nametgammafa--tgammaf-function"></a><a name="tgammaf"></a>Tgammaf-Funktion  
 Berechnet die Gammafunktion von _X  
  
```  
inline float tgammaf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Ergebnis der Gammafunktion von _X  
  
##  <a name="a-nametrunca--trunc-function"></a><a name="trunc"></a>TRUNC-Funktion  
 Schneidet das Argument der ganzzahligen Komponente ab  
  
```  
inline float trunc(float _X) restrict(amp);

 
inline double trunc(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die ganze Zahl-Komponente des Arguments zurück  
  
##  <a name="a-nametruncfa--truncf-function"></a><a name="truncf"></a>Truncf-Funktion  
 Schneidet das Argument der ganzzahligen Komponente ab  
  
```  
inline float truncf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die ganze Zahl-Komponente des Arguments zurück  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency:: precise_math-Namespace](concurrency-precise-math-namespace.md)

