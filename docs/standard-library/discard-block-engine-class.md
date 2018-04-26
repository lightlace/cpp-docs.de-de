---
title: discard_block_engine-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- random/std::discard_block_engine
dev_langs:
- C++
helpviewer_keywords:
- discard_block_engine class
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 59136111b6d4f594d84040c02270b219ad55ae0f
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="discardblockengine-class"></a>discard_block_engine-Klasse

Generiert eine zufällige Sequenz, indem die vom Basismodul zurückgegebenen Werte verworfen werden.

## <a name="syntax"></a>Syntax

```cpp
template <class Engine, size_t P, size_t R>
class discard_block_engine;
```

### <a name="parameters"></a>Parameter

`Engine` Der Typ des Basismoduls.

`P` **Blockgröße**. Die Anzahl von Werten in jedem Block.

`R` **Verwendeter Block**. Die Anzahl von Werten in jedem Block, die verwendet werden. Der Rest wird verworfen ( `P` - `R`). **Vorbedingung**:`0 < R ≤ P`

## <a name="members"></a>Member

||||
|-|-|-|
|`discard_block_engine::discard_block_engine`|`discard_block_engine::base`|`discard_block_engine::discard`|
|`discard_block_engine::operator()`|`discard_block_engine::base_type`|`discard_block_engine::seed`|

Weitere Informationen über Modulmember finden Sie unter [\<random>](../standard-library/random.md).

## <a name="remarks"></a>Hinweise

Diese Vorlagenklasse beschreibt einen Moduladapter, der Werte produziert, indem er einige der von seinem Moduladapter zurückgegebenen Werte verwirft.

## <a name="requirements"></a>Anforderungen

**Header:** \<random>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[\<random>](../standard-library/random.md)<br/>
