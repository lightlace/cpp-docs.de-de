---
title: "VectorIterator::operator&gt;=-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator>="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator>=-Operator"
ms.assetid: 8154015e-8da7-4381-8128-d3669eb88e16
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator&gt;=-Operator
Gibt an, ob der aktuelle VectorIterator größer oder gleich dem angegebenen VectorIterator ist.  
  
## Syntax  
  
```cpp  
  
bool operator>=(  
   const VectorIterator& other  
) const   
```  
  
#### Parameter  
 `other`  
 Ein weiterer VectorIterator.  
  
## Rückgabewert  
 `true`, wenn der aktuelle VectorIterator größer oder gleich `other` ist, andernfalls `false`.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::VectorIterator\-Klasse](../cppcx/platform-collections-vectoriterator-class.md)