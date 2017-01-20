---
title: "discard_block_engine-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "tr1.discard_block_engine"
  - "std.tr1.discard_block_engine"
  - "std::tr1::discard_block_engine"
  - "random/std::tr1::discard_block_engine"
  - "discard_block_engine"
  - "tr1::discard_block_engine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "discard_block_engine-Klasse"
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
caps.latest.revision: 18
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# discard_block_engine-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Generiert eine zufällige Sequenz, indem die vom Basismodul zurückgegebenen Werte verworfen werden.  
  
## Syntax  
  
```  
template<class Engine, size_t P, size_t R> class discard_block_engine;  
```  
  
#### Parameter  
 `Engine`  
 Der Typ des Basismoduls.  
  
 `P`  
 **Blockgröße**.  Die Anzahl von Werten in jedem Block.  
  
 `R`  
 **Verwendeter Block**.  Die Anzahl von Werten in jedem Block, die verwendet werden.  Der Rest wird verworfen \(`P` \- `R`\).  **Vorbedingung**: `0 < R ≤ P`  
  
## Mitglieder  
  
||||  
|-|-|-|  
|`discard_block_engine::discard_block_engine`|`discard_block_engine::base`|`discard_block_engine::discard`|  
|`discard_block_engine::operator()`|`discard_block_engine::base_type`|`discard_block_engine::seed`|  
  
 Weitere Informationen über Modulmember finden Sie unter [\<random\>](../standard-library/random.md).  
  
## Hinweise  
 Diese Vorlagenklasse beschreibt einen Moduladapter, der Werte produziert, indem er einige der von seinem Moduladapter zurückgegebenen Werte verwirft.  
  
## Anforderungen  
 **Header:** \<random\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<random\>](../standard-library/random.md)