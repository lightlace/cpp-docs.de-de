---
title: "VectorViewIterator::operator&gt;-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator>-Operator"
ms.assetid: c689b677-e3c6-4f6e-8e3a-54d5f2a6123d
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator&gt;-Operator
Gibt an, ob der aktuelle VectorViewIterator größer einem angegebenen VectorViewIterator ist.  
  
## Syntax  
  
```  
  
bool operator>(  
   const VectorViewIterator& other  
) const;  
```  
  
#### Parameter  
 `other`  
 Ein weiterer VectorViewIterator.  
  
## Rückgabewert  
 `true`, wenn der aktuelle VectorViewIterator größer als `other` ist, andernfalls `false`.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::VectorViewIterator\-Klasse](../cppcx/platform-collections-vectorviewiterator-class.md)