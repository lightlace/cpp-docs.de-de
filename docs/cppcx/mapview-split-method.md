---
title: "MapView::Split-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView::Split"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MapView::Split-Methode"
ms.assetid: b863e223-2282-4d1a-b995-77a690120542
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# MapView::Split-Methode
Teilt das aktuelle MapView\-Objekt in zwei MapView\-Objekte. Diese Methode führt keine Operationen aus.  
  
## Syntax  
  
```  
void Split(  
   Windows::Foundation::Collections::IMapView<  
                         K,  
                         V>^ * firstPartition,  
   Windows::Foundation::Collections::IMapView<  
                         K,  
                         V>^ * secondPartition  
);  
```  
  
#### Parameter  
 `firstPartition`  
 Der erste Teil des ursprünglichen MapView\-Objekts.  
  
 `secondPartition`  
 Der zweite Teil des ursprünglichen MapView\-Objekts.  
  
## Hinweise  
 Diese Methode führt keine Operationen aus und hat keine Auswirkungen.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::MapView\-Klasse](../cppcx/platform-collections-mapview-class.md)