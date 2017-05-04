---
title: "Vector::SetAt-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::SetAt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::SetAt"
ms.assetid: ddfb454e-dbfd-4831-b040-674b085d8fb6
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::SetAt-Methode
Weist den angegebenen Wert dem Element im aktuellen Vektor zu, der vom angegebenen Index identifiziert wird.  
  
## Syntax  
  
```  
  
virtual void SetAt(  
   unsigned int index,   
   T item  
);  
```  
  
#### Parameter  
 `index`  
 Eine nullbasierte, ganze Zahl ohne Vorzeichen, die ein bestimmtes Element im Vector\-Objekt spezifiziert.  
  
 `item`  
 Der dem angegebenen Element zuzuweisende Wert. Der Typ von `item` wird durch den Typnamen *T* definiert.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::Vector\-Klasse](../cppcx/platform-collections-vector-class.md)