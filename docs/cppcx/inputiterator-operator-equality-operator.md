---
title: "InputIterator::operator==-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::InputIterator::operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InputIterator::operator==-Operator"
ms.assetid: 84f1b69a-77b9-467c-ad1a-2fe8a7c3009e
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# InputIterator::operator==-Operator
Gibt an, ob der aktuelle InputIterator gleich einem angegebenen InputIterator ist.  
  
## Syntax  
  
```  
bool operator==(  
   const InputIterator& other  
) const;  
```  
  
#### Parameter  
 `other`  
 Ein weiterer InputIterator.  
  
## Rückgabewert  
 `true`, wenn der aktuelle InputIterator gleich `other` ist, andernfalls `false`.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::InputIterator\-Klasse](../cppcx/platform-collections-inputiterator-class.md)