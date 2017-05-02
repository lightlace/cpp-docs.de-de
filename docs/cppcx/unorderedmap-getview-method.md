---
title: "UnorderedMap::GetView-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::GetView"
ms.assetid: 41a12802-3f42-461c-a6fc-a35fc34517f2
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::GetView-Methode
Gibt eine schreibgeschützte Ansicht der aktuellen UnorderedMap zurück; das heißt, eine [Platform::Collections::UnorderedMapView\-Klasse](../cppcx/platform-collections-unorderedmapview-class.md), die die Schnittstelle [Windows::Foundation::Collections::IMapView::IMapView](http://msdn.microsoft.com/library/windows/apps/br226037.aspx) implementiert.  
  
## Syntax  
  
```scr  
  
Windows::Foundation::Collections::IMapView<K, V>^   
   GetView();  
```  
  
## Rückgabewert  
 Ein `UnorderedMapView`\-Objekt.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Auflistungen](../cppcx/collections-c-cx.md)   
 [Platform::Collections::UnorderedMap\-Klasse](../cppcx/platform-collections-unorderedmap-class.md)   
 [Platform::Collections::UnorderedMapView\-Klasse](../cppcx/platform-collections-unorderedmapview-class.md)