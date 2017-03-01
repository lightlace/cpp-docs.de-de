---
title: 'Concurrency:: precise_math-Namespace | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_math/Concurrency::precise_math
dev_langs:
- C++
ms.assetid: ba653308-dc28-4384-b2fd-6cd718a72f91
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b64bd3e3702701ae2685d6688d88988dd91dc5d0
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencyprecisemath-namespace"></a>Concurrency::precise_math-Namespace
Funktionen im `precise_math`-Namespace sind C99-kompatibel. Sowohl einfache Genauigkeit, und doppelte Genauigkeit Versionen jeder Funktion enthalten sind. Beispielsweise `acos` ist die Version mit doppelter Genauigkeit und `acosf` ist die Version mit einfacher Genauigkeit. Diese Funktionen, einschließlich der Funktionen mit einfacher Genauigkeit erfordern erweiterte Unterstützung mit doppelter Genauigkeit auf der Zugriffstaste. Sie können die [Accelerator:: supports_double_precision-Datenmember](accelerator-class.md#supports_double_precision) bestimmt, ob Sie diese Funktionen auf eine bestimmte Zugriffstaste ausführen können. 

  
## <a name="syntax"></a>Syntax  
  
```cpp  
namespace precise_math;  
```  
  
#### <a name="parameters"></a>Parameter  
  
## <a name="members"></a>Mitglieder  
  
### <a name="functions"></a>Funktionen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ACOS-Funktion](concurrency-precise-math-namespace-functions.md#acos)|Überladen. Berechnet den Arkuskosinus des Arguments|  
|[Acosf-Funktion](concurrency-precise-math-namespace-functions.md#acosf)|Berechnet den Arkuskosinus des Arguments|  
|[Acosh-Funktion](concurrency-precise-math-namespace-functions.md#acosh)|Überladen. Berechnet den umgekehrten hyperbolischen Kosinus des Arguments|  
|[Acoshf-Funktion](concurrency-precise-math-namespace-functions.md#acoshf)|Berechnet den umgekehrten hyperbolischen Kosinus des Arguments|  
|[ASIN-Funktion](concurrency-precise-math-namespace-functions.md#asin)|Überladen. Berechnet den Arkussinus des Arguments|  
|[Asinf-Funktion](concurrency-precise-math-namespace-functions.md#asinf)|Berechnet den Arkussinus des Arguments|  
|[Asinh-Funktion](concurrency-precise-math-namespace-functions.md#asinh)|Überladen. Berechnet den umgekehrten hyperbolischen Sinus des Arguments|  
|[Asinhf-Funktion](concurrency-precise-math-namespace-functions.md#asinhf)|Berechnet den umgekehrten hyperbolischen Sinus des Arguments|  
|[ATAN-Funktion](concurrency-precise-math-namespace-functions.md#atan)|Überladen. Berechnet den Arkustangens des Arguments|  
|[atan2-Funktion](concurrency-precise-math-namespace-functions.md#atan2)|Überladen. Berechnet den Arkustangens von _Y/_X|  
|[atan2f-Funktion](concurrency-precise-math-namespace-functions.md#atan2f)|Berechnet den Arkustangens von _Y/_X|  
|[Atanf-Funktion](concurrency-precise-math-namespace-functions.md#atanf)|Berechnet den Arkustangens des Arguments|  
|[Atanh-Funktion](concurrency-precise-math-namespace-functions.md#atanh)|Überladen. Berechnet den umgekehrten hyperbolischen Tangens des Arguments|  
|[Atanhf-Funktion](concurrency-precise-math-namespace-functions.md#atanhf)|Berechnet den umgekehrten hyperbolischen Tangens des Arguments|  
|[Cbrt-Funktion](concurrency-precise-math-namespace-functions.md#cbrt)|Überladen. Berechnet die Kubikwurzel real des Arguments|  
|[Cbrtf-Funktion](concurrency-precise-math-namespace-functions.md#cbrtf)|Berechnet die Kubikwurzel real des Arguments|  
|[ceil-Funktion](concurrency-precise-math-namespace-functions.md#ceil)|Überladen. Berechnet den Höchstwert des Arguments|  
|[Ceilf-Funktion](concurrency-precise-math-namespace-functions.md#ceilf)|Berechnet den Höchstwert des Arguments|  
|[Copysign-Funktion](concurrency-precise-math-namespace-functions.md#copysign)|Überladen. Produziert einen Wert mit der Größe von _X und das Zeichen _y|  
|[Copysignf-Funktion](concurrency-precise-math-namespace-functions.md#copysignf)|Produziert einen Wert mit der Größe von _X und das Zeichen _y|  
|[cos Funktion](concurrency-precise-math-namespace-functions.md#cos)|Überladen. Berechnet den Kosinus des Arguments|  
|[Cosf-Funktion](concurrency-precise-math-namespace-functions.md#cosf)|Berechnet den Kosinus des Arguments|  
|[cosh-Funktion](concurrency-precise-math-namespace-functions.md#cosh)|Überladen. Berechnet den Hyperbelkosinuswert des Arguments|  
|[Coshf-Funktion](concurrency-precise-math-namespace-functions.md#coshf)|Berechnet den Hyperbelkosinuswert des Arguments|  
|[Cospi-Funktion](concurrency-precise-math-namespace-functions.md#cospi)|Überladen. Berechnet den Kosinuswert von Pi * _X|  
|[Cospif-Funktion](concurrency-precise-math-namespace-functions.md#cospif)|Berechnet den Kosinuswert von Pi * _X|  
|[Erf-Funktion](concurrency-precise-math-namespace-functions.md#erf)|Überladen. Berechnet die Fehlerfunktion von _X|  
|[ErfC-Funktion](concurrency-precise-math-namespace-functions.md#erfc)|Überladen. Berechnet die komplementäre Fehlerfunktion von _X|  
|[Erfcf-Funktion](concurrency-precise-math-namespace-functions.md#erfcf)|Berechnet die komplementäre Fehlerfunktion von _X|  
|[Erfcinv-Funktion](concurrency-precise-math-namespace-functions.md#erfcinv)|Überladen. Berechnet die inverse komplementäre Fehlerfunktion von _X|  
|[Erfcinvf-Funktion](concurrency-precise-math-namespace-functions.md#erfcinvf)|Berechnet die inverse komplementäre Fehlerfunktion von _X|  
|[Erff-Funktion](concurrency-precise-math-namespace-functions.md#erff)|Berechnet die Fehlerfunktion von _X|  
|[Erfinv-Funktion](concurrency-precise-math-namespace-functions.md#erfinv)|Überladen. Berechnet die inverse Error-Funktion von _X|  
|[Erfinvf-Funktion](concurrency-precise-math-namespace-functions.md#erfinvf)|Berechnet die inverse Error-Funktion von _X|  
|[EXP-Funktion](concurrency-precise-math-namespace-functions.md#exp)|Überladen. Berechnet die Basis-E, die vom Argument exponential ist|  
|[exp10-Funktion](concurrency-precise-math-namespace-functions.md#exp10)|Überladen. Berechnet die Basis&10; vom Argument exponential|  
|[exp10f-Funktion](concurrency-precise-math-namespace-functions.md#exp10f)|Berechnet die Basis&10; vom Argument exponential|  
|[EXP2-Funktion](concurrency-precise-math-namespace-functions.md#exp2)|Überladen. Berechnet die Basis-2, die vom Argument exponential ist|  
|[exp2f-Funktion](concurrency-precise-math-namespace-functions.md#exp2f)|Berechnet die Basis-2, die vom Argument exponential ist|  
|[Expf-Funktion](concurrency-precise-math-namespace-functions.md#expf)|Berechnet die Basis-E, die vom Argument exponential ist|  
|[expm1-Funktion](concurrency-precise-math-namespace-functions.md#expm1)|Überladen. Berechnet die Basis-E, die vom Argument exponential ist, minus 1|  
|[expm1f-Funktion](concurrency-precise-math-namespace-functions.md#expm1f)|Berechnet die Basis-E, die vom Argument exponential ist, minus 1|  
|[Fabs-Funktion](concurrency-precise-math-namespace-functions.md#fabs)|Überladen. Gibt den absoluten Wert des Arguments zurück.|  
|[Fabsf-Funktion](concurrency-precise-math-namespace-functions.md#fabsf)|Gibt den absoluten Wert des Arguments zurück.|  
|[Fdim-Funktion](concurrency-precise-math-namespace-functions.md#fdim)|Überladen. Bestimmt den positiven Unterschied zwischen den Argumenten|  
|[Fdimf-Funktion](concurrency-precise-math-namespace-functions.md#fdimf)|Bestimmt den positiven Unterschied zwischen den Argumenten|  
|[Floor-Funktion](concurrency-precise-math-namespace-functions.md#floor)|Überladen. Berechnet den Tiefstwert des Arguments|  
|[Floorf-Funktion](concurrency-precise-math-namespace-functions.md#floorf)|Berechnet den Tiefstwert des Arguments|  
|[FMA-Funktion](concurrency-precise-math-namespace-functions.md#fma)|Überladen. Berechnen (_X * _Y) + _Z, als ternärer Vorgang gerundet|  
|[Fmaf-Funktion](concurrency-precise-math-namespace-functions.md#fmaf)|Berechnen (_X * _Y) + _Z, als ternärer Vorgang gerundet|  
|[Fmax-Funktion](concurrency-precise-math-namespace-functions.md#fmax)|Überladen. Festlegung des höchsten numerischen Werts der Argumente|  
|[Fmaxf-Funktion](concurrency-precise-math-namespace-functions.md#fmaxf)|Festlegung des höchsten numerischen Werts der Argumente|  
|[Fmin-Funktion](concurrency-precise-math-namespace-functions.md#fmin)|Überladen. Festlegung des niedrigsten numerischen Werts der Argumente|  
|[Fminf-Funktion](concurrency-precise-math-namespace-functions.md#fminf)|Festlegung des niedrigsten numerischen Werts der Argumente|  
|[Fmod-Funktion (C++-AMP)](concurrency-precise-math-namespace-functions.md#fmod)|Überladen. Berechnet den Gleitkommarest von _X/_Y|  
|[Fmodf-Funktion](concurrency-precise-math-namespace-functions.md#fmodf)|Berechnet den Gleitkommarest von _X/_Y|  
|[Fpclassify-Funktion](concurrency-precise-math-namespace-functions.md#fpclassify)|Überladen. Den Argumentwert klassifiziert, wie NaN, unendlich, Normal, subnormal,&0; (null)|  
|[Frexp-Funktion](concurrency-precise-math-namespace-functions.md#frexp)|Überladen. Ruft die Mantisse und den Exponenten von _X ab|  
|[Frexpf-Funktion](concurrency-precise-math-namespace-functions.md#frexpf)|Ruft die Mantisse und den Exponenten von _X ab|  
|[Hypot-Funktion](concurrency-precise-math-namespace-functions.md#hypot)|Überladen. Berechnet die Quadratwurzel der Summe der Quadrate von _X und _Y|  
|[Hypotf-Funktion](concurrency-precise-math-namespace-functions.md#hypotf)|Berechnet die Quadratwurzel der Summe der Quadrate von _X und _Y|  
|[Ilogb-Funktion](concurrency-precise-math-namespace-functions.md#ilogb)|Überladen. Extrahieren Sie den Exponenten von _X als Wert mit Vorzeichen int|  
|[Ilogbf-Funktion](concurrency-precise-math-namespace-functions.md#ilogbf)|Extrahieren Sie den Exponenten von _X als Wert mit Vorzeichen int|  
|[IsFinite-Funktion](concurrency-precise-math-namespace-functions.md#isfinite)|Überladen. Bestimmt, ob das Argument einen über begrenzten Wert verfügt|  
|[Isinf-Funktion](concurrency-precise-math-namespace-functions.md#isinf)|Überladen. Bestimmt, ob das Argument unendlich ist|  
|[IsNaN-Funktion](concurrency-precise-math-namespace-functions.md#isnan)|Überladen. Bestimmt, ob das Argument ein NaN|  
|[Isnormal-Funktion](concurrency-precise-math-namespace-functions.md#isnormal)|Überladen. Bestimmt, ob das Argument ein normaler|  
|[Ldexp-Funktion](concurrency-precise-math-namespace-functions.md#ldexp)|Überladen. Berechnet eine reelle Zahl aus der Mantisse und dem Exponent|  
|[Ldexpf-Funktion](concurrency-precise-math-namespace-functions.md#ldexpf)|Berechnet eine reelle Zahl aus der Mantisse und dem Exponent|  
|[Lgamma-Funktion](concurrency-precise-math-namespace-functions.md#lgamma)|Überladen. Berechnet den natürlichen Logarithmus der Absolute Wert des Gamma des Arguments|  
|[Lgammaf-Funktion](concurrency-precise-math-namespace-functions.md#lgammaf)|Berechnet den natürlichen Logarithmus der Absolute Wert des Gamma des Arguments|  
|[log-Funktion](concurrency-precise-math-namespace-functions.md#log)|Überladen. Berechnet den Basis-E-Logarithmus des Arguments|  
|[LOG10-Funktion](concurrency-precise-math-namespace-functions.md#log10)|Überladen. Berechnet den Basis-10-Logarithmus des Arguments|  
|[log10f-Funktion](concurrency-precise-math-namespace-functions.md#log10f)|Berechnet den Basis-10-Logarithmus des Arguments|  
|[log1p-Funktion](concurrency-precise-math-namespace-functions.md#log1p)|Überladen. Berechnet den Basis-e-Logarithmus des 1 plus das argument|  
|[log1pf-Funktion](concurrency-precise-math-namespace-functions.md#log1pf)|Berechnet den Basis-e-Logarithmus des 1 plus das argument|  
|[log2-Funktion](concurrency-precise-math-namespace-functions.md#log2)|Überladen. Berechnet den Basis-2-Logarithmus des Arguments|  
|[log2f-Funktion](concurrency-precise-math-namespace-functions.md#log2f)|Berechnet den Basis-2-Logarithmus des Arguments|  
|[Logb-Funktion](concurrency-precise-math-namespace-functions.md#logb)|Überladen. Extrahiert den Exponenten von _x ab, als eine Ganzzahl mit Vorzeichen im Gleitkommaformat|  
|[Logbf-Funktion](concurrency-precise-math-namespace-functions.md#logbf)|Extrahiert den Exponenten von _x ab, als eine Ganzzahl mit Vorzeichen im Gleitkommaformat|  
|[Logf-Funktion](concurrency-precise-math-namespace-functions.md#logf)|Berechnet den Basis-E-Logarithmus des Arguments|  
|[Modf-Funktion](concurrency-precise-math-namespace-functions.md#modf)|Überladen. Teilt _X in Nachkommastellen und ganze Zahlen auf.|  
|[Modff-Funktion](concurrency-precise-math-namespace-functions.md#modff)|Teilt _X in Nachkommastellen und ganze Zahlen auf.|  
|[NaN-Funktion](concurrency-precise-math-namespace-functions.md#nan)|Gibt ein stilles NaN zurück|  
|[Nanf-Funktion](concurrency-precise-math-namespace-functions.md#nanf)|Gibt ein stilles NaN zurück|  
|[Nearbyint-Funktion](concurrency-precise-math-namespace-functions.md#nearbyint)|Überladen. Rundet das Argument in einen ganzzahligen Wert im Gleitkommaformat mit dem aktuellen Rundung.|  
|[Nearbyintf-Funktion](concurrency-precise-math-namespace-functions.md#nearbyintf)|Rundet das Argument in einen ganzzahligen Wert im Gleitkommaformat mit dem aktuellen Rundung.|  
|[Nextafter-Funktion](concurrency-precise-math-namespace-functions.md#nextafter)|Überladen. Bestimmen Sie den nächsten darstellbaren Wert, im Typ der Funktion, nach _X in Richtung _Y|  
|[Nextafterf-Funktion](concurrency-precise-math-namespace-functions.md#nextafterf)|Bestimmen Sie den nächsten darstellbaren Wert, im Typ der Funktion, nach _X in Richtung _Y|  
|[Phi-Funktion](concurrency-precise-math-namespace-functions.md#phi)|Überladen. Gibt die kumulative Verteilungsfunktion des Arguments zurück|  
|[Phif-Funktion](concurrency-precise-math-namespace-functions.md#phif)|Gibt die kumulative Verteilungsfunktion des Arguments zurück|  
|[Pow-Funktion](concurrency-precise-math-namespace-functions.md#pow)|Überladen. Berechnet _X potenziert mit _Y|  
|[Powf-Funktion](concurrency-precise-math-namespace-functions.md#powf)|Berechnet _X potenziert mit _Y|  
|[probit-Funktion](concurrency-precise-math-namespace-functions.md#probit)|Überladen. Gibt die inverse kumulative Verteilungsfunktion des Arguments zurück|  
|[Probitf-Funktion](concurrency-precise-math-namespace-functions.md#probitf)|Gibt die inverse kumulative Verteilungsfunktion des Arguments zurück|  
|[Rcbrt-Funktion](concurrency-precise-math-namespace-functions.md#rcbrt)|Überladen. Gibt den Kehrwert der die Kubikwurzel des Arguments zurück|  
|[Rcbrtf-Funktion](concurrency-precise-math-namespace-functions.md#rcbrtf)|Gibt den Kehrwert der die Kubikwurzel des Arguments zurück|  
|[Restfunktion](concurrency-precise-math-namespace-functions.md#remainder)|Überladen. Berechnet den Rest: _X REM _Y|  
|[Remainderf-Funktion](concurrency-precise-math-namespace-functions.md#remainderf)|Berechnet den Rest: _X REM _Y|  
|[Remquo-Funktion](concurrency-precise-math-namespace-functions.md#remquo)|Überladen. Berechnet den gleichen Rest als _X REM _Y. Auch die unteren 23 Bits von den ganzzahligen Quotienten _X/_Y berechnet, und gibt dieser Wert die gleichen Vorzeichen wie _X/_Y. Dieser Wert mit Vorzeichen in die ganze Zahl, die auf den _Quo gespeichert.|  
|[Remquof-Funktion](concurrency-precise-math-namespace-functions.md#remquof)|Berechnet den gleichen Rest als _X REM _Y. Auch die unteren 23 Bits von den ganzzahligen Quotienten _X/_Y berechnet, und gibt dieser Wert die gleichen Vorzeichen wie _X/_Y. Dieser Wert mit Vorzeichen in die ganze Zahl, die auf den _Quo gespeichert.|  
|[Round-Funktion](concurrency-precise-math-namespace-functions.md#round)|Überladen. Rundet _X auf die nächste ganze Zahl|  
|[Roundf-Funktion](concurrency-precise-math-namespace-functions.md#roundf)|Rundet _X auf die nächste ganze Zahl|  
|[Rsqrt-Funktion](concurrency-precise-math-namespace-functions.md#rsqrt)|Überladen. Gibt den Kehrwert der Quadratwurzel des Arguments zurück|  
|[Rsqrtf-Funktion](concurrency-precise-math-namespace-functions.md#rsqrtf)|Gibt den Kehrwert der Quadratwurzel des Arguments zurück|  
|[Scalb-Funktion](concurrency-precise-math-namespace-functions.md#scalb)|Überladen. Multipliziert _X von FLT_RADIX auf die Power-_Y|  
|[Scalbf-Funktion](concurrency-precise-math-namespace-functions.md#scalbf)|Multipliziert _X von FLT_RADIX auf die Power-_Y|  
|[Scalbn-Funktion](concurrency-precise-math-namespace-functions.md#scalbn)|Überladen. Multipliziert _X von FLT_RADIX auf die Power-_Y|  
|[Scalbnf-Funktion](concurrency-precise-math-namespace-functions.md#scalbnf)|Multipliziert _X von FLT_RADIX auf die Power-_Y|  
|[Signbit-Funktion](concurrency-precise-math-namespace-functions.md#signbit)|Überladen. Bestimmt, ob die Vorzeichen von _X negativ ist.|  
|[Signbitf-Funktion](concurrency-precise-math-namespace-functions.md#signbitf)|Bestimmt, ob die Vorzeichen von _X negativ ist.|  
|[SIN-Funktion](concurrency-precise-math-namespace-functions.md#sin)|Überladen. Berechnet den Sinuswert des Arguments|  
|[Sincos-Funktion](concurrency-precise-math-namespace-functions.md#sincos)|Überladen. Berechnet Sinus- und Kosinuswert von _X|  
|[Sincosf-Funktion](concurrency-precise-math-namespace-functions.md#sincosf)|Berechnet Sinus- und Kosinuswert von _X|  
|[Sinf-Funktion](concurrency-precise-math-namespace-functions.md#sinf)|Berechnet den Sinuswert des Arguments|  
|[Sinh-Funktion](concurrency-precise-math-namespace-functions.md#sinh)|Überladen. Berechnet den Hyperbelsinuswert des Arguments|  
|[Sinhf-Funktion](concurrency-precise-math-namespace-functions.md#sinhf)|Berechnet den Hyperbelsinuswert des Arguments|  
|[Sinpi-Funktion](concurrency-precise-math-namespace-functions.md#sinpi)|Überladen. Berechnet den Sinuswert von Pi * _X|  
|[Sinpif-Funktion](concurrency-precise-math-namespace-functions.md#sinpif)|Berechnet den Sinuswert von Pi * _X|  
|[Sqrt-Funktion](concurrency-precise-math-namespace-functions.md#sqrt)|Überladen. Berechnet den Squre Stamm des Arguments|  
|[Sqrtf-Funktion](concurrency-precise-math-namespace-functions.md#sqrtf)|Berechnet den Squre Stamm des Arguments|  
|[Tan-Funktion](concurrency-precise-math-namespace-functions.md#tan)|Überladen. Berechnet den Tangenswert des Arguments|  
|[Tanf-Funktion](concurrency-precise-math-namespace-functions.md#tanf)|Berechnet den Tangenswert des Arguments|  
|[Tanh-Funktion](concurrency-precise-math-namespace-functions.md#tanh)|Überladen. Berechnet den Hyperbeltangenswert des Arguments|  
|[Tanhf-Funktion](concurrency-precise-math-namespace-functions.md#tanhf)|Berechnet den Hyperbeltangenswert des Arguments|  
|[Tanpi-Funktion](concurrency-precise-math-namespace-functions.md#tanpi)|Überladen. Berechnet den Tangenswert von Pi * _X|  
|[Tanpif-Funktion](concurrency-precise-math-namespace-functions.md#tanpif)|Berechnet den Tangenswert von Pi * _X|  
|[Tgamma-Funktion](concurrency-precise-math-namespace-functions.md#tgamma)|Überladen. Berechnet die Gammafunktion von _X|  
|[Tgammaf-Funktion](concurrency-precise-math-namespace-functions.md#tgammaf)|Berechnet die Gammafunktion von _X|  
|[TRUNC-Funktion](concurrency-precise-math-namespace-functions.md#trunc)|Überladen. Schneidet das Argument der ganzzahligen Komponente ab|  
|[Truncf-Funktion](concurrency-precise-math-namespace-functions.md#truncf)|Schneidet das Argument der ganzzahligen Komponente ab|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp_math.h  
  
 **Namespace:** Parallelität  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++-AMP)](concurrency-namespace-cpp-amp.md)

