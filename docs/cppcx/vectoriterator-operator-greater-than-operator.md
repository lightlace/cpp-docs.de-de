---
title: "VectorIterator::operator&gt;-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator>-Operator"
ms.assetid: a9a323a4-d28a-4080-a48c-ed4c8ef2eafb
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator&gt;-Operator
Gibt an, ob der aktuelle VectorIterator größer als ein angegebener VectorIterator ist.  
  
## Syntax  
  
```cpp  
  
bool operator>(  
   const VectorIterator& other  
) const   
```  
  
#### Parameter  
 `other`  
 Ein weiterer VectorIterator.  
  
## Rückgabewert  
 `true`, wenn der aktuelle VectorIterator größer als `other` ist, andernfalls `false`.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::VectorIterator\-Klasse](../cppcx/platform-collections-vectoriterator-class.md)