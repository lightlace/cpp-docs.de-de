---
title: '&lt;random&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
ms.openlocfilehash: 5b0cd634dad099669d803d4a2717fc9198151781
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954157"
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

*RealType* der ganzzahlige Gleitkommatyp. Mögliche Typen finden Sie unter [\<random>](../standard-library/random.md).

*Bits* den Zufallszahlengenerator an.

*Gen* den Zufallszahlengenerator an.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion ruft `operator()` von *Gen* wiederholt und verpackt die zurückgegebenen Werte in einen Gleitkommawert `x` des Typs *RealType* bis er die angegebene Anzahl erfasst hat von Mantissen-Bits in `x`. Die angegebene Zahl ist die kleinere von *Bits* (die muss ungleich NULL sein) und die volle Anzahl von Mantissen-Bits in *RealType*. Beim ersten Aufruf werden die Bits mit dem geringsten Wert ausgegeben. Die Funktion gibt `x` zurück.

## <a name="see-also"></a>Siehe auch

[\<random>](../standard-library/random.md)<br/>
