---
title: "VectorView::GetAt-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::GetAt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::GetAt-Methode"
ms.assetid: 01c5feda-2a97-4429-ae15-4aced96ce332
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::GetAt-Methode
Ruft das Element der aktuellen VectorView ab, das durch den angegebenen Index bezeichnet wird.  
  
## Syntax  
  
```  
  
T GetAt(  
   UInt32 index  
);  
```  
  
#### Parameter  
 `index`  
 Eine nullbasierte ganze Zahl, die ein bestimmtes Element im VectorView\-Objekt angibt.  
  
## Rückgabewert  
 Das Element, das durch den `index`\-Parameter spezifiziert wird. Der Elementtyp wird durch den VectorView\-Vorlagenparameter *T* angegeben.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [VectorView Class](http://msdn.microsoft.com/de-de/79697692-ae58-40e0-958f-cf1be6347994)