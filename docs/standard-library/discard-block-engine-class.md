---
title: discard_block_engine-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- discard_block_engine
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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: b770c9b353f126939a1d70c195b9cc421cb2e06e
ms.contentlocale: de-de
ms.lasthandoff: 04/19/2017

---
# <a name="discardblockengine-class"></a>discard_block_engine-Klasse
Generiert eine zufällige Sequenz, indem die vom Basismodul zurückgegebenen Werte verworfen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Engine, size_t P, size_t R>  
class discard_block_engine;  
```  
  
#### <a name="parameters"></a>Parameter  
 `Engine`  
 Der Typ des Basismoduls.  
  
 `P`  
 **Blockgröße**. Die Anzahl von Werten in jedem Block.  
  
 `R`  
 **Verwendeter Block**. Die Anzahl von Werten in jedem Block, die verwendet werden. Der Rest wird verworfen ( `P` - `R`). **Vorbedingung**: `0 < R ≤ P`  
  
## <a name="members"></a>Mitglieder  
  
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
 [\<random>](../standard-library/random.md)


