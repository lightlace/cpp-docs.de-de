---
title: subtract_with_carry_engine-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- random/std::subtract_with_carry_engine
- random/std::subtract_with_carry_engine::default_seed
- random/std::subtract_with_carry_engine::discard
- random/std::subtract_with_carry_engine::min
- random/std::subtract_with_carry_engine::max
- random/std::subtract_with_carry_engine::seed
dev_langs:
- C++
helpviewer_keywords:
- std::subtract_with_carry_engine [C++]
- std::subtract_with_carry_engine [C++], default_seed
- std::subtract_with_carry_engine [C++], discard
- std::subtract_with_carry_engine [C++], min
- std::subtract_with_carry_engine [C++], max
- std::subtract_with_carry_engine [C++], seed
ms.assetid: 94a055f2-a620-4a22-ac34-c156924bab31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bfb0c3c0544a9c58801f98567825e7e97e48b13c
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43687986"
---
# <a name="subtractwithcarryengine-class"></a>subtract_with_carry_engine-Klasse

Generiert eine zufällige Sequenz mithilfe des (verzögerten Fibonacci-)Algorithmus "subtract with carry".

## <a name="syntax"></a>Syntax

```cpp
template <class UIntType, size_t W, size_t S, size_t R>
class subtract_with_carry_engine;
```

### <a name="parameters"></a>Parameter

*UIntType*  
 Der unsigned integer-Ergebnistyp. Mögliche Typen finden Sie unter [\<random>](../standard-library/random.md).

*W*  
 **Wortgröße**. Größe jedes einzelnen Wortes der Zustandssequenz in Bits. **Vorbedingung**:`0 < W ≤ numeric_limits<UIntType>::digits`

*S*  
 **Kurze Verzögerung**. Anzahl der Ganzzahlwerte. **Vorbedingung**:`0 < S < R`

*R*  
 **Lange Verzögerung**. Bestimmt die Wiederholungsrate in der generierten Serie.

## <a name="members"></a>Mitglieder

||||
|-|-|-|
|`subtract_with_carry_engine::subtract_with_carry_engine`|`subtract_with_carry_engine::min`|`subtract_with_carry_engine::discard`|
|`subtract_with_carry_engine::operator()`|`subtract_with_carry_engine::max`|`subtract_with_carry_engine::seed`|
|`default_seed` ist eine als `19780503u` definierte Memberkonstante, die als Standardparameterwert für `subtract_with_carry_engine::seed` und den Einzelwertkonstruktor verwendet wird.|||

Weitere Informationen über Engine-Member finden Sie unter [\<random&gt;](../standard-library/random.md).

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse `substract_with_carry_engine` stellt eine Verbesserung gegenüber dem [linear_congruential_engine](../standard-library/linear-congruential-engine-class.md) dar. Keines dieser Module ist so schnell oder gibt so hochqualitative Ergebnisse zurück wie das [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md).

Die Engine produziert Werte eines benutzerspezifischen unsignierten Ganzzahltyps mithilfe der Wiederholungsrelation ( *period*) `x(i) = (x(i - R) - x(i - S) - cy(i - 1)) mod M`, wobei `cy(i)` den Wert `1` hat, wenn `x(i - S) - x(i - R) - cy(i - 1) < 0`, andernfalls `0`, und `M` den Wert `2`<sup>W</sup> hat. Der Zustand der Engine ist ein Carry Indikator plus *R* Werte. Diese Werte bestehen aus den letzten *R* Werte zurückgegeben, wenn `operator()` mindestens aufgerufen wurde *R* Timeout, andernfalls die `N` , die zurückgegeben wurden und die letzten `R - N` -Werte des Startwerts.

Das Vorlagenargument `UIntType` muss groß genug sein, um Werte bis zu `M - 1` zu enthalten.

Obwohl Sie direkt aus dieser Engine einen Generator konstruieren können, können Sie auch eine der voreingestellten Typdefinitionen verwenden:

`ranlux24_base`: Wird als Grundlage für `ranlux24` verwendet.
`typedef subtract_with_carry_engine<unsigned int, 24, 10, 24> ranlux24_base;`

`ranlux48_base`: Wird als Grundlage für `ranlux48` verwendet.
`typedef subtract_with_carry_engine<unsigned long long, 48, 5, 12> ranlux48_base;`

Ausführliche Informationen über den Algorithmus „subtract with carry engine“ erhalten Sie im Wikipedia-Artikel [Lagged Fibonacci generator (Kongruenzgenerator, in englischer Sprache)](https://en.wikipedia.org/wiki/Lagged_Fibonacci_generator).

## <a name="requirements"></a>Anforderungen

**Header:** \<random>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[\<random>](../standard-library/random.md)<br/>
