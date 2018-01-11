---
title: shuffle_order_engine-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- random/std::shuffle_order_engine
- random/std::shuffle_order_engine::base
- random/std::shuffle_order_engine::discard
- random/std::shuffle_order_engine::operator()
- random/std::shuffle_order_engine::base_type
- random/std::shuffle_order_engine::seed
dev_langs: C++
helpviewer_keywords:
- std::shuffle_order_engine [C++]
- std::shuffle_order_engine [C++], base
- std::shuffle_order_engine [C++], discard
- std::shuffle_order_engine [C++], base_type
- std::shuffle_order_engine [C++], seed
ms.assetid: 0bcd1fb0-44d7-4e59-bb1b-4a9b673a960d
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 43de5df2afa0aca7e1634eac0338ae1b49ea9372
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
  
## <a name="members"></a>Member  
  
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

