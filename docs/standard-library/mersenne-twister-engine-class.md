---
title: mersenne_twister_engine-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: random/std::mersenne_twister_engine
dev_langs: C++
helpviewer_keywords: mersenne_twister_engine class
ms.assetid: 7ee968fa-a1cc-450f-890f-7305de062685
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9db5fd19c480ac7dfa6f647a1e1bf4beec5609d1
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="mersennetwisterengine-class"></a>mersenne_twister_engine-Klasse
Generiert mithilfe des Mersenne-Twisteralgorithmus eine qualitativ hochwertige Zufallssequenz aus Ganzzahlen.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class UIntType,   
    size_t W, size_t N, size_t M, size_t R,  
    UIntType A, size_t U, UIntType D, size_t S,  
    UIntType B, size_t T, UIntType C, size_t L, UIntType F>  
class mersenne_twister_engine;  
```  
  
#### <a name="parameters"></a>Parameter  
 `UIntType`  
 Der unsigned integer-Ergebnistyp. Mögliche Typen finden Sie unter [\<random>](../standard-library/random.md).  
  
 `W`  
 **Wortgröße**. Größe jedes einzelnen Wortes der Zustandssequenz in Bits. **Vorbedingung**:`2u < W ≤ numeric_limits<UIntType>::digits`  
  
 `N`  
 **Zustandsgröße**. Die Anzahl von Elementen (Werten) in der Zustandssequenz.  
  
 `M`  
 **Verschiebungsgröße**. Die Anzahl von Elementen, die während jeder Verzerrung übersprungen werden sollen. **Vorbedingung**:`0 < M ≤ N`  
  
 `R`  
 **Maskenbits**. **Vorbedingung**:`R ≤ W`  
  
 `A`  
 **XOR-Maske**. **Vorbedingung**: `A ≤ (1u<<W) - 1u`  
  
 `U`, `S`, `T`, `L`  
 **Tempering der Verschiebungsparameter**. Werden während der Verschlüsselung (Tempering) als Verschiebungswerte verwendet. Vorbedingung: `U,S,T,L ≤ W`  
  
 `D`, `B`, `C`  
 **Tempering von Bitmaskenparametern**. Werden während der Verschlüsselung (Tempering) als Maskenwerte verwendet. Vorbedingung: `D,B,C ≤ (1u<<W) - 1u`  
  
 `F`  
 **Initialisierungsmultiplikator**. Wird verwendet, um die Initialisierung der Sequenz zu unterstützen. Vorbedingung: `F ≤ (1u<<W) - 1u`  
  
## <a name="members"></a>Mitglieder  
  
||||  
|-|-|-|  
|`mersenne_twister_engine::mersenne_twister_engine`|`mersenne_twister_engine::min`|`mersenne_twister_engine::discard`|  
|`mersenne_twister_engine::operator()`|`mersenne_twister_engine::max`|`mersenne_twister_engine::seed`|  
  
 `default_seed` ist eine als `5489u` definierte Memberkonstante, die als Standardparameterwert für `mersenne_twister_engine::seed` und den Einzelwertkonstruktor verwendet wird.  
  
 Weitere Informationen über Modulmember finden Sie unter [\<random>](../standard-library/random.md).  
  
## <a name="remarks"></a>Hinweise  
 Diese Vorlagenklasse beschreibt ein Zufallszahlenmodul und gibt Werte zum geschlossenen Intervall [`0`, `2`<sup>W</sup> - `1`] zurück. Sie enthält einen großen Integralwert mit `W * (N - 1) + R` Bits. Sie extrahiert aus diesem großen Wert `W` Bits auf einmal, und sobald alle Bits verwendet wurden, wird der große Wert verzerrt, indem die Bits verschoben und kombiniert werden, sodass ein neuen Satz von Bits entsteht aus dem extrahiert werden kann. Beim Zustand des Moduls handelt es sich um den letzten verwendeten `N` `W`-Bitwert, wenn `operator()` mindestens `N`-mal aufgerufen wurde. Andernfalls sind es die verwendeten `M` `W`-Bitwerte und die letzten `N - M`-Werte des Startwerts.  
  
 Der Generator verzerrt den großen Wert, den er enthält, indem er ein verzerrtes generalisiertes Feedback-Schieberegister verwendet, das durch die Verschiebungswerte `N` und `M`, einen Verzerrungswert `R` und eine bedingte XOR-Maske `A` definiert wird. Zusätzlich werden die Bits des Schieberegisters verschlüsselt (getempert). Dies geschieht entsprechend einer Bit-Scrambling-Matrix, die durch die Werte `U`, `D`, `S`, `B`, `T`, `C` und `L` definiert ist.  
  
 Das Vorlagenargument `UIntType`muss groß genug sein, um Werte bis zu `2`<sup>W</sup> - `1` zu enthalten. Die Werte der anderen Vorlagenargumente müssen die folgenden Anforderungen erfüllen: `2u < W, 0 < M, M ≤ N, R ≤ W, U ≤ W, S ≤ W, T ≤ W, L ≤ W, W ≤ numeric_limits<UIntType>::digits, A ≤ (1u<<W) - 1u, B ≤ (1u<<W) - 1u, C ≤ (1u<<W) - 1u, D ≤ (1u<<W) - 1u, and F ≤ (1u<<W) - 1u`.  
  
 Obwohl Sie direkt aus diesem Modul einen Generator konstruieren können, wird empfohlen, eine dieser voreingestellten Typedefs zu verwenden:  
  
 `mt19937`: 32-Bit-Mersenne-Twistermodul (Matsumoto und Nishimura, 1998).  
  
```  
typedef mersenne_twister_engine<unsigned int, 32, 624, 397,   
    31, 0x9908b0df,   
    11, 0xffffffff,   
    7, 0x9d2c5680,   
    15, 0xefc60000,   
    18, 1812433253> mt19937;  
```  
  
 `mt19937_64`: 64-Bit-Mersenne-Twistermodul (Matsumoto und Nishimura, 2000).  
  
```  
typedef mersenne_twister_engine<unsigned long long, 64, 312, 156,   
    31, 0xb5026f5aa96619e9ULL,   
    29, 0x5555555555555555ULL,   
    17, 0x71d67fffeda60000ULL,   
    37, 0xfff7eee000000000ULL,   
    43, 6364136223846793005ULL> mt19937_64;  
```  
  
 Ausführliche Informationen über den Mersenne-Twisteralgorithmus erhalten Sie im Wikipedia-Artikel [Mersenne twister (Mersenne-Twister)](http://go.microsoft.com/fwlink/p/?linkid=402356).  
  
## <a name="example"></a>Beispiel  
 Ein Codebeispiel finden Sie unter [\<random>](../standard-library/random.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<random>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [\<random>](../standard-library/random.md)

