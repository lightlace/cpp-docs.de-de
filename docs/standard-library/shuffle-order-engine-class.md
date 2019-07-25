---
title: shuffle_order_engine-Klasse
ms.date: 11/04/2016
f1_keywords:
- random/std::shuffle_order_engine
- random/std::shuffle_order_engine::base
- random/std::shuffle_order_engine::discard
- random/std::shuffle_order_engine::operator()
- random/std::shuffle_order_engine::base_type
- random/std::shuffle_order_engine::seed
helpviewer_keywords:
- std::shuffle_order_engine [C++]
- std::shuffle_order_engine [C++], base
- std::shuffle_order_engine [C++], discard
- std::shuffle_order_engine [C++], base_type
- std::shuffle_order_engine [C++], seed
ms.assetid: 0bcd1fb0-44d7-4e59-bb1b-4a9b673a960d
ms.openlocfilehash: 972ba83afb5478cd89314817ba823b8d5657c9c8
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450413"
---
# <a name="shuffleorderengine-class"></a>shuffle_order_engine-Klasse

Generiert eine zufällige Sequenz durch Neupositionieren der Werte, die von ihrer Basis-Engine zurückgegeben werden.

## <a name="syntax"></a>Syntax

```cpp
template <class Engine, size_t K>
class shuffle_order_engine;
```

### <a name="parameters"></a>Parameter

*Ge*\
Der Typ der Basis-Engine.

*KM*\
**Tabellengröße**. Anzahl der Elemente im Puffer (Tabelle). **Vorbedingung**:`0 < K`

## <a name="members"></a>Member

||||
|-|-|-|
|`shuffle_order_engine::shuffle_order_engine`|`shuffle_order_engine::base`|`shuffle_order_engine::discard`|
|`shuffle_order_engine::operator()`|`shuffle_order_engine::base_type`|`shuffle_order_engine::seed`|

Weitere Informationen über Engine-Member finden Sie unter [\<random&gt;](../standard-library/random.md).

## <a name="remarks"></a>Hinweise

Diese Vorlagenklasse beschreibt einen *Engine-Adapter*, der Werte produziert, indem er die von seiner Basis-Engine zurückgegebenen Werte neu sortiert. Jeder Konstruktor füllt die interne Tabelle mit *K* -Werten, die von der Basis-Engine zurückgegeben werden, und ein zufälliges Element wird aus der Tabelle ausgewählt, wenn ein Wert angefordert wird.

## <a name="requirements"></a>Anforderungen

**Header:** \<random>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[\<random>](../standard-library/random.md)
