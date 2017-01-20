---
title: "Concurrency::precise_math-Namespace"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "amp_math/Concurrency::precise_math"
dev_langs: 
  - "C++"
ms.assetid: ba653308-dc28-4384-b2fd-6cd718a72f91
caps.latest.revision: 6
caps.handback.revision: "2"
ms.author: "mblome"
manager: "ghogen"
---
# Concurrency::precise_math-Namespace
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Funktionen im `precise_math`\-Namespace sind C99\-kompatibel.  werden Versionen der einfachen Genauigkeit und mit doppelter Genauigkeit jeder Funktion enthalten.  Beispielsweise ist `acos` die Version mit doppelter Genauigkeit und `acosf` ist die Version mit einfacher Genauigkeit.  Diese Funktionen, einschließlich der Genauigkeitsfunktionen, benötigen erweiterte Unterstützung mit doppelter Genauigkeit auf der Zugriffstaste.  Verwenden Sie [accelerator::supports\_double\_precision\-Datenmember](../Topic/accelerator::supports_double_precision%20Data%20Member.md), um zu bestimmen, wenn Sie diese Funktionen auf einer bestimmten Tastenkombination ausführen können.  
  
## Syntax  
  
```vb  
namespace precise_math;  
```  
  
#### Parameter  
  
## Member  
  
### Funktionen  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[acos\-Funktion](../Topic/acos%20Function.md)|Überladen.  Berechnet den Arkuskosinus des Arguments|  
|[acosf\-Funktion](../Topic/acosf%20Function.md)|Berechnet den Arkuskosinus des Arguments|  
|[acosh\-Funktion](../Topic/acosh%20Function.md)|Überladen.  Berechnet den hyperbolischen Arkuskosinus des Arguments|  
|[acoshf\-Funktion](../Topic/acoshf%20Function.md)|Berechnet den hyperbolischen Arkuskosinus des Arguments|  
|[asin\-Funktion](../Topic/asin%20Function.md)|Überladen.  Berechnet den Arkussinus des Arguments|  
|[asinf\-Funktion](../Topic/asinf%20Function.md)|Berechnet den Arkussinus des Arguments|  
|[asinh\-Funktion](../Topic/asinh%20Function.md)|Überladen.  Berechnet den hyperbolischen Arkussinus des Arguments|  
|[asinhf\-Funktion](../Topic/asinhf%20Function.md)|Berechnet den hyperbolischen Arkussinus des Arguments|  
|[atan\-Funktion](../Topic/atan%20Function.md)|Überladen.  Berechnet den Arkustangens des Arguments|  
|[atan2\-Funktion](../Topic/atan2%20Function.md)|Überladen.  Berechnet den Arkustangens von \_Y\/\_X|  
|[atan2f\-Funktion](../Topic/atan2f%20Function.md)|Berechnet den Arkustangens von \_Y\/\_X|  
|[atanf\-Funktion](../Topic/atanf%20Function.md)|Berechnet den Arkustangens des Arguments|  
|[atanh\-Funktion](../Topic/atanh%20Function.md)|Überladen.  Berechnet den hyperbolischer Arkustangens des Arguments|  
|[atanhf\-Funktion](../Topic/atanhf%20Function.md)|Berechnet den hyperbolischer Arkustangens des Arguments|  
|[cbrt\-Funktion](../Topic/cbrt%20Function.md)|Überladen.  Berechnet die echte Kubikwurzel des Arguments|  
|[cbrtf\-Funktion](../Topic/cbrtf%20Function.md)|Berechnet die echte Kubikwurzel des Arguments|  
|[ceil\-Funktion](../Topic/ceil%20Function.md)|Überladen.  Berechnet die Höchstwert des Arguments|  
|[ceilf\-Funktion](../Topic/ceilf%20Function.md)|Berechnet die Höchstwert des Arguments|  
|[copysign\-Funktion](../Topic/copysign%20Function.md)|Überladen.  Erzeugt einen Wert mit der Größe \_X und das Zeichen von \_Y|  
|[copysignf\-Funktion](../Topic/copysignf%20Function.md)|Erzeugt einen Wert mit der Größe \_X und das Zeichen von \_Y|  
|[cos\-Funktion](../Topic/cos%20Function.md)|Überladen.  Berechnet den Kosinus des Arguments|  
|[cosf\-Funktion](../Topic/cosf%20Function.md)|Berechnet den Kosinus des Arguments|  
|[cosh\-Funktion](../Topic/cosh%20Function.md)|Überladen.  Berechnet den Hyperbelkosinuswert des Arguments|  
|[coshf\-Funktion](../Topic/coshf%20Function.md)|Berechnet den Hyperbelkosinuswert des Arguments|  
|[cospi\-Funktion](../Topic/cospi%20Function.md)|Überladen.  Berechnet den Kosinuswert von Pi \* \_X|  
|[cospif\-Funktion](../Topic/cospif%20Function.md)|Berechnet den Kosinuswert von Pi \* \_X|  
|[erf\-Funktion](../Topic/erf%20Function.md)|Überladen.  Berechnet die Fehlerfunktion von \_X|  
|[erfc\-Funktion](../Topic/erfc%20Function.md)|Überladen.  Berechnet die komplementäre Fehlerfunktion von \_X|  
|[erfcf\-Funktion](../Topic/erfcf%20Function.md)|Berechnet die komplementäre Fehlerfunktion von \_X|  
|[erfcinv\-Funktion](../Topic/erfcinv%20Function.md)|Überladen.  Berechnet die umgekehrte komplementäre Fehlerfunktion von \_X|  
|[erfcinvf\-Funktion](../Topic/erfcinvf%20Function.md)|Berechnet die umgekehrte komplementäre Fehlerfunktion von \_X|  
|[erff\-Funktion](../Topic/erff%20Function.md)|Berechnet die Fehlerfunktion von \_X|  
|[erfinv\-Funktion](../Topic/erfinv%20Function.md)|Überladen.  Berechnet die umgekehrte Fehlerfunktion von \_X|  
|[erfinvf\-Funktion](../Topic/erfinvf%20Function.md)|Berechnet die umgekehrte Fehlerfunktion von \_X|  
|[exp\-Funktion](../Topic/exp%20Function.md)|Überladen.  Berechnet die Basis\-E, die vom Argument exponential ist|  
|[exp10\-Funktion](../Topic/exp10%20Function.md)|Überladen.  Berechnet die Basis\-10, die vom Argument exponential ist|  
|[exp10f\-Funktion](../Topic/exp10f%20Function.md)|Berechnet die Basis\-10, die vom Argument exponential ist|  
|[exp2\-Funktion](../Topic/exp2%20Function.md)|Überladen.  Berechnet die Basis\-2, die vom Argument exponential ist|  
|[exp2f\-Funktion](../Topic/exp2f%20Function.md)|Berechnet die Basis\-2, die vom Argument exponential ist|  
|[expf\-Funktion](../Topic/expf%20Function.md)|Berechnet die Basis\-E, die vom Argument exponential ist|  
|[expm1\-Funktion](../Topic/expm1%20Function.md)|Überladen.  Berechnet die Basis\-E, die vom Argument, minus 1 Exponential ist|  
|[expm1f\-Funktion](../Topic/expm1f%20Function.md)|Berechnet die Basis\-E, die vom Argument, minus 1 Exponential ist|  
|[fabs\-Funktion](../Topic/fabs%20Function.md)|Überladen.  Gibt den absoluten Wert des Arguments zurück.|  
|[fabsf\-Funktion](../Topic/fabsf%20Function.md)|Gibt den absoluten Wert des Arguments zurück.|  
|[fdim\-Funktion](../Topic/fdim%20Function.md)|Überladen.  Bestimmt die positiven Unterschied zwischen den Argumenten|  
|[fdimf\-Funktion](../Topic/fdimf%20Function.md)|Bestimmt die positiven Unterschied zwischen den Argumenten|  
|[floor\-Funktion](../Topic/floor%20Function.md)|Überladen.  Berechnet den Tiefstwert des Arguments|  
|[floorf\-Funktion](../Topic/floorf%20Function.md)|Berechnet den Tiefstwert des Arguments|  
|[fma\-Funktion](../Topic/fma%20Function.md)|Überladen.  Berechnung \_X \(\* \_Y\) \+ \_Z, abgerundet als ein dreifacher Operation|  
|[fmaf\-Funktion](../Topic/fmaf%20Function.md)|Berechnung \_X \(\* \_Y\) \+ \_Z, abgerundet als ein dreifacher Operation|  
|[fmax\-Funktion](../Topic/fmax%20Function.md)|Überladen.  Festlegung des höchsten numerischen Werts der Argumente|  
|[fmaxf\-Funktion](../Topic/fmaxf%20Function.md)|Festlegung des höchsten numerischen Werts der Argumente|  
|[fmin\-Funktion](../Topic/fmin%20Function.md)|Überladen.  Festlegung des niedrigsten numerischen Werts der Argumente|  
|[fminf\-Funktion](../Topic/fminf%20Function.md)|Festlegung des niedrigsten numerischen Werts der Argumente|  
|[fmod\-Funktion \(C\+\+ AMP\)](../Topic/fmod%20Function%20\(C++%20AMP\).md)|Überladen.  Berechnet den Gleitkommarest von \_X\/\_Y|  
|[fmodf\-Funktion](../Topic/fmodf%20Function.md)|Berechnet den Gleitkommarest von \_X\/\_Y|  
|[fpclassify\-Funktion](../Topic/fpclassify%20Function.md)|Überladen.  Klassifiziert den Argumentwert als nan, unendlich, Normal, subnormal, gleich|  
|[frexp\-Funktion](../Topic/frexp%20Function.md)|Überladen.  Ruft die Mantisse und den Exponenten von \_X ab|  
|[frexpf\-Funktion](../Topic/frexpf%20Function.md)|Ruft die Mantisse und den Exponenten von \_X ab|  
|[hypot\-Funktion](../Topic/hypot%20Function.md)|Überladen.  Berechnet die Quadratwurzel der Summe der Quadrate von \_X und von \_Y|  
|[hypotf\-Funktion](../Topic/hypotf%20Function.md)|Berechnet die Quadratwurzel der Summe der Quadrate von \_X und von \_Y|  
|[ilogb\-Funktion](../Topic/ilogb%20Function.md)|Überladen.  Extrahiert den Exponenten \_X als der int\-Wert mit Vorzeichen|  
|[ilogbf\-Funktion](../Topic/ilogbf%20Function.md)|Extrahiert den Exponenten \_X als der int\-Wert mit Vorzeichen|  
|[isfinite\-Funktion](../Topic/isfinite%20Function.md)|Überladen.  Bestimmt, ob das Argument einen über begrenzten Wert verfügt|  
|[isinf\-Funktion](../Topic/isinf%20Function.md)|Überladen.  Bestimmt, ob das Argument unendlich ist|  
|[isnan\-Funktion](../Topic/isnan%20Function.md)|Überladen.  Bestimmt, ob das Argument ein NaN|  
|[isnormal\-Funktion](../Topic/isnormal%20Function.md)|Überladen.  Bestimmt, ob das Argument ein normaler Block ist|  
|[ldexp\-Funktion](../Topic/ldexp%20Function.md)|Überladen.  Berechnet eine reelle Zahl aus der Mantisse und dem Exponent|  
|[ldexpf\-Funktion](../Topic/ldexpf%20Function.md)|Berechnet eine reelle Zahl aus der Mantisse und dem Exponent|  
|[lgamma\-Funktion](../Topic/lgamma%20Function.md)|Überladen.  Berechnet den natürlichen Logarithmus des absoluten Wert des Gammas vom Argument|  
|[lgammaf\-Funktion](../Topic/lgammaf%20Function.md)|Berechnet den natürlichen Logarithmus des absoluten Wert des Gammas vom Argument|  
|[log\-Funktion](../Topic/log%20Function.md)|Überladen.  Berechnet den Basis\-E\-Logarithmus des Arguments|  
|[log10\-Funktion](../Topic/log10%20Function.md)|Überladen.  Berechnet den Basis\-10\-Logarithmus des Arguments|  
|[log10f\-Funktion](../Topic/log10f%20Function.md)|Berechnet den Basis\-10\-Logarithmus des Arguments|  
|[log1p\-Funktion](../Topic/log1p%20Function.md)|Überladen.  Berechnet den Basis\-Elogarithmus von 1 plus Argument|  
|[log1pf\-Funktion](../Topic/log1pf%20Function.md)|Berechnet den Basis\-Elogarithmus von 1 plus Argument|  
|[log2\-Funktion](../Topic/log2%20Function.md)|Überladen.  Berechnet den Basis\-2\-Logarithmus des Arguments|  
|[log2f\-Funktion](../Topic/log2f%20Function.md)|Berechnet den Basis\-2\-Logarithmus des Arguments|  
|[logb\-Funktion](../Topic/logb%20Function.md)|Überladen.  Extrahiert den Exponenten von \_X, als ganzzahliger Wert mit Vorzeichen im Gleitkommaformats|  
|[logbf\-Funktion](../Topic/logbf%20Function.md)|Extrahiert den Exponenten von \_X, als ganzzahliger Wert mit Vorzeichen im Gleitkommaformats|  
|[logf\-Funktion](../Topic/logf%20Function.md)|Berechnet den Basis\-E\-Logarithmus des Arguments|  
|[modf\-Funktion](../Topic/modf%20Function.md)|Überladen.  Teilt \_X in Nachkommastellen und ganze Zahlen auf.|  
|[modff\-Funktion](../Topic/modff%20Function.md)|Teilt \_X in Nachkommastellen und ganze Zahlen auf.|  
|[nan\-Funktion](../Topic/nan%20Function.md)|Gibt einen stillen nan zurück|  
|[nanf\-Funktion](../Topic/nanf%20Function.md)|Gibt einen stillen nan zurück|  
|[nearbyint\-Funktion](../Topic/nearbyint%20Function.md)|Überladen.  Rundet das Argument in einen Ganzzahlwert im Gleitkommaformat, mit der aktuellen rundenden Richtung.|  
|[nearbyintf\-Funktion](../Topic/nearbyintf%20Function.md)|Rundet das Argument in einen Ganzzahlwert im Gleitkommaformat, mit der aktuellen rundenden Richtung.|  
|[nextafter\-Funktion](../Topic/nextafter%20Function.md)|Überladen.  Bestimmen Sie den nächsten darstellbaren Wert, im Typ der Funktion, nach \_X in Richtung \_Y|  
|[nextafterf\-Funktion](../Topic/nextafterf%20Function.md)|Bestimmen Sie den nächsten darstellbaren Wert, im Typ der Funktion, nach \_X in Richtung \_Y|  
|[phi\-Funktion](../Topic/phi%20Function.md)|Überladen.  Gibt der kumulativen Verteilungsfunktion des Arguments zurück|  
|[phif\-Funktion](../Topic/phif%20Function.md)|Gibt der kumulativen Verteilungsfunktion des Arguments zurück|  
|[pow\-Funktion](../Topic/pow%20Function.md)|Überladen.  Berechnet \_X potenziert mit \_Y|  
|[powf\-Funktion](../Topic/powf%20Function.md)|Berechnet \_X potenziert mit \_Y|  
|[probit\-Funktion](../Topic/probit%20Function.md)|Überladen.  Gibt der umgekehrten kumulativen Verteilungsfunktion des Arguments zurück|  
|[probitf\-Funktion](../Topic/probitf%20Function.md)|Gibt der umgekehrten kumulativen Verteilungsfunktion des Arguments zurück|  
|[rcbrt\-Funktion](../Topic/rcbrt%20Function.md)|Überladen.  Gibt das gegenseitige der Kubikwurzel des Arguments zurück|  
|[rcbrtf\-Funktion](../Topic/rcbrtf%20Function.md)|Gibt das gegenseitige der Kubikwurzel des Arguments zurück|  
|[Restfunktion](../Topic/remainder%20Function.md)|Überladen.  Berechnet den Rest: \_X REM\- Y|  
|[remainderf\-Funktion](../Topic/remainderf%20Function.md)|Berechnet den Rest: \_X REM\- Y|  
|[remquo\-Funktion](../Topic/remquo%20Function.md)|Überladen.  Berechnet denselben Rest wie \_X REM\- Y.  Berechnet auch die unteren 23 Bits des ganzzahligen Quotienten \_X\/\_Y und gibt, die dasselbe Zeichen wie \_X\/\_Y bewerten.  Es speichert diesen Wert mit Vorzeichen in der ganzen Zahl, die von \_Quo gezeigt wird.|  
|[remquof\-Funktion](../Topic/remquof%20Function.md)|Berechnet denselben Rest wie \_X REM\- Y.  Berechnet auch die unteren 23 Bits des ganzzahligen Quotienten \_X\/\_Y und gibt, die dasselbe Zeichen wie \_X\/\_Y bewerten.  Es speichert diesen Wert mit Vorzeichen in der ganzen Zahl, die von \_Quo gezeigt wird.|  
|[round\-Funktion](../Topic/round%20Function.md)|Überladen.  Rundet \_X auf die nächste ganze Zahl|  
|[roundf\-Funktion](../Topic/roundf%20Function.md)|Rundet \_X auf die nächste ganze Zahl|  
|[rsqrt\-Funktion](../Topic/rsqrt%20Function.md)|Überladen.  Gibt den Kehrwert der Quadratwurzel des Arguments zurück|  
|[rsqrtf\-Funktion](../Topic/rsqrtf%20Function.md)|Gibt den Kehrwert der Quadratwurzel des Arguments zurück|  
|[scalb\-Funktion](../Topic/scalb%20Function.md)|Überladen.  Multipliziert \_X durch FLT\_RADIX Leistungsfähigkeit zum \_Y|  
|[scalbf\-Funktion](../Topic/scalbf%20Function.md)|Multipliziert \_X durch FLT\_RADIX Leistungsfähigkeit zum \_Y|  
|[scalbn\-Funktion](../Topic/scalbn%20Function.md)|Überladen.  Multipliziert \_X durch FLT\_RADIX Leistungsfähigkeit zum \_Y|  
|[scalbnf\-Funktion](../Topic/scalbnf%20Function.md)|Multipliziert \_X durch FLT\_RADIX Leistungsfähigkeit zum \_Y|  
|[signbit\-Funktion](../Topic/signbit%20Function.md)|Überladen.  Bestimmt, ob das Zeichen von \_X negativ ist|  
|[signbitf\-Funktion](../Topic/signbitf%20Function.md)|Bestimmt, ob das Zeichen von \_X negativ ist|  
|[sin\-Funktion](../Topic/sin%20Function.md)|Überladen.  Berechnet den Sinuswert des Arguments|  
|[sincos\-Funktion](../Topic/sincos%20Function.md)|Überladen.  Berechnet Sinus\- und Kosinuswert von \_X|  
|[sincosf\-Funktion](../Topic/sincosf%20Function.md)|Berechnet Sinus\- und Kosinuswert von \_X|  
|[sinf\-Funktion](../Topic/sinf%20Function.md)|Berechnet den Sinuswert des Arguments|  
|[sinh\-Funktion](../Topic/sinh%20Function.md)|Überladen.  Berechnet den Hyperbelsinuswert des Arguments|  
|[sinhf\-Funktion](../Topic/sinhf%20Function.md)|Berechnet den Hyperbelsinuswert des Arguments|  
|[sinpi\-Funktion](../Topic/sinpi%20Function.md)|Überladen.  Berechnet den Sinuswert von Pi \* \_X|  
|[sinpif\-Funktion](../Topic/sinpif%20Function.md)|Berechnet den Sinuswert von Pi \* \_X|  
|[sqrt\-Funktion](../Topic/sqrt%20Function.md)|Überladen.  Berechnet den squre Stamm des Arguments|  
|[sqrtf\-Funktion](../Topic/sqrtf%20Function.md)|Berechnet den squre Stamm des Arguments|  
|[tan\-Funktion](../Topic/tan%20Function.md)|Überladen.  Berechnet den Tangenswert des Arguments|  
|[tanf\-Funktion](../Topic/tanf%20Function.md)|Berechnet den Tangenswert des Arguments|  
|[tanh\-Funktion](../Topic/tanh%20Function.md)|Überladen.  Berechnet den Hyperbeltangenswert des Arguments|  
|[tanhf\-Funktion](../Topic/tanhf%20Function.md)|Berechnet den Hyperbeltangenswert des Arguments|  
|[tanpi\-Funktion](../Topic/tanpi%20Function.md)|Überladen.  Berechnet den Tangenswert von Pi \* \_X|  
|[tanpif\-Funktion](../Topic/tanpif%20Function.md)|Berechnet den Tangenswert von Pi \* \_X|  
|[tgamma\-Funktion](../Topic/tgamma%20Function.md)|Überladen.  Berechnet die Gamma\-Funktion von \_X|  
|[tgammaf\-Funktion](../Topic/tgammaf%20Function.md)|Berechnet die Gamma\-Funktion von \_X|  
|[trunc\-Funktion](../Topic/trunc%20Function.md)|Überladen.  Schneidet das Argument der ganzzahligen Komponente ab|  
|[truncf\-Funktion](../Topic/truncf%20Function.md)|Schneidet das Argument der ganzzahligen Komponente ab|  
  
## Anforderungen  
 **Header:** amp\_math.h  
  
 **Namespace:** Nebenläufigkeit  
  
## Siehe auch  
 [Concurrency\-Namespace \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)