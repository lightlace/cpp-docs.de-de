---
title: 'Concurrency:: fast_math-Namespace Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_math/Concurrency::fast_math::acos
- amp_math/Concurrency::fast_math::asin
- amp_math/Concurrency::fast_math::asinf
- amp_math/Concurrency::fast_math::atan2
- amp_math/Concurrency::fast_math::atan2f
- amp_math/Concurrency::fast_math::ceil
- amp_math/Concurrency::fast_math::ceilf
- amp_math/Concurrency::fast_math::cosf
- amp_math/Concurrency::fast_math::cosh
- amp_math/Concurrency::fast_math::exp
- amp_math/Concurrency::fast_math::exp2
- amp_math/Concurrency::fast_math::expf
- amp_math/Concurrency::fast_math::fabs
- amp_math/Concurrency::fast_math::floor
- amp_math/Concurrency::fast_math::floorf
- amp_math/Concurrency::fast_math::fmaxf
- amp_math/Concurrency::fast_math::fmin
- amp_math/Concurrency::fast_math::fmod
- amp_math/Concurrency::fast_math::fmodf
- amp_math/Concurrency::fast_math::frexpf
- amp_math/Concurrency::fast_math::isfinite
- amp_math/Concurrency::fast_math::isnan
- amp_math/Concurrency::fast_math::ldexp
- amp_math/Concurrency::fast_math::log
- amp_math/Concurrency::fast_math::log10
- amp_math/Concurrency::fast_math::log2
- amp_math/Concurrency::fast_math::log2f
- amp_math/Concurrency::fast_math::modf
- amp_math/Concurrency::fast_math::modff
- amp_math/Concurrency::fast_math::powf
- amp_math/Concurrency::fast_math::round
- amp_math/Concurrency::fast_math::rsqrt
- amp_math/Concurrency::fast_math::rsqrtf
- amp_math/Concurrency::fast_math::signbitf
- amp_math/Concurrency::fast_math::sin
- amp_math/Concurrency::fast_math::sincosf
- amp_math/Concurrency::fast_math::sinf
- amp_math/Concurrency::fast_math::sinhf
- amp_math/Concurrency::fast_math::sqrt
- amp_math/Concurrency::fast_math::tan
- amp_math/Concurrency::fast_math::tanf
- amp_math/Concurrency::fast_math::tanhf
- amp_math/Concurrency::fast_math::trunc
dev_langs:
- C++
ms.assetid: f5763d62-795b-4de6-a7a5-c7115f158708
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 2ca8b085c7dcc226a216032060e628c7c7ce0a4a
ms.lasthandoff: 03/17/2017

---
# <a name="concurrencyfastmath-namespace-functions"></a>Concurrency:: fast_math-Namespace-Funktionen
||||  
|-|-|-|  
|[acos](#acos)|[acosf](#acosf)|[asin](#asin)|  
|[asinf](#asinf)|[atan](#atan)|[atan2](#atan2)|  
|[atan2f](#atan2f)|[atanf](#atanf)|[ceil](#ceil)|  
|[ceilf](#ceilf)|[cos](#cos)|[cosf](#cosf)|  
|[cosh](#cosh)|[coshf](#coshf)|[exp](#exp)|  
|[exp2](#exp2)|[exp2f](#exp2f)|[expf](#expf)|  
|[fabs](#fabs)|[fabsf](#fabsf)|[floor](#floor)|  
|[floorf](#floorf)|[fmax](#fmax)|[fmaxf](#fmaxf)|  
|[fmin](#fmin)|[fminf](#fminf)|[fmod](#fmod)|  
|[fmodf](#fmodf)|[frexp](#frexp)|[frexpf](#frexpf)|  
|[isFinite](#isfinite)|[isinf](#isinf)|[isnan](#isnan)|  
|[ldexp](#ldexp)|[ldexpf](#ldexpf)|[log](#log)|  
|[log10](#log10)|[log10f](#log10f)|[log2](#log2)|  
|[log2f](#log2f)|[logf](#logf)|[modf](#modf)|  
|[modff](#modff)|[pow](#pow)|[powf](#powf)|  
|[round](#round)|[roundf](#roundf)|[rsqrt](#rsqrt)|  
|[rsqrtf](#rsqrtf)|[signbit](#signbit)|[signbitf](#signbitf)|  
|[sin](#sin)|[sincos](#sincos)|[sincosf](#sincosf)|  
|[sinf](#sinf)|[sinh](#sinh)|[sinhf](#sinhf)|  
|[sqrt](#sqrt)|[sqrtf](#sqrtf)|[tan](#tan)|  
|[tanf](#tanf)|[tanh](#tanh)|[tanhf](#tanhf)|  
|[trunc](#trunc)|[truncf](#truncf)|  
  
##  <a name="acos"></a> acos  
 Berechnet den Arkuskosinus des Arguments  
  
```  
inline float acos(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Arkuskosinus-Wert des Arguments zurück  
  
##  <a name="acosf"></a>acosf  
 Berechnet den Arkuskosinus des Arguments  
  
```  
inline float acosf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Arkuskosinus-Wert des Arguments zurück  
  
##  <a name="asin"></a> asin  
 Berechnet den Arkussinus des Arguments  
  
```  
inline float asin(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Arkussinus-Wert des Arguments zurück  
  
##  <a name="asinf"></a>asinf  
 Berechnet den Arkussinus des Arguments  
  
```  
inline float asinf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Arkussinus-Wert des Arguments zurück  
  
##  <a name="atan"></a> atan  
 Berechnet den Arkustangens des Arguments  
  
```  
inline float atan(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Arkustangens-Wert des Arguments zurück  
  
##  <a name="atan2"></a> atan2  
 Berechnet den Arkustangens von _Y/_X  
  
```  
inline float atan2(
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
  
##  <a name="atan2f"></a>atan2f  
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
  
##  <a name="atanf"></a>atanf  
 Berechnet den Arkustangens des Arguments  
  
```  
inline float atanf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Arkustangens-Wert des Arguments zurück  
  
##  <a name="ceil"></a>ceil  
 Berechnet den Höchstwert des Arguments  
  
```  
inline float ceil(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Höchstwert des Arguments zurück  
  
##  <a name="ceilf"></a>ceilf  
 Berechnet den Höchstwert des Arguments  
  
```  
inline float ceilf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Höchstwert des Arguments zurück  
  
##  <a name="cosf"></a>cosf  
 Berechnet den Kosinus des Arguments  
  
```  
inline float cosf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Kosinuswert des Arguments zurück  
  
##  <a name="coshf"></a>coshf  
 Berechnet den Hyperbelkosinuswert des Arguments  
  
```  
inline float coshf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den hyperbolischen Kosinus-Wert des Arguments zurück  
  
##  <a name="cos"></a> cos  
 Berechnet den Kosinus des Arguments  
  
```  
inline float cos(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Kosinuswert des Arguments zurück  
  
##  <a name="cosh"></a> cosh  
 Berechnet den Hyperbelkosinuswert des Arguments  
  
```  
inline float cosh(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den hyperbolischen Kosinus-Wert des Arguments zurück  
  
##  <a name="exp"></a> exp  
 Berechnet die Basis-E, die vom Argument exponential ist  
  
```  
inline float exp(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die vom Argument exponential Basis-e  
  
##  <a name="exp2"></a>EXP2  
 Berechnet die Basis-2, die vom Argument exponential ist  
  
```  
inline float exp2(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die vom Argument exponential Basis-2  
  
##  <a name="exp2f"></a>exp2f  
 Berechnet die Basis-2, die vom Argument exponential ist  
  
```  
inline float exp2f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die vom Argument exponential Basis-2  
  
##  <a name="expf"></a>expf  
 Berechnet die Basis-E, die vom Argument exponential ist  
  
```  
inline float expf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die vom Argument exponential Basis-e  
  
##  <a name="fabs"></a>Fabs  
 Gibt den absoluten Wert des Arguments zurück.  
  
```  
inline float fabs(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Ganzzahliger Wert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den absoluten Wert des Arguments zurück.  
  
##  <a name="fabsf"></a>fabsf  
 Gibt den absoluten Wert des Arguments zurück.  
  
```  
inline float fabsf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den absoluten Wert des Arguments zurück.  
  
##  <a name="floor"></a>Floor  
 Berechnet den Tiefstwert des Arguments  
  
```  
inline float floor(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Untergrenze des Arguments  
  
##  <a name="floorf"></a>floorf  
 Berechnet den Tiefstwert des Arguments  
  
```  
inline float floorf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Untergrenze des Arguments  
  
##  <a name="fmax"></a>Fmax  
 Festlegung des höchsten numerischen Werts der Argumente  
  
```  
inline float max(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Ganzzahliger Wert  
  
 `_Y`  
 Ganzzahliger Wert  
  
### <a name="return-value"></a>Rückgabewert  
 Rückgabe des höchsten numerischen Werts der Argumente  
  
##  <a name="fmaxf"></a>fmaxf  
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
  
##  <a name="fmin"></a>fmin  
 Festlegung des niedrigsten numerischen Werts der Argumente  
  
```  
inline float min(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Ganzzahliger Wert  
  
 `_Y`  
 Ganzzahliger Wert  
  
### <a name="return-value"></a>Rückgabewert  
 Rückgabe des niedrigsten numerischen Werts der Argumente  
  
##  <a name="fminf"></a>fminf  
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
  
##  <a name="fmod"></a>fmod  
 Berechnet den Gleitkommarest von _X/_Y  
  
```  
inline float fmod(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
 `_Y`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Gleitkommarest von _X/_Y  
  
##  <a name="fmodf"></a>fmodf  
 Berechnet den Gleitkommarest von _X/_Y.  
  
```  
inline float fmodf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
 `_Y`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Gleitkommarest von _X/_Y  
  
##  <a name="frexp"></a>frexp  
 Ruft die Mantisse und den Exponenten von _X ab  
  
```  
inline float frexp(
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
  
##  <a name="frexpf"></a>frexpf  
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
  
##  <a name="isfinite"></a>isFinite  
 Bestimmt, ob das Argument einen über begrenzten Wert verfügt  
  
```  
inline int isfinite(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert ungleich NULL nur, wenn das Argument einen begrenzten Wert verfügt.  
  
##  <a name="isinf"></a>isinf  
 Bestimmt, ob das Argument unendlich ist  
  
```  
inline int isinf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert ungleich NULL nur, wenn das Argument einen unendlichen Wert hat.  
  
##  <a name="isnan"></a>IsNaN  
 Bestimmt, ob das Argument ein NaN  
  
```  
inline int isnan(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert ungleich NULL nur, wenn das Argument einen NaN-Wert hat.  
  
##  <a name="ldexp"></a>ldexp  
 Berechnet eine reelle Zahl aus der Mantisse und dem Exponent  
  
```  
inline float ldexp(
    float _X,  
    int _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert, mentissa  
  
 `_Exp`  
 Ganzzahlexponent  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt _X * 2^_Exp zurück  
  
##  <a name="ldexpf"></a>ldexpf  
 Berechnet eine reelle Zahl aus der Mantisse und dem Exponent  
  
```  
inline float ldexpf(
    float _X,  
    int _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert, mentissa  
  
 `_Exp`  
 Ganzzahlexponent  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt _X * 2^_Exp zurück  
  
##  <a name="log"></a> log  
 Berechnet den Basis-E-Logarithmus des Arguments  
  
```  
inline float log(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Basis-e-Logarithmus des Arguments  
  
##  <a name="log10"></a> log10  
 Berechnet den Basis-10-Logarithmus des Arguments  
  
```  
inline float log10(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Base-10-Logarithmus des Arguments  
  
##  <a name="log10f"></a>log10f  
 Berechnet den Basis-10-Logarithmus des Arguments  
  
```  
inline float log10f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Base-10-Logarithmus des Arguments  
  
##  <a name="log2"></a>Log2  
 Berechnet den Basis-2-Logarithmus des Arguments  
  
```  
inline float log2(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Logarithmus Basis&2; des Arguments zurück  
  
##  <a name="log2f"></a>log2f  
 Berechnet den Basis-2-Logarithmus des Arguments  
  
```  
inline float log2f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Base-10-Logarithmus des Arguments  
  
##  <a name="logf"></a>logf  
 Berechnet den Basis-E-Logarithmus des Arguments  
  
```  
inline float logf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Basis-e-Logarithmus des Arguments  
  
##  <a name="modf"></a>modf  
 Teilt _X in Nachkommastellen und ganze Zahlen auf.  
  
```  
inline float modf(
    float _X,  
    float* _Ip) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
 `_Ip`  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Bruchteil mit Vorzeichen von _X  
  
##  <a name="modff"></a>modff  
 Teilt _X in Nachkommastellen und ganze Zahlen auf.  
  
```  
inline float modff(
    float _X,  
    float* _Ip) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
 `_Ip`  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Bruchteil mit Vorzeichen von _X  
  
##  <a name="pow"></a> pow  
 Berechnet _X potenziert mit _Y  
  
```  
inline float pow(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert, Basis  
  
 `_Y`  
 Gleitkommawert, exponent  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert der _X potenziert mit _y  
  
##  <a name="powf"></a>powf  
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
  
##  <a name="round"></a>runden  
 Rundet _X auf die nächste ganze Zahl  
  
```  
inline float round(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die nächste ganze Zahl von _X  
  
##  <a name="roundf"></a>roundf  
 Rundet _X auf die nächste ganze Zahl  
  
```  
inline float roundf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die nächste ganze Zahl von _X  
  
##  <a name="rsqrt"></a>rsqrt  
 Gibt den Kehrwert der Quadratwurzel des Arguments zurück  
  
```  
inline float rsqrt(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Kehrwert der Quadratwurzel des Arguments zurück  
  
##  <a name="rsqrtf"></a>rsqrtf  
 Gibt den Kehrwert der Quadratwurzel des Arguments zurück  
  
```  
inline float rsqrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Kehrwert der Quadratwurzel des Arguments zurück  
  
##  <a name="signbit"></a>signbit  
 Bestimmt, ob die Vorzeichen von _X negativ ist.  
  
```  
inline int signbit(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert ungleich NULL zurück, wenn die Vorzeichen des _X negativ ist  
  
##  <a name="signbitf"></a>signbitf  
 Bestimmt, ob die Vorzeichen von _X negativ ist.  
  
```  
inline int signbitf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert ungleich NULL zurück, wenn die Vorzeichen des _X negativ ist  
  
##  <a name="sin"></a> sin  
 Berechnet den Sinuswert des Arguments  
  
```  
inline float sin(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Sinuswert des Arguments zurück  
  
##  <a name="sinf"></a>sinf  
 Berechnet den Sinuswert des Arguments  
  
```  
inline float sinf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Sinuswert des Arguments zurück  
  
##  <a name="sincos"></a>sincos  
 Berechnet Sinus- und Kosinuswert von _X  
  
```  
inline void sincos(
    float _X,  
    float* _S,  
    float* _C) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
 `_S`  
 Gibt den Sinuswert des _X  
  
 `_C`  
 Gibt den Kosinuswert von _X  
  
##  <a name="sincosf"></a>sincosf  
 Berechnet Sinus- und Kosinuswert von _X  
  
```  
inline void sincosf(
    float _X,  
    float* _S,  
    float* _C) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
 `_S`  
 Gibt den Sinuswert des _X  
  
 `_C`  
 Gibt den Kosinuswert von _X  
  
##  <a name="sinh"></a> sinh  
 Berechnet den Hyperbelsinuswert des Arguments  
  
```  
inline float sinh(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den hyperbolischen Sinus-Wert des Arguments zurück  
  
##  <a name="sinhf"></a>sinhf  
 Berechnet den Hyperbelsinuswert des Arguments  
  
```  
inline float sinhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den hyperbolischen Sinus-Wert des Arguments zurück  
  
##  <a name="sqrt"></a> sqrt  
 Berechnet den Squre Stamm des Arguments  
  
```  
inline float sqrt(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Stamm Squre des Arguments zurück  
  
##  <a name="sqrtf"></a>sqrtf  
 Berechnet den Squre Stamm des Arguments  
  
```  
inline float sqrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Stamm Squre des Arguments zurück  
  
##  <a name="tan"></a> tan  
 Berechnet den Tangenswert des Arguments  
  
```  
inline float tan(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Tangenswert des Arguments zurück  
  
##  <a name="tanf"></a>tanf  
 Berechnet den Tangenswert des Arguments  
  
```  
inline float tanf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Tangenswert des Arguments zurück  
  
##  <a name="tanh"></a> tanh  
 Berechnet den Hyperbeltangenswert des Arguments  
  
```  
inline float tanh(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den hyperbeltangenswert des Arguments zurück  
  
##  <a name="tanhf"></a>tanhf  
 Berechnet den Hyperbeltangenswert des Arguments  
  
```  
inline float tanhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den hyperbeltangenswert des Arguments zurück  
  
##  <a name="trunc"></a>trunc  
 Schneidet das Argument der ganzzahligen Komponente ab  
  
```  
inline float trunc(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die ganze Zahl-Komponente des Arguments zurück  
  
##  <a name="truncf"></a>truncf  
 Schneidet das Argument der ganzzahligen Komponente ab  
  
```  
inline float truncf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die ganze Zahl-Komponente des Arguments zurück  

## <a name="requirements"></a>Anforderungen
**Header:** amp_math.h **Namespace:** Concurrency:: fast_math
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency::fast_math Namespace](concurrency-fast-math-namespace.md)

