---
title: "InputIterator::operator++-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::InputIterator::operator++"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InputIterator::operator++-Operator"
ms.assetid: 50781585-7a12-4f02-bff8-68fe0adf0693
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# InputIterator::operator++-Operator
Inkrementiert den aktuellen InputIterator.  
  
## Syntax  
  
```  
  
InputIterator& operator++();  
  
InputIterator operator++(  
   int  
);  
```  
  
## Rückgabewert  
 Die erste Syntax inkrementiert den aktuellen InputIterator und gibt ihn dann zurück. Die zweite Syntax gibt eine Kopie des aktuellen InputIterator zurück und inkrementiert dann den aktuellen InputIterator.  
  
## Hinweise  
 Die ersten InputIterator\-Syntax vorinkrementiert den aktuellen InputIterator.  
  
 Die zweite Syntax nachinkrementiert den aktuellen InputIterator. Der Typ `int` in der zweiten Syntax gibt eine Nach\-Inkrementierungsoperation an, keinen tatsächlichen ganzzahligen Operanden.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::InputIterator\-Klasse](../cppcx/platform-collections-inputiterator-class.md)