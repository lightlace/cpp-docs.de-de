---
title: "Concurrency::fast_math-Namespace | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_math/Concurrency::fast_math"
dev_langs: 
  - "C++"
ms.assetid: 54fed939-9902-49db-9f29-e98fd9821508
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Concurrency::fast_math-Namespace
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Funktionen im `fast_math`\-Namespace haben eine geringere Genauigkeit, unterstützen nur mit einfacher Genauigkeit \(`float`\) und rufen die systeminternen DirectX\-Funktionen auf.  Es gibt zwei Versionen jeder Funktion, beispielsweise `cos` und `cosf`.  Beide Versionen erstellen und geben einen `float`\-Wert zurück, aber jede ruft die gleiche systeminterne DirectX\-Funktion auf.  
  
## Syntax  
  
```  
namespace fast_math;  
```  
  
## Member  
  
### Funktionen  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[cos\-Funktion \(fast\_math\)](../Topic/cos%20Function%20%20\(fast_math\).md)|Berechnet den Arkuskosinus des Arguments|  
|[cosf\-Funktion \(fast\_math\)](../Topic/cosf%20Function%20\(fast_math\).md)|Berechnet den Arkuskosinus des Arguments|  
|[asin\-Funktion \(fast\_math\)](../Topic/asin%20Function%20\(fast_math\).md)|Berechnet den Arkussinus des Arguments|  
|[asinf\-Funktion \(fast\_math\)](../Topic/asinf%20Function%20\(fast_math\).md)|Berechnet den Arkussinus des Arguments|  
|[atan\-Funktion \(fast\_math\)](../Topic/atan%20Function%20\(fast_math\).md)|Berechnet den Arkustangens des Arguments|  
|[atan2\-Funktion \(fast\_math\)](../Topic/atan2%20Function%20\(fast_math\).md)|Berechnet den Arkustangens von \_Y\/\_X|  
|[atan2f\-Funktion \(fast\_math\)](../Topic/atan2f%20Function%20\(fast_math\).md)|Berechnet den Arkustangens von \_Y\/\_X|  
|[atanf\-Funktion \(fast\_math\)](../Topic/atanf%20Function%20\(fast_math\).md)|Berechnet den Arkustangens des Arguments|  
|[ceil\-Funktion \(fast\_math\)](../Topic/ceil%20Function%20\(fast_math\).md)|Berechnet die Höchstwert des Arguments|  
|[ceilf\-Funktion \(fast\_math\)](../Topic/ceilf%20Function%20\(fast_math\).md)|Berechnet die Höchstwert des Arguments|  
|[cos\-Funktion \(fast\_math\)](../Topic/cos%20Function%20%20\(fast_math\).md)|Berechnet den Kosinus des Arguments|  
|[cosf\-Funktion \(fast\_math\)](../Topic/cosf%20Function%20\(fast_math\).md)|Berechnet den Kosinus des Arguments|  
|[cosh\-Funktion \(fast\_math\)](../Topic/cosh%20Function%20\(fast_math\).md)|Berechnet den Hyperbelkosinuswert des Arguments|  
|[coshf\-Funktion \(fast\_math\)](../Topic/coshf%20Function%20\(fast_math\).md)|Berechnet den Hyperbelkosinuswert des Arguments|  
|[exp\-Funktion \(fast\_math\)](../Topic/exp%20Function%20\(fast_math\).md)|Berechnet die Basis\-E, die vom Argument exponential ist|  
|[exp2\-Funktion \(fast\_math\)](../Topic/exp2%20Function%20\(fast_math\).md)|Berechnet die Basis\-2, die vom Argument exponential ist|  
|[exp2f\-Funktion \(fast\_math\)](../Topic/exp2f%20Function%20\(fast_math\).md)|Berechnet die Basis\-2, die vom Argument exponential ist|  
|[expf\-Funktion \(fast\_math\)](../Topic/expf%20Function%20\(fast_math\).md)|Berechnet die Basis\-E, die vom Argument exponential ist|  
|[fabs\-Funktion \(fast\_math\)](../Topic/fabs%20Function%20\(fast_math\).md)|Gibt den absoluten Wert des Arguments zurück.|  
|[fabsf\-Funktion \(fast\_math\)](../Topic/fabsf%20Function%20\(fast_math\).md)|Gibt den absoluten Wert des Arguments zurück.|  
|[floor\-Funktion \(fast\_math\)](../Topic/floor%20Function%20\(fast_math\).md)|Berechnet den Tiefstwert des Arguments|  
|[floorf\-Funktion \(fast\_math\)](../Topic/floorf%20Function%20\(fast_math\).md)|Berechnet den Tiefstwert des Arguments|  
|[fmax\-Funktion \(fast\_math\)](../Topic/fmax%20Function%20\(fast_math\).md)|Festlegung des höchsten numerischen Werts der Argumente|  
|[fmaxf\-Funktion \(fast\_math\)](../Topic/fmaxf%20Function%20\(fast_math\).md)|Festlegung des höchsten numerischen Werts der Argumente|  
|[fmin\-Funktion \(fast\_math\)](../Topic/fmin%20Function%20\(fast_math\).md)|Festlegung des niedrigsten numerischen Werts der Argumente|  
|[fminf\-Funktion \(fast\_math\)](../Topic/fminf%20Function%20\(fast_math\).md)|Festlegung des niedrigsten numerischen Werts der Argumente|  
|[fmod\-Funktion \(fast\_math\)](../Topic/fmod%20Function%20\(fast_math\).md)|Berechnet den Gleitkommarest von \_X\/\_Y|  
|[fmodf\-Funktion \(fast\_math\)](../Topic/fmodf%20Function%20\(fast_math\).md)|Berechnet den Gleitkommarest von \_X\/\_Y|  
|[frexp\-Funktion \(fast\_math\)](../Topic/frexp%20Function%20\(fast_math\).md)|Ruft die Mantisse und den Exponenten von \_X ab|  
|[frexpf\-Funktion \(fast\_math\)](../Topic/frexpf%20Function%20\(fast_math\).md)|Ruft die Mantisse und den Exponenten von \_X ab|  
|[isfinite\-Funktion \(fast\_math\)](../Topic/isfinite%20Function%20\(fast_math\).md)|Bestimmt, ob das Argument einen über begrenzten Wert verfügt|  
|[isinf\-Funktion \(fast\_math\)](../Topic/isinf%20Function%20\(fast_math\).md)|Bestimmt, ob das Argument unendlich ist|  
|[isnan\-Funktion \(fast\_math\)](../Topic/isnan%20Function%20\(fast_math\).md)|Bestimmt, ob das Argument ein NaN|  
|[ldexp\-Funktion \(fast\_math\)](../Topic/ldexp%20Function%20\(fast_math\).md)|Berechnet eine reelle Zahl aus der Mantisse und dem Exponent|  
|[ldexpf\-Funktion \(fast\_math\)](../Topic/ldexpf%20Function%20\(fast_math\).md)|Berechnet eine reelle Zahl aus der Mantisse und dem Exponent|  
|[log\-Funktion \(fast\_math\)](../Topic/log%20Function%20\(fast_math\).md)|Berechnet den Basis\-E\-Logarithmus des Arguments|  
|[log10\-Funktion \(fast\_math\)](../Topic/log10%20Function%20\(fast_math\).md)|Berechnet den Basis\-10\-Logarithmus des Arguments|  
|[log10f\-Funktion \(fast\_math\)](../Topic/log10f%20Function%20\(fast_math\).md)|Berechnet den Basis\-10\-Logarithmus des Arguments|  
|[log2\-Funktion \(fast\_math\)](../Topic/log2%20Function%20\(fast_math\).md)|Berechnet den Basis\-2\-Logarithmus des Arguments|  
|[log2f\-Funktion \(fast\_math\)](../Topic/log2f%20Function%20\(fast_math\).md)|Berechnet den Basis\-2\-Logarithmus des Arguments|  
|[logf\-Funktion \(fast\_math\)](../Topic/logf%20Function%20\(fast_math\).md)|Berechnet den Basis\-E\-Logarithmus des Arguments|  
|[modf\-Funktion \(fast\_math\)](../Topic/modf%20Function%20\(fast_math\).md)|Teilt \_X in Nachkommastellen und ganze Zahlen auf.|  
|[modff\-Funktion \(fast\_math\)](../Topic/modff%20Function%20\(fast_math\).md)|Teilt \_X in Nachkommastellen und ganze Zahlen auf.|  
|[pow\-Funktion \(fast\_math\)](../Topic/pow%20Function%20\(fast_math\).md)|Berechnet \_X potenziert mit \_Y|  
|[powf\-Funktion \(fast\_math\)](../Topic/powf%20Function%20\(fast_math\).md)|Berechnet \_X potenziert mit \_Y|  
|[round\-Funktion \(fast\_math\)](../Topic/round%20Function%20\(fast_math\).md)|Rundet \_X auf die nächste ganze Zahl|  
|[roundf\-Funktion \(fast\_math\)](../Topic/roundf%20Function%20\(fast_math\).md)|Rundet \_X auf die nächste ganze Zahl|  
|[rsqrt\-Funktion \(fast\_math\)](../Topic/rsqrt%20Function%20\(fast_math\).md)|Gibt den Kehrwert der Quadratwurzel des Arguments zurück|  
|[rsqrtf\-Funktion \(fast\_math\)](../Topic/rsqrtf%20Function%20\(fast_math\).md)|Gibt den Kehrwert der Quadratwurzel des Arguments zurück|  
|[signbit\-Funktion \(fast\_math\)](../Topic/signbit%20Function%20\(fast_math\).md)|Gibt das Vorzeichen des Arguments zurück|  
|[signbitf\-Funktion \(fast\_math\)](../Topic/signbitf%20Function%20\(fast_math\).md)|Gibt das Vorzeichen des Arguments zurück|  
|[sin\-Funktion \(fast\_math\)](../Topic/sin%20Function%20\(fast_math\).md)|Berechnet den Sinuswert des Arguments|  
|[sincos\-Funktion \(fast\_math\)](../Topic/sincos%20Function%20\(fast_math\).md)|Berechnet Sinus\- und Kosinuswert von \_X|  
|[sincosf\-Funktion \(fast\_math\)](../Topic/sincosf%20Function%20\(fast_math\).md)|Berechnet Sinus\- und Kosinuswert von \_X|  
|[sinf\-Funktion \(fast\_math\)](../Topic/sinf%20Function%20\(fast_math\).md)|Berechnet den Sinuswert des Arguments|  
|[sinh\-Funktion \(fast\_math\)](../Topic/sinh%20Function%20\(fast_math\).md)|Berechnet den Hyperbelsinuswert des Arguments|  
|[sinhf\-Funktion \(fast\_math\)](../Topic/sinhf%20Function%20\(fast_math\).md)|Berechnet den Hyperbelsinuswert des Arguments|  
|[sqrt\-Funktion \(fast\_math\)](../Topic/sqrt%20Function%20\(fast_math\).md)|Berechnet die Quadratwurzel des Arguments|  
|[sqrtf\-Funktion \(fast\_math\)](../Topic/sqrtf%20Function%20\(fast_math\).md)|Berechnet die Quadratwurzel des Arguments|  
|[tan\-Funktion \(fast\_math\)](../Topic/tan%20Function%20\(fast_math\).md)|Berechnet den Tangenswert des Arguments|  
|[tanf\-Funktion \(fast\_math\)](../Topic/tanf%20Function%20\(fast_math\).md)|Berechnet den Tangenswert des Arguments|  
|[tanh\-Funktion \(fast\_math\)](../Topic/tanh%20Function%20\(fast_math\).md)|Berechnet den Hyperbeltangenswert des Arguments|  
|[tanhf\-Funktion \(fast\_math\)](../Topic/tanhf%20Function%20\(fast_math\).md)|Berechnet den Hyperbeltangenswert des Arguments|  
|[trunc\-Funktion \(fast\_math\)](../Topic/trunc%20Function%20\(fast_math\).md)|Schneidet das Argument der ganzzahligen Komponente ab|  
|[truncf\-Funktion \(fast\_math\)](../Topic/truncf%20Function%20\(fast_math\).md)|Schneidet das Argument der ganzzahligen Komponente ab|  
  
## Anforderungen  
 **Header:** amp\_math.h  
  
 **Namespace:** Concurrency::fast\_math  
  
## Siehe auch  
 [Concurrency\-Namespace \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)