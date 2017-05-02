---
title: "VectorViewIterator::operatorOperator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator[]"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator[]-Operator"
ms.assetid: 41bf327d-2037-457c-83df-6338fc1abbc2
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operatorOperator
Ruft einen Verweis auf das Element ab, das eine angegebene Verschiebung vom aktuellen VectorViewIterator ist.  
  
## Syntax  
  
```  
reference operator[](difference_type n) const;  
```  
  
#### Parameter  
 `n`  
 Eine ganzzahlige Verschiebung.  
  
## Rückgabewert  
 Das Element, das vom aktuellen VectorViewIterator um `n` Elemente verschoben wird.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::VectorViewIterator\-Klasse](../cppcx/platform-collections-vectorviewiterator-class.md)