---
title: "VectorViewIterator::operator-&gt;-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator->"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator->-Operator"
ms.assetid: cc02cfa2-dfcb-4fb7-b4a0-c290f91aa4a6
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator-&gt;-Operator
Ruft die Adresse des Elements ab, auf das vom aktuellen VectorViewIterator verwiesen wird.  
  
## Syntax  
  
```  
Detail::ArrowProxy<T> operator->() const;  
```  
  
## Rückgabewert  
 Der Wert des Elements, auf das vom aktuellen VectorViewIterator verwiesen wird.  
  
 Der Typ des Rückgabewerts ist ein nicht angegebener interner Typ, der für die Implementierung dieses Operators erforderlich ist.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::VectorViewIterator\-Klasse](../cppcx/platform-collections-vectorviewiterator-class.md)