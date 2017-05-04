---
title: "VectorIterator::operator-&gt;-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator->"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator->-Operator"
ms.assetid: d6caed5c-4899-45f8-95a2-687eafeeb8e1
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator-&gt;-Operator
Ruft die Adresse des Elements ab, auf das vom aktuellen VectorIterator verwiesen wird.  
  
## Syntax  
  
```  
Detail::ArrowProxy<T> operator->() const;  
```  
  
## Rückgabewert  
 Der Wert des Elements, auf das vom aktuellen VectorIterator verwiesen wird.  
  
 Der Typ des Rückgabewerts ist ein nicht angegebener interner Typ, der für die Implementierung dieses Operators erforderlich ist.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::VectorIterator\-Klasse](../cppcx/platform-collections-vectoriterator-class.md)