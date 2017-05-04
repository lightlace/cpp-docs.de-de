---
title: "VectorIterator::operator---Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator--"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator---Operator"
ms.assetid: 650a3037-2984-4110-9d7c-cd3756e5f4b9
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator---Operator
Dekrementiert den aktuellen VectorIterator.  
  
## Syntax  
  
```  
  
VectorIterator& operator--();  
VectorIterator operator--(  
   int  
);  
```  
  
## Rückgabewert  
 Die erste Syntax dekrementiert und gibt dann den aktuellen VectorIterator zurück. Die zweite Syntax gibt eine Kopie des aktuellen VectorIterator zurück und dekrementiert dann den aktuellen VectorIterator.  
  
## Hinweise  
 Die erste VectorIterator\-Syntax prädekrementiert den aktuellen VectorIterator.  
  
 Die zweite Syntax postdekrementiert den aktuellen VectorIterator. Der Typ `int` in der zweiten Syntax gibt eine Nach\-Dekrementierungsoperation an, keinen tatsächlichen ganzzahligen Operanden.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::VectorIterator\-Klasse](../cppcx/platform-collections-vectoriterator-class.md)