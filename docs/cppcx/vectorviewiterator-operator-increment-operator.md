---
title: "VectorViewIterator::operator++-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator++"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator++-Operator"
ms.assetid: 5391e6e2-a7ee-4dab-8cee-b2237894246f
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator++-Operator
Inkrementiert den aktuellen VectorViewIterator.  
  
## Syntax  
  
```  
  
VectorViewIterator& operator++();  
VectorViewIterator operator++(  
   int  
);  
```  
  
## Rückgabewert  
 Die erste Syntax inkrementiert den aktuellen VectorViewIterator und gibt ihn dann zurück. Die zweite Syntax gibt eine Kopie des aktuellen VectorViewIterator zurück und inkrementiert dann den aktuellen VectorViewIterator.  
  
## Hinweise  
 In der ersten VectorViewIterator\-Syntax wird der aktuelle VectorViewIterator vorinkrementiert.  
  
 In der zweiten Syntax wird der aktuelle VectorViewIterator nachinkrementiert. Der Typ `int` in der zweiten Syntax gibt eine Nach\-Inkrementierungsoperation an, keinen tatsächlichen ganzzahligen Operanden.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::VectorViewIterator\-Klasse](../cppcx/platform-collections-vectorviewiterator-class.md)