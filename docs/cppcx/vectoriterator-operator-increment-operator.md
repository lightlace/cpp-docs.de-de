---
title: "VectorIterator::operator++-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator++"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator++-Operator"
ms.assetid: c46b18ff-45be-436a-8f31-b3a5ecc19b77
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator++-Operator
Inkrementiert den aktuellen VectorIterator.  
  
## Syntax  
  
```  
  
VectorIterator& operator++();  
VectorIterator operator++(  
   int  
);  
```  
  
## Rückgabewert  
 Die erste Syntax inkrementiert und gibt dann den aktuellen VectorIterator zurück. Die zweite Syntax gibt eine Kopie des aktuellen VectorIterator zurück und inkrementiert dann den aktuellen VectorIterator.  
  
## Hinweise  
 Die erste VectorIterator\-Syntax präinkrementiert den aktuellen VectorIterator.  
  
 Die zweite Syntax postinkrementiert den aktuellen VectorIterator. Der Typ `int` in der zweiten Syntax gibt eine Nach\-Inkrementierungsoperation an, keinen tatsächlichen ganzzahligen Operanden.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::VectorIterator\-Klasse](../cppcx/platform-collections-vectoriterator-class.md)