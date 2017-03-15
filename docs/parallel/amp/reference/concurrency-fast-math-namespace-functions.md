---
title: 'Concurrency:: fast_math-Namespace Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f5763d62-795b-4de6-a7a5-c7115f158708
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 4a01f48a7d087281ab1e9222d1077e92ab8b0d6c
ms.openlocfilehash: 0545a57c492f5c1872c71c04c99b54f86b644102
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencyfastmath-namespace-functions"></a>Concurrency:: fast_math-Namespace-Funktionen
||||  
|-|-|-|  
|[ACOS-Funktion](#acos)|[Acosf-Funktion](#acosf)|[ASIN-Funktion](#asin)|  
|[Asinf-Funktion](#asinf)|[ATAN-Funktion](#atan)|[atan2-Funktion](#atan2)|  
|[atan2f-Funktion](#atan2f)|[Atanf-Funktion](#atanf)|[ceil-Funktion](#ceil)|  
|[Ceilf-Funktion](#ceilf)|[cos Funktion](#cos)|[Cosf-Funktion](#cosf)|  
|[cosh-Funktion](#cosh)|[Coshf-Funktion](#coshf)|[EXP-Funktion](#exp)|  
|[EXP2-Funktion](#exp2)|[exp2f-Funktion](#exp2f)|[Expf-Funktion](#expf)|  
|[Fabs-Funktion](#fabs)|[Fabsf-Funktion](#fabsf)|[Floor-Funktion](#floor)|  
|[Floorf-Funktion](#floorf)|[Fmax-Funktion](#fmax)|[Fmaxf-Funktion](#fmaxf)|  
|[Fmin-Funktion](#fmin)|[Fminf-Funktion](#fminf)|[fmod-Funktion](#fmod)|  
|[Fmodf-Funktion](#fmodf)|[Frexp-Funktion](#frexp)|[Frexpf-Funktion](#frexpf)|  
|[IsFinite-Funktion](#isfinite)|[Isinf-Funktion](#isinf)|[IsNaN-Funktion](#isnan)|  
|[Ldexp-Funktion](#ldexp)|[Ldexpf-Funktion](#ldexpf)|[log-Funktion](#log)|  
|[LOG10-Funktion](#log10)|[log10f-Funktion](#log10f)|[log2-Funktion](#log2)|  
|[log2f-Funktion](#log2f)|[Logf-Funktion](#logf)|[Modf-Funktion](#modf)|  
|[Modff-Funktion](#modff)|[Pow-Funktion](#pow)|[Powf-Funktion](#powf)|  
|[Round-Funktion](#round)|[Roundf-Funktion](#roundf)|[Rsqrt-Funktion](#rsqrt)|  
|[Rsqrtf-Funktion](#rsqrtf)|[Signbit-Funktion](#signbit)|[Signbitf-Funktion](#signbitf)|  
|[SIN-Funktion](#sin)|[Sincos-Funktion](#sincos)|[Sincosf-Funktion](#sincosf)|  
|[Sinf-Funktion](#sinf)|[Sinh-Funktion](#sinh)|[Sinhf-Funktion](#sinhf)|  
|[Sqrt-Funktion](#sqrt)|[Sqrtf-Funktion](#sqrtf)|[Tan-Funktion](#tan)|  
|[Tanf-Funktion](#tanf)|[Tanh-Funktion](#tanh)|[Tanhf-Funktion](#tanhf)|  
|[TRUNC-Funktion](#trunc)|[Truncf-Funktion](#truncf)|  
  
##  <a name="a-nameacosa--acos-function"></a><a name="acos"></a>ACOS-Funktion  
 Berechnet den Arkuskosinus des Arguments  
  
```  
inline float acos(float _X) restrict(amp);
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
  
##  <a name="a-nameasina--asin-function"></a><a name="asin"></a>ASIN-Funktion  
 Berechnet den Arkussinus des Arguments  
  
```  
inline float asin(float _X) restrict(amp);
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
  
##  <a name="a-nameatana--atan-function"></a><a name="atan"></a>ATAN-Funktion  
 Berechnet den Arkustangens des Arguments  
  
```  
inline float atan(float _X) restrict(amp);
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
  
##  <a name="a-nameceila--ceil-function"></a><a name="ceil"></a>ceil-Funktion  
 Berechnet den Höchstwert des Arguments  
  
```  
inline float ceil(float _X) restrict(amp);
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
  
##  <a name="a-namecosa--cos-function"></a><a name="cos"></a>cos Funktion   
 Berechnet den Kosinus des Arguments  
  
```  
inline float cos(float _X) restrict(amp);
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
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den hyperbolischen Kosinus-Wert des Arguments zurück  
  
##  <a name="a-nameexpa--exp-function"></a><a name="exp"></a>EXP-Funktion  
 Berechnet die Basis-E, die vom Argument exponential ist  
  
```  
inline float exp(float _X) restrict(amp);
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
  
##  <a name="a-namefabsa--fabs-function"></a><a name="fabs"></a>Fabs-Funktion  
 Gibt den absoluten Wert des Arguments zurück.  
  
```  
inline float fabs(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Ganzzahliger Wert  
  
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
  
##  <a name="a-namefloora--floor-function"></a><a name="floor"></a>Floor-Funktion  
 Berechnet den Tiefstwert des Arguments  
  
```  
inline float floor(float _X) restrict(amp);
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
  
##  <a name="a-namefmaxa--fmax-function"></a><a name="fmax"></a>Fmax-Funktion  
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
  
##  <a name="a-namefmoda--fmod-function"></a><a name="fmod"></a>Fmod-Funktion  
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
  
##  <a name="a-namefmodfa--fmodf-function"></a><a name="fmodf"></a>Fmodf-Funktion  
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
  
##  <a name="a-namefrexpa--frexp-function"></a><a name="frexp"></a>Frexp-Funktion  
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
  
##  <a name="a-nameisfinitea--isfinite-function"></a><a name="isfinite"></a>IsFinite-Funktion  
 Bestimmt, ob das Argument einen über begrenzten Wert verfügt  
  
```  
inline int isfinite(float _X) restrict(amp);
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
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert ungleich NULL nur, wenn das Argument einen NaN-Wert hat.  
  
##  <a name="a-nameldexpa--ldexp-function"></a><a name="ldexp"></a>Ldexp-Funktion  
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
  
##  <a name="a-nameldexpfa--ldexpf-function"></a><a name="ldexpf"></a>Ldexpf-Funktion  
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
  
##  <a name="a-nameloga--log-function"></a><a name="log"></a>log-Funktion  
 Berechnet den Basis-E-Logarithmus des Arguments  
  
```  
inline float log(float _X) restrict(amp);
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
  
##  <a name="a-namelog2a--log2-function"></a><a name="log2"></a>log2-Funktion  
 Berechnet den Basis-2-Logarithmus des Arguments  
  
```  
inline float log2(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
 `_X`  
 Gleitkommawert  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Logarithmus Basis&2; des Arguments zurück  
  
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
  
##  <a name="a-namemodffa--modff-function"></a><a name="modff"></a>Modff-Funktion  
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
  
##  <a name="a-namepowa--pow-function"></a><a name="pow"></a>Pow-Funktion  
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
  
##  <a name="a-namerounda--round-function"></a><a name="round"></a>Round-Funktion  
 Rundet _X auf die nächste ganze Zahl  
  
```  
inline float round(float _X) restrict(amp);
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
  
##  <a name="a-namesignbita--signbit-function"></a><a name="signbit"></a>Signbit-Funktion  
 Bestimmt, ob die Vorzeichen von _X negativ ist.  
  
```  
inline int signbit(float _X) restrict(amp);
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
  
##  <a name="a-namesincosfa--sincosf-function"></a><a name="sincosf"></a>Sincosf-Funktion  
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
  
##  <a name="a-namesinha--sinh-function"></a><a name="sinh"></a>Sinh-Funktion  
 Berechnet den Hyperbelsinuswert des Arguments  
  
```  
inline float sinh(float _X) restrict(amp);
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
  
##  <a name="a-namesqrta--sqrt-function"></a><a name="sqrt"></a>Sqrt-Funktion  
 Berechnet den Squre Stamm des Arguments  
  
```  
inline float sqrt(float _X) restrict(amp);
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
  
##  <a name="a-nametrunca--trunc-function"></a><a name="trunc"></a>TRUNC-Funktion  
 Schneidet das Argument der ganzzahligen Komponente ab  
  
```  
inline float trunc(float _X) restrict(amp);
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
 [Concurrency:: fast_math-Namespace](concurrency-fast-math-namespace.md)

