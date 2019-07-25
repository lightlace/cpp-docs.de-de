---
title: discard_block_engine-Klasse
ms.date: 11/04/2016
f1_keywords:
- random/std::discard_block_engine
helpviewer_keywords:
- discard_block_engine class
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
ms.openlocfilehash: 76a78a2f47bd160c6b2b981b1ccdda2ef3a90575
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454398"
---
# <a name="discardblockengine-class"></a>discard_block_engine-Klasse

Generiert eine zufällige Sequenz, indem die von der Basis-Engine zurückgegebenen Werte verworfen werden.

## <a name="syntax"></a>Syntax

```cpp
template <class Engine, size_t P, size_t R>
class discard_block_engine;
```

### <a name="parameters"></a>Parameter

*Ge*\
Der Typ der Basis-Engine.

*CKER*\
**Blockgröße**. Die Anzahl von Werten in jedem Block.

*R*\
**Verwendeter Block**. Die Anzahl von Werten in jedem Block, die verwendet werden. Der Rest wird verworfen (`P` - `R`). **Vorbedingung**:`0 < R ≤ P`

## <a name="members"></a>Member

||||
|-|-|-|
|`discard_block_engine::discard_block_engine`|`discard_block_engine::base`|`discard_block_engine::discard`|
|`discard_block_engine::operator()`|`discard_block_engine::base_type`|`discard_block_engine::seed`|

Weitere Informationen über Engine-Member finden Sie unter [\<random&gt;](../standard-library/random.md).

## <a name="remarks"></a>Hinweise

Diese Vorlagenklasse beschreibt einen Engine-Adapter, der Werte produziert, indem er die von seiner Basis-Engine zurückgegebenen Werte neu sortiert.

## <a name="requirements"></a>Anforderungen

**Header:** \<random>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[\<random>](../standard-library/random.md)
