---
title: "Map::GetView-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::GetView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map::GetView-Methode"
ms.assetid: d432bb98-d354-4caa-8c2b-794406ac0b0b
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::GetView-Methode
Gibt eine schreibgeschützte Ansicht der aktuellen Zuordnung zurück; das heißt, eine [Platform::Collections::MapView\-Klasse](../cppcx/platform-collections-mapview-class.md), die die Schnittstelle [Windows::Foundation::Collections::IMapView\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br226037.aspx) implementiert.  
  
## Syntax  
  
```  
  
Windows::Foundation::Collections::IMapView<K, V>^   
   GetView();  
```  
  
## Rückgabewert  
 Ein `MapView`\-Objekt.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::Map\-Klasse](../cppcx/platform-collections-map-class.md)   
 [Platform::Collections::UnorderedMapClass](../cppcx/platform-collections-unorderedmap-class.md)   
 [Auflistungen \(C\+\+\/CX\)](../cppcx/collections-c-cx.md)