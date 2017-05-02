---
title: "VectorIterator::operatorOperator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator[]"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator[]-Operator"
ms.assetid: e1ba8101-8c16-4be1-b31b-91099d6e81f3
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operatorOperator
Ruft einen Verweis auf das Element ab, das eine angegebene Verschiebung vom aktuellen VectorIterator ist.  
  
## Syntax  
  
```  
  
reference operator[](difference_type n) const;  
```  
  
#### Parameter  
 `n`  
 Eine ganzzahlige Verschiebung.  
  
## Rückgabewert  
 Das Element, das vom aktuellen VectorIterator durch die `n`\-Elemente ersetzt wird.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::VectorIterator\-Klasse](../cppcx/platform-collections-vectoriterator-class.md)