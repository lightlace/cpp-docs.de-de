---
title: "VectorViewIterator::VectorViewIterator-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::VectorViewIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::VectorViewIterator-Konstruktor"
ms.assetid: 30bf643a-4100-4547-b34c-ce16c89f78ed
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::VectorViewIterator-Konstruktor
Initialisiert eine neue Instanz der VectorViewIterator\-Klasse.  
  
## Syntax  
  
```  
  
VectorViewIterator();  
  
explicit VectorViewIterator(  
   Windows::Foundation::Collections::IVectorView<T>^ v  
);  
```  
  
#### Parameter  
 `v`  
 Ein IVectorView\<T\>\-Objekt.  
  
## Hinweise  
 Das erste Syntaxbeispiel ist der Standardkonstruktor. Das zweite Syntaxbeispiel ist ein expliziter Konstruktor, der verwendet wird, um einen VectorViewIterator aus einem IVectorView\<T\>\-Objekt zu erstellen.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::VectorViewIterator\-Klasse](../cppcx/platform-collections-vectorviewiterator-class.md)