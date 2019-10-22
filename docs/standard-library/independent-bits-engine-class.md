---
title: independent_bits_engine-Klasse
ms.date: 11/04/2016
f1_keywords:
- random/std::independent_bits_engine
helpviewer_keywords:
- independent_bits_engine class
ms.assetid: 889e9a82-f457-49a7-9d2e-26e0fc3cd907
ms.openlocfilehash: 28c9301d270ef516a1acc59f6ab06f0e61a1c9c5
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687929"
---
# <a name="independent_bits_engine-class"></a>independent_bits_engine-Klasse

Generiert eine zufällige Zahlensequenz mit einer angegebenen Anzahl von Bits, indem Bits aus von der Basis-Engine zurückgegebenen Werten erneut verpackt werden.

## <a name="syntax"></a>Syntax

```cpp
template <class Engine, size_t W, class UIntType>
class independent_bits_engine;
```

### <a name="parameters"></a>Parameter

*Engine* -\
Der Typ der Basis-Engine.

*W* \
**Wortgröße**. Größe jeder generierten Zahl in Bits. **Vorbedingung**:`0 < W ≤ numeric_limits<UIntType>::digits`

*Uinttype* -\
Der unsigned integer-Ergebnistyp. Die möglichen Typen finden Sie unter [\<random>](../standard-library/random.md).

## <a name="members"></a>Member

||||
|-|-|-|
|`independent_bits_engine::independent_bits_engine`|`independent_bits_engine::base`|`independent_bits_engine::discard`|
|`independent_bits_engine::operator()`|`independent_bits_engine::base_type`|`independent_bits_engine::seed`|

Weitere Informationen über Engine-Member finden Sie unter [\<random&gt;](../standard-library/random.md).

## <a name="remarks"></a>Hinweise

Diese Klassen Vorlage beschreibt einen *Engine-Adapter* , der Werte erzeugt, indem Bits aus den Werten, die von der Basis-Engine zurückgegeben werden, wieder hergestellt werden, was zu *W*-Bit-Werten führt.

## <a name="requirements"></a>Anforderungen

**Header:** \<random>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[\<random>](../standard-library/random.md)
