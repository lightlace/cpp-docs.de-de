---
title: "independent_bits_engine-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.independent_bits_engine"
  - "std::tr1::independent_bits_engine"
  - "tr1::independent_bits_engine"
  - "tr1.independent_bits_engine"
  - "independent_bits_engine"
  - "random/std::tr1::independent_bits_engine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "independent_bits_engine-Klasse"
ms.assetid: 889e9a82-f457-49a7-9d2e-26e0fc3cd907
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# independent_bits_engine-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Generiert eine zufällige Zahlensequenz mit einer angegebenen Anzahl von Bits, indem Bits aus vom Basismodul zurückgegebenen Werten erneut verpackt werden.  
  
## Syntax  
  
```  
template<class Engine, size_t W, class UIntType> class independent_bits_engine;  
```  
  
#### Parameter  
 `Engine`  
 Der Typ des Basismoduls.  
  
 `W`  
 **Wortgröße**.  Größe jeder generierten Zahl in Bits.  **Vorbedingung**: `0 < W ≤ numeric_limits<UIntType>::digits`  
  
 `UIntType`  
 Der unsigned integer\-Ergebnistyp.  Die möglichen Typen finden Sie unter [\<random\>](../standard-library/random.md).  
  
## Mitglieder  
  
||||  
|-|-|-|  
|`independent_bits_engine::independent_bits_engine`|`independent_bits_engine::base`|`independent_bits_engine::discard`|  
|`independent_bits_engine::operator()`|`independent_bits_engine::base_type`|`independent_bits_engine::seed`|  
  
 Weitere Informationen über Modulmember finden Sie unter [\<random\>](../standard-library/random.md).  
  
## Hinweise  
 Diese Vorlagenklasse beschreibt einen *Moduladapter*, der Werte produziert, indem er die von seinem Moduladapter zurückgegebenen Werte neu verpackt. Dies führt zu `W`\-Bit\-Werten.  
  
## Anforderungen  
 **Header:** \<random\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<random\>](../standard-library/random.md)