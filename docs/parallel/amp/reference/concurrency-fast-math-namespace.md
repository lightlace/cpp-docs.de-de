---
title: 'Concurrency:: fast_math-Namespace | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_math/Concurrency::fast_math
dev_langs:
- C++
ms.assetid: 54fed939-9902-49db-9f29-e98fd9821508
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 293452bf0a01f7f83a8a41bcb511bc57c9d45f26
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencyfastmath-namespace"></a>Concurrency::fast_math-Namespace
Funktionen im `fast_math`-Namespace haben eine geringere Genauigkeit, unterstützen nur mit einfacher Genauigkeit (`float`) und rufen die systeminternen DirectX-Funktionen auf. Es gibt zwei Versionen jeder Funktion, beispielsweise `cos` und `cosf`. Beide Versionen erstellen und geben einen `float`-Wert zurück, aber jede ruft die gleiche systeminterne DirectX-Funktion auf.  
  
## <a name="syntax"></a>Syntax  
  
```  
namespace fast_math;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="functions"></a>Funktionen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[cos-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#cos)|Berechnet den Arkuskosinus des Arguments|  
|[Cosf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#cosf)|Berechnet den Arkuskosinus des Arguments|  
|[ASIN-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#asin)|Berechnet den Arkussinus des Arguments|  
|[Asinf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#asinf)|Berechnet den Arkussinus des Arguments|  
|[ATAN-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#atan)|Berechnet den Arkustangens des Arguments|  
|[atan2-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#atan2)|Berechnet den Arkustangens von _Y/_X|  
|[atan2f-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#atan2f)|Berechnet den Arkustangens von _Y/_X|  
|[Atanf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#atanf)|Berechnet den Arkustangens des Arguments|  
|[ceil-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#ceil)|Berechnet den Höchstwert des Arguments|  
|[Ceilf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#ceilf)|Berechnet den Höchstwert des Arguments|  
|[cos-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#cos)|Berechnet den Kosinus des Arguments|  
|[Cosf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#cosf)|Berechnet den Kosinus des Arguments|  
|[cosh-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#cosh)|Berechnet den Hyperbelkosinuswert des Arguments|  
|[Coshf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#coshf)|Berechnet den Hyperbelkosinuswert des Arguments|  
|[EXP-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#exp)|Berechnet die Basis-E, die vom Argument exponential ist|  
|[EXP2-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#exp2)|Berechnet die Basis-2, die vom Argument exponential ist|  
|[exp2f-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#exp2f)|Berechnet die Basis-2, die vom Argument exponential ist|  
|[Expf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#expf)|Berechnet die Basis-E, die vom Argument exponential ist|  
|[Fabs-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#fabs)|Gibt den absoluten Wert des Arguments zurück.|  
|[Fabsf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#fabsf)|Gibt den absoluten Wert des Arguments zurück.|  
|[Floor-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#floor)|Berechnet den Tiefstwert des Arguments|  
|[Floorf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#floorf)|Berechnet den Tiefstwert des Arguments|  
|[Fmax-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#fmax)|Festlegung des höchsten numerischen Werts der Argumente|  
|[Fmaxf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#fmaxf)|Festlegung des höchsten numerischen Werts der Argumente|  
|[Fmin-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#fmin)|Festlegung des niedrigsten numerischen Werts der Argumente|  
|[Fminf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#fminf)|Festlegung des niedrigsten numerischen Werts der Argumente|  
|[Fmod-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#fmod)|Berechnet den Gleitkommarest von _X/_Y|  
|[Fmodf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#fmodf)|Berechnet den Gleitkommarest von _X/_Y|  
|[Frexp-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#frexp)|Ruft die Mantisse und den Exponenten von _X ab|  
|[Frexpf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#frexpf)|Ruft die Mantisse und den Exponenten von _X ab|  
|[IsFinite-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#isfinite)|Bestimmt, ob das Argument einen über begrenzten Wert verfügt|  
|[Isinf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#isinf)|Bestimmt, ob das Argument unendlich ist|  
|[IsNaN-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#isnan)|Bestimmt, ob das Argument ein NaN|  
|[Ldexp-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#ldexp)|Berechnet eine reelle Zahl aus der Mantisse und dem Exponent|  
|[Ldexpf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#ldexpf)|Berechnet eine reelle Zahl aus der Mantisse und dem Exponent|  
|[log-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#log)|Berechnet den Basis-E-Logarithmus des Arguments|  
|[LOG10-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#log10)|Berechnet den Basis-10-Logarithmus des Arguments|  
|[log10f-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#log10f)|Berechnet den Basis-10-Logarithmus des Arguments|  
|[log2-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#log2)|Berechnet den Basis-2-Logarithmus des Arguments|  
|[log2f-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#log2f)|Berechnet den Basis-2-Logarithmus des Arguments|  
|[Logf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#logf)|Berechnet den Basis-E-Logarithmus des Arguments|  
|[Modf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#modf)|Teilt _X in Nachkommastellen und ganze Zahlen auf.|  
|[Modff-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#modff)|Teilt _X in Nachkommastellen und ganze Zahlen auf.|  
|[Pow-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#pow)|Berechnet _X potenziert mit _Y|  
|[Powf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#powf)|Berechnet _X potenziert mit _Y|  
|[Round-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#round)|Rundet _X auf die nächste ganze Zahl|  
|[Roundf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#roundf)|Rundet _X auf die nächste ganze Zahl|  
|[Rsqrt-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#rsqrt)|Gibt den Kehrwert der Quadratwurzel des Arguments zurück|  
|[Rsqrtf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#rsqrtf)|Gibt den Kehrwert der Quadratwurzel des Arguments zurück|  
|[Signbit-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#signbit)|Gibt das Vorzeichen des Arguments zurück|  
|[Signbitf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#signbitf)|Gibt das Vorzeichen des Arguments zurück|  
|[SIN-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#sin)|Berechnet den Sinuswert des Arguments|  
|[Sincos-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#sincos)|Berechnet Sinus- und Kosinuswert von _X|  
|[Sincosf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#sincosf)|Berechnet Sinus- und Kosinuswert von _X|  
|[Sinf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#sinf)|Berechnet den Sinuswert des Arguments|  
|[Sinh-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#sinh)|Berechnet den Hyperbelsinuswert des Arguments|  
|[Sinhf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#sinhf)|Berechnet den Hyperbelsinuswert des Arguments|  
|[Sqrt-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#sqrt)|Berechnet die Quadratwurzel des Arguments|  
|[Sqrtf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#sqrtf)|Berechnet die Quadratwurzel des Arguments|  
|[tan-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#tan)|Berechnet den Tangenswert des Arguments|  
|[Tanf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#tanf)|Berechnet den Tangenswert des Arguments|  
|[Tanh-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#tanh)|Berechnet den Hyperbeltangenswert des Arguments|  
|[Tanhf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#tanhf)|Berechnet den Hyperbeltangenswert des Arguments|  
|[TRUNC-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#trunc)|Schneidet das Argument der ganzzahligen Komponente ab|  
|[Truncf-Funktion (Fast_math)](concurrency-fast-math-namespace-functions.md#truncf)|Schneidet das Argument der ganzzahligen Komponente ab|  

## <a name="requirements"></a>Anforderungen  
 **Header:** amp_math.h  
  
 **Namespace:** Concurrency:: fast_math  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++-AMP)](concurrency-namespace-cpp-amp.md)

