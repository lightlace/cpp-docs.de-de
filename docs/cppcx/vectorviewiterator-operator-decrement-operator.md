---
title: "VectorViewIterator::operator---Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator--"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator---Operator"
ms.assetid: edf3ba42-1fa4-4795-9a37-1f7dfb23ad19
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator---Operator
Dekrementiert den aktuellen VectorViewIterator.  
  
## Syntax  
  
```  
VectorViewIterator& operator--();  
VectorViewIterator operator--(  
   int  
);  
```  
  
## Rückgabewert  
 Die erste Syntax dekrementiert den aktuellen VectorViewIterator und gibt ihn dann zurück. Die zweite Syntax gibt eine Kopie des aktuellen VectorViewIterator zurück und dekrementiert dann den aktuellen VectorViewIterator.  
  
## Hinweise  
 In der ersten VectorViewIterator\-Syntax wird der aktuelle VectorViewIterator vordekrementiert.  
  
 In der zweiten Syntax wird der aktuelle VectorViewIterator nachdekrementiert. Der Typ `int` in der zweiten Syntax gibt eine Nach\-Dekrementierungsoperation an, keinen tatsächlichen ganzzahligen Operanden.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::VectorViewIterator\-Klasse](../cppcx/platform-collections-vectorviewiterator-class.md)