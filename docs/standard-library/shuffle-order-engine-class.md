---
title: "shuffle_order_engine-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "shuffle_order_engine"
  - "std.tr1.shuffle_order_engine"
  - "tr1::shuffle_order_engine"
  - "tr1.shuffle_order_engine"
  - "std::tr1::shuffle_order_engine"
  - "random/std::tr1::shuffle_order_engine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "shuffle_order_engine-Klasse"
ms.assetid: 0bcd1fb0-44d7-4e59-bb1b-4a9b673a960d
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# shuffle_order_engine-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Generiert eine zufällige Sequenz durch Neupositionieren der Werte, die von ihrem Basismodul zurückgegeben werden.  
  
## Syntax  
  
```  
template<class Engine, size_t K>  
class shuffle_order_engine;  
```  
  
#### Parameter  
 `Engine`  
 Der Typ des Basismoduls.  
  
 `K`  
 **Tabellengröße**. Anzahl der Elemente im Puffer \(Tabelle\).**Vorbedingung**: `0 < K`  
  
## Mitglieder  
  
||||  
|-|-|-|  
|`shuffle_order_engine::shuffle_order_engine`|`shuffle_order_engine::base`|`shuffle_order_engine::discard`|  
|`shuffle_order_engine::operator()`|`shuffle_order_engine::base_type`|`shuffle_order_engine::seed`|  
  
 Weitere Informationen über Modulmember finden Sie unter [\<random\>](../standard-library/random.md).  
  
## Hinweise  
 Diese Vorlagenklasse beschreibt einen *Moduladapter*, der Werte produziert, indem er die von seinem Moduladapter zurückgegebenen Werte neu sortiert. Jeder Konstruktor füllt die interne Tabelle mit vom Basismodul zurückgegebenen `K`\-Werten. Wenn ein Wert angefordert wird, wird ein Zufallselement aus der Tabelle ausgewählt.  
  
## Anforderungen  
 **Header:** \<random\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<random\>](../standard-library/random.md)