---
title: shuffle_order_engine-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- shuffle_order_engine
- random/std::shuffle_order_engine
- random/std::shuffle_order_engine::base
- random/std::shuffle_order_engine::discard
- random/std::shuffle_order_engine::operator()
- random/std::shuffle_order_engine::base_type
- random/std::shuffle_order_engine::seed
dev_langs:
- C++
helpviewer_keywords:
- shuffle_order_engine class
ms.assetid: 0bcd1fb0-44d7-4e59-bb1b-4a9b673a960d
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 93c5721a4b651315bc4d67cc9d5a0cb7d2f852a3
ms.contentlocale: de-de
ms.lasthandoff: 04/19/2017

---
# <a name="shuffleorderengine-class"></a>shuffle_order_engine-Klasse
Generiert eine zufällige Sequenz durch Neupositionieren der Werte, die von ihrem Basismodul zurückgegeben werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Engine, size_t K>  
class shuffle_order_engine;  
```  
  
#### <a name="parameters"></a>Parameter  
 `Engine`  
 Der Typ des Basismoduls.  
  
 `K`  
 **Tabellengröße**. Anzahl der Elemente im Puffer (Tabelle). **Vorbedingung**:`0 < K`  
  
## <a name="members"></a>Mitglieder  
  
||||  
|-|-|-|  
|`shuffle_order_engine::shuffle_order_engine`|`shuffle_order_engine::base`|`shuffle_order_engine::discard`|  
|`shuffle_order_engine::operator()`|`shuffle_order_engine::base_type`|`shuffle_order_engine::seed`|  
  
 Weitere Informationen über Modulmember finden Sie unter [\<random>](../standard-library/random.md).  
  
## <a name="remarks"></a>Hinweise  
 Diese Vorlagenklasse beschreibt einen *Moduladapter*, der Werte produziert, indem er die von seinem Basismodul zurückgegebenen Werte neu sortiert. Jeder Konstruktor füllt die interne Tabelle mit vom Basismodul zurückgegebenen `K`-Werten. Wenn ein Wert angefordert wird, wird ein Zufallselement aus der Tabelle ausgewählt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<random>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [\<random>](../standard-library/random.md)


