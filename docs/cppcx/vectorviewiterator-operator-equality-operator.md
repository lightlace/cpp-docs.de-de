---
title: "VectorViewIterator::operator==-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator==-Operator"
ms.assetid: 89534116-5035-413b-89d3-073eedb88337
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator==-Operator
Gibt an, ob der aktuelle VectorViewIterator gleich einem angegebenen VectorViewIterator ist.  
  
## Syntax  
  
```  
bool operator==(  
   const VectorViewIterator& other  
) const;  
```  
  
#### Parameter  
 `other`  
 Ein weiterer VectorViewIterator.  
  
## Rückgabewert  
 `true`, wenn der aktuelle VectorViewIterator gleich dem `other` ist, andernfalls `false`.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::VectorViewIterator\-Klasse](../cppcx/platform-collections-vectorviewiterator-class.md)