---
title: "__based-Grammatik"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Basierende Adressierung"
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# __based-Grammatik
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Die basierende Adressierung ist nützlich, wenn eine genaue Kontrolle über das Segment erforderlich ist, in dem Objekte zugeordnet sind \(statische und dynamische basierende Daten\).  
  
 Die einzige Form der basierenden Adressierung, die in 32\-Bit\- und 64\-Bit\-Kompilierungen zulässig ist "basiert auf einem Zeiger". Dieser gibt einen Typ an, der eine 32\-Bit\- oder 64\-Bit\-Verschiebung auf eine 32\-Bit\- oder 64\-Bit\-Basis enthält oder auf `void` basiert.  
  
## Grammatik  
 *based\-range\-modifier*:  
 **\_\_based\(**  *base\-expression*  **\)**  
  
 *base\-expression*:  
 *based\-variablebased\-abstract\-declaratorsegment\-namesegment\-cast*  
  
 *based\-variable*:  
 *identifier*  
  
 *based\-abstract\-declarator*:  
 *abstract\-declarator*  
  
 *base\-type*:  
 *Typname*  
  
## END Microsoft\-spezifisch  
  
## Siehe auch  
 [Basierte Zeiger](../cpp/based-pointers-cpp.md)