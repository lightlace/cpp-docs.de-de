---
title: "MapView::MapView-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "01/25/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView::MapView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MapView::MapView-Konstruktor"
ms.assetid: 67a3250c-b527-47ac-a103-0fd186046d71
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# MapView::MapView-Konstruktor
Initialisiert eine neue Instanz der MapView\-Klasse.  
  
## Syntax  
  
```  
explicit MapView(  
    const C& comp = C()  
    );  
  
explicit MapView(  
    const ::std::map<K, V, C>& m  
    );  
  
explicit MapView(  
    std::map<K, V, C>&& m  
    );  
  
template <typename InIt> MapView(  
    InIt first,  
    InIt last,  
    const C& comp = C()  
    );  
  
MapView(::std::initializer_list<  
    std::pair<const K, V>> il,  
    const C& comp = C()  
    );  
```  
  
#### Parameter  
 `InIt`  
 Der Typname der aktuellen MapView.  
  
 `comp`  
 Ein Funktionsobjekt, das zwei Elementwerte als Sortierschlüssel vergleichen kann, um deren relative Reihenfolge in der MapView zu bestimmen.  
  
 `m`  
 Ein Verweis oder [Lvalues und Rvalues](~/cpp/lvalues-and-rvalues-visual-cpp.md) zu [map\-Klasse](../standard-library/map-class.md), der verwendet wird, um die aktuelle MapView zu initialisieren.  
  
 `first`  
 Der Eingabeiterator des ersten Elements in einem Bereich von Elementen, die verwendet werden, um die aktuelle MapView zu initialisieren.  
  
 `last`  
 Der Eingabeiterator des ersten Elements nach einem Bereich von Elementen, die verwendet werden, um die aktuelle MapView zu initialisieren.  
  
 il  
 Ein [std::initializer\_list \<std::pair\<K,V\>\>](../standard-library/initializer-list-class.md), dessen Elemente in die MapView eingefügt werden.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::MapView\-Klasse](../cppcx/platform-collections-mapview-class.md)