---
title: "UnorderedMapView::Split-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView::Split"
ms.assetid: b759d254-40c9-40f1-9838-106ffb2c5626
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMapView::Split-Methode
Teilt das aktuelle UnorderedMapView\-Objekt in zwei UnorderedMapView\-Objekte. Diese Methode führt keine Operationen aus.  
  
## Syntax  
  
```cpp  
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
 Der erste Teil des ursprünglichen UnorderedMapView\-Objekts.  
  
 `secondPartition`  
 Der zweite Teil des ursprünglichen UnorderedMapView\-Objekts.  
  
## Hinweise  
 Diese Methode führt keine Operationen aus und hat keine Auswirkungen.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::UnorderedMapView\-Klasse](../cppcx/platform-collections-unorderedmapview-class.md)