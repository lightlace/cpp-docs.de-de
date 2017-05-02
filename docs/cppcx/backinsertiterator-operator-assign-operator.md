---
title: "BackInsertIterator::operator=-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::BackInsertIterator::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BackInsertIterator::operator=-Operator"
ms.assetid: 509c9b4c-14fb-4318-bf65-b8926cc72f4f
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# BackInsertIterator::operator=-Operator
Fügt das angegebene Objekt am Ende der aktuellen sequenziellen Auflistung an.  
  
## Syntax  
  
```  
  
BackInsertIterator& operator=(  
   const T& t  
);  
```  
  
#### Parameter  
 `t`  
 Das Objekt, das der aktuellen Auflistung angefügt werden soll.  
  
## Rückgabewert  
 Ein Verweis auf den aktuellen BackInsertIterator.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::BackInsertIterator\-Klasse](../cppcx/platform-collections-backinsertiterator-class.md)