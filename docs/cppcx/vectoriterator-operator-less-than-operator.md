---
title: "VectorIterator::operator&lt;-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator<"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator<-Operator"
ms.assetid: 1d7dabdd-70da-4c39-b76e-e22e743751a0
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator&lt;-Operator
Gibt an, ob der aktuelle VectorIterator kleiner einem angegebenen VectorIterator ist.  
  
## Syntax  
  
```cpp  
  
bool operator<(  
   const VectorIterator& other  
) const   
```  
  
#### Parameter  
 `other`  
 Ein weiterer VectorIterator.  
  
## Rückgabewert  
 `true`, wenn der aktuelle VectorIterator kleiner als `other` ist, andernfalls `false`.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::VectorIterator\-Klasse](../cppcx/platform-collections-vectoriterator-class.md)