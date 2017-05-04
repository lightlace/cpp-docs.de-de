---
title: "VectorView::GetMany-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::GetMany"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::GetMany-Methode"
ms.assetid: 67d9348f-66fe-417e-9e25-5de0a3cd306c
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::GetMany-Methode
Ruft eine Sequenz von Elementen von der aktuellen VectorView ab, die am angegebenen Index beginnt.  
  
## Syntax  
  
```  
  
virtual unsigned int GetMany(  
   unsigned int startIndex,   
   ::Platform::WriteOnlyArray<T>^ dest  
);  
```  
  
#### Parameter  
 `startIndex`  
 Der nullbasierte Index des Anfangs der Elemente, die abgerufen werden sollen.  
  
 `dest`  
 Wenn die Operation abgeschlossen wird, ein Array von Elementen, die bei dem Element beginnen, das durch `startIndex` angegeben ist, und beim letzten Element im Vektor enden.  
  
## Rückgabewert  
 Die Anzahl der abgerufenen Elemente.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [VectorView Class](http://msdn.microsoft.com/de-de/79697692-ae58-40e0-958f-cf1be6347994)