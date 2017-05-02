---
title: "VectorViewIterator::operator+-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator+"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator+-Operator"
ms.assetid: 8206de2f-61b3-49cd-9715-d57695d880b3
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator+-Operator
Gibt einen VectorViewIterator zurück, der auf das Element an der angegebenen Verschiebung von dem angegebenen VectorViewIterator verweist.  
  
## Syntax  
  
```  
  
VectorViewIterator operator+(  
   difference_type n  
) const;  
  
template <  
   typename T  
>   
inline VectorViewIterator<T> operator+  
   (ptrdiff_t n,   
   const VectorViewIterator<T>& i  
);  
  
```  
  
#### Parameter  
 `T`  
 In der zweiten Syntax der Typname vom VectorViewIterator.  
  
 `n`  
 Eine ganzzahlige Verschiebung.  
  
 `i`  
 In der zweiten Syntax ein VectorViewIterator.  
  
## Rückgabewert  
 In der ersten Syntax ein VectorViewIterator, der auf das Element an der angegebenen Verschiebung vom aktuellen VectorViewIterator verweist.  
  
 In der zweiten Syntax ein VectorViewIterator, der auf das Element an der angegebenen Verschiebung vom Anfang des Parameters `i` verweist.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::VectorViewIterator\-Klasse](../cppcx/platform-collections-vectorviewiterator-class.md)