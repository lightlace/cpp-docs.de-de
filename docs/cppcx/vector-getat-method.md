---
title: "Vector::GetAt-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::GetAt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::GetAt-Methode"
ms.assetid: 3766b399-cef2-4006-9a87-50f717390cac
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::GetAt-Methode
Ruft das Element des aktuellen Vector ab, das durch den angegebenen Index bezeichnet wird.  
  
## Syntax  
  
```  
  
virtual T GetAt(  
   unsigned int index  
);  
```  
  
#### Parameter  
 `index`  
 Eine nullbasierte, ganze Zahl ohne Vorzeichen, die ein bestimmtes Element im Vector\-Objekt spezifiziert.  
  
## Rückgabewert  
 Das Element, das durch den `index`\-Parameter spezifiziert wird. Der Elementtyp wird durch den *T*\-Typnamen definiert.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::Vector\-Klasse](../cppcx/platform-collections-vector-class.md)