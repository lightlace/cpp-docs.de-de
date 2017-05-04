---
title: "VectorIterator::operator--Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator-"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator--Operator"
ms.assetid: 5714c132-e973-47fd-901b-ba13da7b9372
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator--Operator
Subtrahiert entweder eine angegebene Anzahl von Elementen vom aktuellen Iterator und bildet einen neuen Iterator, oder subtrahiert einen angegebenen Iterator vom aktuellen Iterator, und gibt die Anzahl von Elementen zwischen den Iteratoren zurück.  
  
## Syntax  
  
```  
  
VectorIterator operator-(  
   difference_type n  
) const;  
  
difference_type operator-(  
   const VectorIterator& other  
) const;  
```  
  
#### Parameter  
 `n`  
 Eine Anzahl von Elementen.  
  
 `other`  
 Ein weiterer VectorIterator.  
  
## Rückgabewert  
 Die erste Operatorsyntax gibt ein VectorIterator\-Objekt zurück, das `n` Elemente kleiner ist, als der aktuelle VectorIterator. Die zweite Operatorsyntax gibt die Anzahl von Elementen zwischen dem aktuellen und dem `other` VectorIterator zurück.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::VectorIterator\-Klasse](../cppcx/platform-collections-vectoriterator-class.md)