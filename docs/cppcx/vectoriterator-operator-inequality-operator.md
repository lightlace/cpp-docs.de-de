---
title: "VectorIterator::operator!=-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator!="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator!=-Operator"
ms.assetid: 88b71c7e-9c88-4282-a518-455059da16c2
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator!=-Operator
Gibt an, ob der aktuelle VectorIterator ungleich einem angegebenen VectorIterator ist.  
  
## Syntax  
  
```  
bool operator!=(  
   const VectorIterator& other  
) const;  
```  
  
#### Parameter  
 `other`  
 Ein weiterer VectorIterator.  
  
## Rückgabewert  
 `true`, wenn der aktuelle VectorIterator ungleich dem `other` ist, andernfalls `false`.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::VectorIterator\-Klasse](../cppcx/platform-collections-vectoriterator-class.md)