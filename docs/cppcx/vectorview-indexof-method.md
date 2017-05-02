---
title: "VectorView::IndexOf-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::IndexOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::IndexOf-Methode"
ms.assetid: 848117ec-ad4a-4a0b-9c1e-9076e5188869
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::IndexOf-Methode
Sucht das angegebene Element in der aktuellen VectorView und gibt, wenn es gefunden wurde, den Index des Elements zurück.  
  
## Syntax  
  
```  
  
virtual bool IndexOf(  
   T value,  
   unsigned int* index  
);  
```  
  
#### Parameter  
 `value`  
 Das Element, das gesucht werden soll.  
  
 `index`  
 Der nullbasierte Index des Elements, wenn der Parameter `value` gefunden wurde, andernfalls 0.  
  
 Der `index`\-Parameter ist 0, wenn das Element entweder das erste Element der VectorView ist oder wenn das Element nicht gefunden wurde. Wenn der Rückgabewert `true` ist, wurde das Element gefunden und es ist das erste Element; andernfalls wurde das Element nicht gefunden.  
  
## Rückgabewert  
 `true` wenn das angegebene Element gefunden wurde, andernfalls `false`.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [VectorView Class](http://msdn.microsoft.com/de-de/79697692-ae58-40e0-958f-cf1be6347994)