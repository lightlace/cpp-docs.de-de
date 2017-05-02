---
title: "Vector::InsertAt-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::InsertAt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::InsertAt"
ms.assetid: 05b2ca08-234e-4fc0-acfd-cafa148d1577
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::InsertAt-Methode
Fügt das angegebene Element in den aktuellen Vector nach dem Element ein, das durch den angegebenen Index identifiziert wird.  
  
## Syntax  
  
```  
  
virtual void InsertAt(  
   unsigned int index,   
   T item)  
```  
  
#### Parameter  
 `index`  
 Eine nullbasierte, ganze Zahl ohne Vorzeichen, die ein bestimmtes Element im Vector\-Objekt spezifiziert.  
  
 `item`  
 Ein Element, das nach dem durch `index` spezifizierten Elements in den Vector einzufügen ist. Der Typ von `item` wird durch den Typnamen *T* definiert.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::Vector\-Klasse](../cppcx/platform-collections-vector-class.md)