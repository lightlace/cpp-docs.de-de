---
title: "subtract_with_carry_engine-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tr1.subtract_with_carry_engine"
  - "std::tr1::subtract_with_carry_engine"
  - "random/std::tr1::subtract_with_carry_engine"
  - "subtract_with_carry_engine"
  - "tr1::subtract_with_carry_engine"
  - "std.tr1.subtract_with_carry_engine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "subtract_with_carry_engine-Klasse"
ms.assetid: 94a055f2-a620-4a22-ac34-c156924bab31
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# subtract_with_carry_engine-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Generiert eine zufällige Sequenz mithilfe des \(verzögerten Fibonacci\-\)Algorithmus "subtract with carry".  
  
## Syntax  
  
```  
template<class UIntType, size_t W, size_t S, size_t R>  
class subtract_with_carry_engine;  
```  
  
#### Parameter  
 `UIntType`  
 Der unsigned integer\-Ergebnistyp. Mögliche Typen finden Sie unter [\<random\>](../standard-library/random.md).  
  
 `W`  
 **Wortgröße**. Größe jedes einzelnen Wortes der Zustandssequenz in Bits.**Vorbedingung**: `0 < W ≤ numeric_limits<UIntType>::digits`  
  
 `S`  
 **Kurze Verzögerung**. Anzahl der Ganzzahlwerte.**Vorbedingung**: `0 < S < R`  
  
 `R`  
 **Lange Verzögerung**. Bestimmt die Wiederholungsrate in der generierten Serie.  
  
## Mitglieder  
  
||||  
|-|-|-|  
|`subtract_with_carry_engine::subtract_with_carry_engine`|`subtract_with_carry_engine::min`|`subtract_with_carry_engine::discard`|  
|`subtract_with_carry_engine::operator()`|`subtract_with_carry_engine::max`|`subtract_with_carry_engine::seed`|  
|`default_seed` ist eine als `19780503u` definierte Memberkonstante, die als Standardparameterwert für `subtract_with_carry_engine::seed` und den Einzelwertkonstruktor verwendet wird.|||  
  
 Weitere Informationen über Modulmember finden Sie unter [\<random\>](../standard-library/random.md).  
  
## Hinweise  
 Die Vorlagenklasse `substract_with_carry_engine` stellt eine Verbesserung gegenüber dem [linear\_congruential\_engine](../standard-library/linear-congruential-engine-class.md) dar. Keines dieser Module ist so schnell oder gibt so hochqualitative Ergebnisse zurück wie das [mersenne\_twister\_engine](../standard-library/mersenne-twister-engine-class.md).  
  
 Das Modul produziert Werte eines benutzerspeziifischen unsignierten Ganzzahltyps mithilfe der Wiederholungsrelation \(*period*\) `x(i) = (x(i - R) - x(i - S) - cy(i - 1)) mod M`, wobei `cy(i)` den Wert `1` hat, wenn `x(i - S) - x(i - R) - cy(i - 1) < 0` ist, und andernfalls `0`, und `M` den Wert `2`<sup>W</sup> hat. Der Zustand des Moduls ist ein carry\-Indikator plus `R` Werten. Diese Werte bestehen aus den letzten `R` Werten, die zurückgegeben werden, wenn `operator()` mindestens `R` Mal aufgerufen wurde, andernfalls aus den `N` Werten, die zurückgegeben wurden, und den letzten `R - N` Werten des Startwerts.  
  
 Das Vorlagenargument `UIntType` muss groß genug sein, um Werte bis zu `M - 1` zu enthalten.  
  
 Obwohl Sie direkt aus diesem Modul einen Generator konstruieren können, können Sie auch eine der folgenden vordefinierten Typdefinitionen verwenden:  
  
 `ranlux24_base`: Wird verwendet, als Basis für `ranlux24`.  
`typedef subtract_with_carry_engine<unsigned int, 24, 10, 24> ranlux24_base;`  
  
 `ranlux48_base`: Wird verwendet, als Basis für `ranlux48`.  
`typedef subtract_with_carry_engine<unsigned long long, 48, 5, 12> ranlux48_base;`  
  
 Ausführliche Informationen zu den Subract mit Carry\-Engine\-Algorithmus, finden Sie im Wikipedia\-Artikel [Lagged Fibonacci Generator](http://go.microsoft.com/fwlink/?LinkId=402445).  
  
## Anforderungen  
 **Header:** \<random\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<random\>](../standard-library/random.md)