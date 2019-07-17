---
title: '&lt;random&gt;-Funktionen'
ms.date: 11/04/2016
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
ms.openlocfilehash: 87b640d4f3aa3fbfa23ad5603d84102301e71ea4
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240386"
---
# <a name="ltrandomgt-functions"></a>&lt;random&gt;-Funktionen

## <a name="generate_canonical"></a> generate_canonical

Gibt einen Gleitkommawert aus einer zufälligen Sequenz zurück.

> [!NOTE]
> Der ISO C++-Standard verlangt, dass diese Funktion Werte im Bereich [`0`, `1`) zurückgibt. Visual Studio ist mit dieser Vorgabe noch nicht kompatibel. Verwenden Sie, um das Problem zu umgehen, zum Generieren von Werten in diesem Bereich [uniform_real_distribution](../standard-library/uniform-real-distribution-class.md).

```cpp
template <class RealType, size_t Bits, class Generator>
RealType generate_canonical(Generator& Gen);
```

### <a name="parameters"></a>Parameter

*RealType*\
Der ganzzahlige Gleitkommatyp. Mögliche Typen finden Sie unter [\<random>](../standard-library/random.md).

*Bits*\
Der Zufallszahlengenerator.

*Gen*\
Der Zufallszahlengenerator.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion ruft `operator()` von *Gen* wiederholt und verpackt die zurückgegebenen Werte in einen Gleitkommawert `x` des Typs *RealType* bis er die angegebene Anzahl erfasst hat von Mantissen-Bits in `x`. Die angegebene Zahl ist die kleinere von *Bits* (die muss ungleich NULL sein) und die volle Anzahl von Mantissen-Bits in *RealType*. Beim ersten Aufruf werden die Bits mit dem geringsten Wert ausgegeben. Die Funktion gibt `x` zurück.
