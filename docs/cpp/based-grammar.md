---
title: "__based-Grammatik | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Basierende Adressierung"
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
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