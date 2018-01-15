---
title: linear_congruential_engine-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: random/std::linear_congruential_engine
dev_langs: C++
helpviewer_keywords: linear_congruential_engine class
ms.assetid: 30e00ca6-1933-4701-9561-54f3e810a5a1
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4624046c2810f3c23807aab8824d5a0ab62fdcc3
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="linearcongruentialengine-class"></a>linear_congruential_engine-Klasse
Generiert eine zufällige Sequenz mithilfe des linearen Kongruenzalgorithmus.  
  
## <a name="syntax"></a>Syntax  
```  
class linear_congruential_engine{  
   public:  // types  
   typedef UIntType result_type;  
   // engine characteristics  
   static constexpr result_type multiplier = a;  
   static constexpr result_type increment = c;  
   static constexpr result_type modulus = m;  
   static constexpr result_type min() { return c == 0u  1u: 0u; }  
   static constexpr result_type max() { return m - 1u; }  
   static constexpr result_type default_seed = 1u;  
   // constructors and seeding functions  
   explicit linear_congruential_engine(result_type s = default_seed);
   template <class Sseq>  
   explicit linear_congruential_engine(Sseq& q);
   void seed(result_type s = default_seed);
   template <class Sseq>  
   void seed(Sseq& q);
   // generating functions  
   result_type operator()();
   void discard(unsigned long long z);
   };  
```  
#### <a name="parameters"></a>Parameter  
 `UIntType`  
 Der unsigned integer-Ergebnistyp. Mögliche Typen finden Sie unter [\<random>](../standard-library/random.md).  
  
 `A`  
 **Multiplikator**. **Vorbedingung**: Siehe Abschnitt „Hinweise“.  
  
 `C`  
 **Inkrement**. **Vorbedingung**: Siehe Abschnitt „Hinweise“.  
  
 `M`  
 **Modulo**. **Vorbedingung**: Siehe Abschnitt „Hinweise“.  
  
## <a name="members"></a>Member  
  
||||  
|-|-|-|  
|`linear_congruential_engine::linear_congruential_engine`|`linear_congruential_engine::min`|`linear_congruential_engine::discard`|  
|`linear_congruential_engine::operator()`|`linear_congruential_engine::max`|`linear_congruential_engine::seed`|  
  
 `default_seed` ist eine als `1u` definierte Memberkonstante, die als Standardparameterwert für `linear_congruential_engine::seed` und den Einzelwertkonstruktor verwendet wird.  
  
 Weitere Informationen über Modulmember finden Sie unter [\<random>](../standard-library/random.md).  
  
## <a name="remarks"></a>Hinweise  
 Die Vorlagenklasse `linear_congruential_engine` ist das einfachste Generatormodul, aber nicht das schnellste oder qualitativ höchstwertige. [substract_with_carry_engine](../standard-library/subtract-with-carry-engine-class.md) ist gegenüber diesem Modul eine Verbesserung. Keines dieser Module ist so schnell oder gibt so hochqualitative Ergebnisse zurück wie [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md).  
  
 Dieses Modul produziert Werte eines benutzerdefinierten Ganzzahltyps ohne Vorzeichen mithilfe der Wiederholungsrelation (*period*) `x(i) = (A * x(i-1) + C) mod M`.  
  
 Wenn `M` gleich Null ist, ist der für diese Modulooperation verwendete Wert `numeric_limits<result_type>::max() + 1`. Der Zustand des Moduls ist der letzte zurückgegebene Wert oder der Startwert, wenn `operator()` nicht aufgerufen wurde.  
  
 Wenn `M` nicht gleich Null ist, müssen die Werte der Vorlagenargumente `A` und `C` niedriger sein als `M`.  
  
 Obwohl Sie direkt aus diesem Modul einen Generator konstruieren können, können Sie auch eine dieser voreingestellten Typdefinitionen verwenden.  
  
 `minstd_rand0`: 1988 minimal standard engine (Lewis, Goodman und Miller, 1969).  
  
```  
typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;  
```  
  
 `minstd_rand`: Updated minimal standard engine `minstd_rand0` (Park, Miller und Stockmeyer, 1993).  
  
```  
typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;  
```  
  
 Ausführliche Informationen über den Algorithmus für das lineare Kongruenzmodul, erhalten Sie im Wikipedia-Artikel [Linearer Kongruenzgenerator](http://go.microsoft.com/fwlink/p/?linkid=402446).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<random>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [\<random>](../standard-library/random.md)


