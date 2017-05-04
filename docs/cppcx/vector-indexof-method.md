---
title: "Vector::IndexOf-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::IndexOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::IndexOf-Methode"
ms.assetid: 4a965992-3858-4e3f-992a-b94c0580b2f7
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::IndexOf-Methode
Sucht das angegebene Element im aktuellen Vector und gibt, wenn es gefunden wurde, den Index des Elements zurück.  
  
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
  
 Der `index`\-Parameter ist 0, wenn das Element entweder das erste Element des Vektors ist oder wenn das Element nicht gefunden wurde. Wenn der Rückgabewert `true` ist, wurde das Element gefunden und es ist das erste Element; andernfalls wurde das Element nicht gefunden.  
  
## Rückgabewert  
 `true` wenn das angegebene Element gefunden wurde, andernfalls `false`.  
  
## Hinweise  
 IndexOf verwendet std::find\_if, um das Element zu suchen. Benutzerdefinierte Elementtypen sollten deshalb den Operator \=\= und \!\= überladen, um die Übereinstimmungsvergleiche zu ermöglichen, die für "find\_if" erforderlich sind.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::Vector\-Klasse](../cppcx/platform-collections-vector-class.md)