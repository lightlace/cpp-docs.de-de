---
title: "VectorIterator::operator+-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator+"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator+-Operator"
ms.assetid: 5e907537-7d10-4766-a412-e7ea08b3456a
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator+-Operator
Gibt einen VectorIterator zurück, der auf das Element an der angegebenen Verschiebung von dem angegebenen VectorIterator verweist.  
  
## Syntax  
  
```  
  
VectorIterator operator+(  
   difference_type n) ;  
  
template <  
   typename T  
>  
inline VectorIterator<T> operator+(  
   ptrdiff_t n,  
   const VectorIterator<T>& i  
);  
  
```  
  
#### Parameter  
 `T`  
 In der zweiten Syntax der Typname vom VectorIterator.  
  
 `n`  
 Eine ganzzahlige Verschiebung.  
  
 `i`  
 In der zweiten Syntax ein VectorIterator.  
  
## Rückgabewert  
 In der ersten Syntax ein VectorIterator, der auf das Element an der angegebenen Verschiebung vom aktuellen VectorIterator verweist.  
  
 In der zweiten Syntax ein VectorIterator, der auf das Element an der angegebenen Verschiebung vom Anfang des Parameters `i` verweist.  
  
## Hinweise  
 Das erste Syntaxbeispiel  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [\(NOTINBUILD\) Plattformnamespace](http://msdn.microsoft.com/de-de/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)