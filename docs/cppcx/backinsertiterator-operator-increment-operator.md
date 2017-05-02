---
title: "BackInsertIterator::operator++-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::BackInsertIterator::operator++"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BackInsertIterator::operator++-Operator"
ms.assetid: 08324574-db2b-4d95-825e-a93a56f327da
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# BackInsertIterator::operator++-Operator
Gibt einen Verweis auf den aktuellen BackInsertIterator zurück. Der Iterator ist unverändert.  
  
## Syntax  
  
```  
  
BackInsertIterator& operator++();  
  
BackInsertIterator operator++(  
   int  
);  
```  
  
## Rückgabewert  
 Ein Verweis auf den aktuellen BackInsertIterator.  
  
## Hinweise  
 Im ersten Syntaxbeispiel wird der aktuelle BackInsertIterator absichtlich präinkrementiert und in der zweiten Syntax wird der aktuelle BackInsertIterator postinkrementiert. Der Typ `int` in der zweiten Syntax gibt eine Nach\-Inkrementierungsoperation an, keinen tatsächlichen ganzzahligen Operanden.  
  
 Dieser Operator ändert jedoch nicht wirklich den BackInsertIterator. Stattdessen gibt dieser Operator einen Verweis auf den unveränderten, aktuellen Iterator zurück. Dieses Verhalten entspricht dem von [Operator\*](../cppcx/backinsertiterator-operator-dereference-operator.md).  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::BackInsertIterator\-Klasse](../cppcx/platform-collections-backinsertiterator-class.md)