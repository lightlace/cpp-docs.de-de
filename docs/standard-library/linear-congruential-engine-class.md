---
title: "linear_congruential_engine-Klasse"
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
  - "std.tr1.linear_congruential_engine"
  - "random/std::tr1::linear_congruential_engine"
  - "linear_congruential_engine"
  - "std::tr1::linear_congruential_engine"
  - "tr1.linear_congruential_engine"
  - "tr1::linear_congruential_engine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "linear_congruential_engine-Klasse"
ms.assetid: 30e00ca6-1933-4701-9561-54f3e810a5a1
caps.latest.revision: 21
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# linear_congruential_engine-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Generiert eine zufällige Sequenz mithilfe des linearen Kongruenzalgorithmus.  
  
## Syntax  
  
```  
template<class UIntType, UIntType A, UIntType C, UIntType M>  
class linear_congruential_engine{  
public:  
    // types  
    typedef UIntType result_type;  
  
    // engine characteristics  
    static constexpr result_type multiplier = a;  
    static constexpr result_type increment = c;  
    static constexpr result_type modulus = m;  
    static constexpr result_type min() { return c == 0u ? 1u: 0u; }  
    static constexpr result_type max() { return m - 1u; }  
    static constexpr result_type default_seed = 1u;  
  
    // constructors and seeding functions  
    explicit linear_congruential_engine(result_type s = default_seed);  
    template<class Sseq> explicit linear_congruential_engine(Sseq& q);  
    void seed(result_type s = default_seed);  
    template<class Sseq> void seed(Sseq& q);  
  
    // generating functions  
    result_type operator()();  
    void discard(unsigned long long z);  
};  
```  
  
#### Parameter  
 `UIntType`  
 Der unsigned integer\-Ergebnistyp. Mögliche Typen finden Sie unter [\<random\>](../standard-library/random.md).  
  
 `A`  
 **Multiplikator**.**Vorbedingung**: Siehe Abschnitt "Hinweise".  
  
 `C`  
 **Inkrement**.**Vorbedingung**: Siehe Abschnitt "Hinweise".  
  
 `M`  
 **Modulooperator**.**Vorbedingung**: Siehe Abschnitt "Hinweise".  
  
## Mitglieder  
  
||||  
|-|-|-|  
|`linear_congruential_engine::linear_congruential_engine`|`linear_congruential_engine::min`|`linear_congruential_engine::discard`|  
|`linear_congruential_engine::operator()`|`linear_congruential_engine::max`|`linear_congruential_engine::seed`|  
  
 `default_seed` ist eine als `1u` definierte Memberkonstante, die als Standardparameterwert für `linear_congruential_engine::seed` und den Einzelwertkonstruktor verwendet wird.  
  
 Weitere Informationen über Modulmember finden Sie unter [\<random\>](../standard-library/random.md).  
  
## Hinweise  
 Die Vorlagenklasse `linear_congruential_engine` ist das einfachste Generatormodul, aber nicht das schnellste oder qualitativ höchstwertige. Eine Verbesserung gegenüber diesem Modul ist das [substract\_with\_carry\_engine](../standard-library/subtract-with-carry-engine-class.md). Keines dieser Module ist so schnell oder gibt so hochqualitative Ergebnisse zurück wie das [mersenne\_twister\_engine](../standard-library/mersenne-twister-engine-class.md).  
  
 Dieses Modul produziert Werte eines benutzerdefinierten Ganzzahltyps ohne Vorzeichen mithilfe der Wiederholungsrelation \(*period*\) `x(i) = (A * x(i-1) + C) mod M`.  
  
 Wenn `M` gleich Null ist, ist der für diese Modulooperation verwendete Wert `numeric_limits<result_type>::max() + 1`. Der Zustand des Moduls ist der letzte zurückgegebene Wert oder der Startwert, wenn `operator()` nicht aufgerufen wurde.  
  
 Wenn `M` nicht gleich Null ist, müssen die Werte der Vorlagenargumente `A` und `C` niedriger sein als `M`.  
  
 Obwohl Sie direkt aus diesem Modul einen Generator konstruieren können, können Sie auch eine der folgenden vordefinierten Typdefinitionen verwenden.  
  
 `minstd_rand0`: minimal standard Engine 1988 \(Lewis, Goodman und Miller 1969\).  
  
```  
typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;  
```  
  
 `minstd_rand`: Aktualisierte minimal standard Engine `minstd_rand0` \(Park, Miller und Stockmeyer 1993\).  
  
```  
typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;  
```  
  
 Ausführliche Informationen zu den Algorithmus lineare kongruenzmodul.erhalten, finden Sie im Wikipedia\-Artikel [Linear congruential Generator](http://go.microsoft.com/fwlink/?LinkId=402446).  
  
## Anforderungen  
 **Header:** \<random\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<random\>](../standard-library/random.md)