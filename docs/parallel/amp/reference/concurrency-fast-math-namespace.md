---
title: 'Concurrency:: fast_math-Namespace | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- amp_math/Concurrency::fast_math
dev_langs:
- C++
ms.assetid: 54fed939-9902-49db-9f29-e98fd9821508
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 04a9cd3d604b18e42202bccb287cce7c7416b51f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692157"
---
# <a name="concurrencyfastmath-namespace"></a>Concurrency::fast_math-Namespace
Funktionen im `fast_math`-Namespace haben eine geringere Genauigkeit, unterstützen nur mit einfacher Genauigkeit (`float`) und rufen die systeminternen DirectX-Funktionen auf. Es gibt zwei Versionen jeder Funktion, beispielsweise `cos` und `cosf`. Beide Versionen erstellen und geben einen `float`-Wert zurück, aber jede ruft die gleiche systeminterne DirectX-Funktion auf.  
  
## <a name="syntax"></a>Syntax  
  
```  
namespace fast_math;  
```  
  
## <a name="members"></a>Member  
  
### <a name="functions"></a>Funktionen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[cos](concurrency-fast-math-namespace-functions.md#cos)|Berechnet den Arkuskosinus des Arguments|  
|[cosf](concurrency-fast-math-namespace-functions.md#cosf)|Berechnet den Arkuskosinus des Arguments|  
|[asin](concurrency-fast-math-namespace-functions.md#asin)|Berechnet den Arkussinus des Arguments|  
|[asinf](concurrency-fast-math-namespace-functions.md#asinf)|Berechnet den Arkussinus des Arguments|  
|[atan](concurrency-fast-math-namespace-functions.md#atan)|Berechnet den Arkustangens des Arguments|  
|[atan2](concurrency-fast-math-namespace-functions.md#atan2)|Berechnet den Arkustangens von _Y/_X|  
|[atan2f](concurrency-fast-math-namespace-functions.md#atan2f)|Berechnet den Arkustangens von _Y/_X|  
|[atanf](concurrency-fast-math-namespace-functions.md#atanf)|Berechnet den Arkustangens des Arguments|  
|[ceil](concurrency-fast-math-namespace-functions.md#ceil)|Berechnet den Höchstwert des Arguments|  
|[ceilf](concurrency-fast-math-namespace-functions.md#ceilf)|Berechnet den Höchstwert des Arguments|  
|[cos](concurrency-fast-math-namespace-functions.md#cos)|Berechnet den Kosinus des Arguments|  
|[cosf](concurrency-fast-math-namespace-functions.md#cosf)|Berechnet den Kosinus des Arguments|  
|[cosh](concurrency-fast-math-namespace-functions.md#cosh)|Berechnet den Hyperbelkosinuswert des Arguments|  
|[coshf](concurrency-fast-math-namespace-functions.md#coshf)|Berechnet den Hyperbelkosinuswert des Arguments|  
|[exp](concurrency-fast-math-namespace-functions.md#exp)|Berechnet die Basis-E, die vom Argument exponential ist|  
|[exp2](concurrency-fast-math-namespace-functions.md#exp2)|Berechnet die Basis-2, die vom Argument exponential ist|  
|[exp2f](concurrency-fast-math-namespace-functions.md#exp2f)|Berechnet die Basis-2, die vom Argument exponential ist|  
|[expf](concurrency-fast-math-namespace-functions.md#expf)|Berechnet die Basis-E, die vom Argument exponential ist|  
|[fabs](concurrency-fast-math-namespace-functions.md#fabs)|Gibt den absoluten Wert des Arguments zurück.|  
|[fabsf](concurrency-fast-math-namespace-functions.md#fabsf)|Gibt den absoluten Wert des Arguments zurück.|  
|[floor](concurrency-fast-math-namespace-functions.md#floor)|Berechnet den Tiefstwert des Arguments|  
|[floorf](concurrency-fast-math-namespace-functions.md#floorf)|Berechnet den Tiefstwert des Arguments|  
|[fmax](concurrency-fast-math-namespace-functions.md#fmax)|Festlegung des höchsten numerischen Werts der Argumente|  
|[fmaxf](concurrency-fast-math-namespace-functions.md#fmaxf)|Festlegung des höchsten numerischen Werts der Argumente|  
|[fmin](concurrency-fast-math-namespace-functions.md#fmin)|Festlegung des niedrigsten numerischen Werts der Argumente|  
|[fminf](concurrency-fast-math-namespace-functions.md#fminf)|Festlegung des niedrigsten numerischen Werts der Argumente|  
|[fmod](concurrency-fast-math-namespace-functions.md#fmod)|Berechnet den Gleitkommarest von _X/_Y|  
|[fmodf](concurrency-fast-math-namespace-functions.md#fmodf)|Berechnet den Gleitkommarest von _X/_Y|  
|[frexp](concurrency-fast-math-namespace-functions.md#frexp)|Ruft die Mantisse und den Exponenten von _X ab|  
|[frexpf](concurrency-fast-math-namespace-functions.md#frexpf)|Ruft die Mantisse und den Exponenten von _X ab|  
|[isfinite](concurrency-fast-math-namespace-functions.md#isfinite)|Bestimmt, ob das Argument einen über begrenzten Wert verfügt|  
|[isinf](concurrency-fast-math-namespace-functions.md#isinf)|Bestimmt, ob das Argument unendlich ist|  
|[isnan](concurrency-fast-math-namespace-functions.md#isnan)|Bestimmt, ob das Argument ein NaN|  
|[ldexp](concurrency-fast-math-namespace-functions.md#ldexp)|Berechnet eine reelle Zahl aus der Mantisse und dem Exponent|  
|[ldexpf](concurrency-fast-math-namespace-functions.md#ldexpf)|Berechnet eine reelle Zahl aus der Mantisse und dem Exponent|  
|[log](concurrency-fast-math-namespace-functions.md#log)|Berechnet den Basis-E-Logarithmus des Arguments|  
|[log10](concurrency-fast-math-namespace-functions.md#log10)|Berechnet den Basis-10-Logarithmus des Arguments|  
|[log10f](concurrency-fast-math-namespace-functions.md#log10f)|Berechnet den Basis-10-Logarithmus des Arguments|  
|[log2](concurrency-fast-math-namespace-functions.md#log2)|Berechnet den Basis-2-Logarithmus des Arguments|  
|[log2f](concurrency-fast-math-namespace-functions.md#log2f)|Berechnet den Basis-2-Logarithmus des Arguments|  
|[logf](concurrency-fast-math-namespace-functions.md#logf)|Berechnet den Basis-E-Logarithmus des Arguments|  
|[modf](concurrency-fast-math-namespace-functions.md#modf)|Teilt _X in Nachkommastellen und ganze Zahlen auf.|  
|[modff](concurrency-fast-math-namespace-functions.md#modff)|Teilt _X in Nachkommastellen und ganze Zahlen auf.|  
|[pow](concurrency-fast-math-namespace-functions.md#pow)|Berechnet _X potenziert mit _Y|  
|[powf](concurrency-fast-math-namespace-functions.md#powf)|Berechnet _X potenziert mit _Y|  
|[round](concurrency-fast-math-namespace-functions.md#round)|Rundet _X auf die nächste ganze Zahl|  
|[roundf](concurrency-fast-math-namespace-functions.md#roundf)|Rundet _X auf die nächste ganze Zahl|  
|[rsqrt](concurrency-fast-math-namespace-functions.md#rsqrt)|Gibt den Kehrwert der Quadratwurzel des Arguments zurück|  
|[rsqrtf](concurrency-fast-math-namespace-functions.md#rsqrtf)|Gibt den Kehrwert der Quadratwurzel des Arguments zurück|  
|[signbit](concurrency-fast-math-namespace-functions.md#signbit)|Gibt das Vorzeichen des Arguments zurück|  
|[signbitf](concurrency-fast-math-namespace-functions.md#signbitf)|Gibt das Vorzeichen des Arguments zurück|  
|[sin](concurrency-fast-math-namespace-functions.md#sin)|Berechnet den Sinuswert des Arguments|  
|[sincos](concurrency-fast-math-namespace-functions.md#sincos)|Berechnet Sinus- und Kosinuswert von _X|  
|[sincosf](concurrency-fast-math-namespace-functions.md#sincosf)|Berechnet Sinus- und Kosinuswert von _X|  
|[sinf](concurrency-fast-math-namespace-functions.md#sinf)|Berechnet den Sinuswert des Arguments|  
|[sinh](concurrency-fast-math-namespace-functions.md#sinh)|Berechnet den Hyperbelsinuswert des Arguments|  
|[sinhf](concurrency-fast-math-namespace-functions.md#sinhf)|Berechnet den Hyperbelsinuswert des Arguments|  
|[sqrt](concurrency-fast-math-namespace-functions.md#sqrt)|Berechnet die Quadratwurzel des Arguments|  
|[sqrtf](concurrency-fast-math-namespace-functions.md#sqrtf)|Berechnet die Quadratwurzel des Arguments|  
|[tan](concurrency-fast-math-namespace-functions.md#tan)|Berechnet den Tangenswert des Arguments|  
|[tanf](concurrency-fast-math-namespace-functions.md#tanf)|Berechnet den Tangenswert des Arguments|  
|[tanh](concurrency-fast-math-namespace-functions.md#tanh)|Berechnet den Hyperbeltangenswert des Arguments|  
|[tanhf](concurrency-fast-math-namespace-functions.md#tanhf)|Berechnet den Hyperbeltangenswert des Arguments|  
|[trunc](concurrency-fast-math-namespace-functions.md#trunc)|Schneidet das Argument der ganzzahligen Komponente ab|  
|[truncf](concurrency-fast-math-namespace-functions.md#truncf)|Schneidet das Argument der ganzzahligen Komponente ab|  

## <a name="requirements"></a>Anforderungen  
 **Header:** amp_math.h  
  
 **Namespace:** Concurrency:: fast_math  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
