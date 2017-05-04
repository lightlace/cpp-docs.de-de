---
title: "UnorderedMapView::UnorderedMapView-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "01/25/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView::UnorderedMapView"
ms.assetid: 408aa6ca-dd8d-4946-a817-42a31d19f429
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMapView::UnorderedMapView-Konstruktor
Initialisiert eine neue Instanz der UnorderedMapView\-Klasse.  
  
## Syntax  
  
```cpp  
  
UnorderedMapView();  
  
explicit UnorderedMapView(size_t n);  
  
UnorderedMapView(size_t n, const H& h);  
  
UnorderedMapView(size_t n, const H& h, const P& p);  
  
explicit UnorderedMapView(  
    const std::unordered_map<K, V, H, P>& m  
    );  
explicit UnorderedMapView(  
    std::unordered_map<K, V, H, P>&& m  
    );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last  
    );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n  
    );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n,  
    const H& h  
    );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n,  
    const H& h,  
    const P& p  
    );  
  
UnorderedMapView(  
    std::initializer_list<std::pair<const K, V>> il  
    );  
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n  
    );  
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n,  
    const H& h  
    );  
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n,  
    const H& h,  
    const P& p  
    );  
```  
  
#### Parameter  
 n  
 Die Anzahl der Elemente, für die Speicherplatz vorab zugewiesen werden soll.  
  
 `InIt`  
 Der Typname der UnorderedMapView.  
  
 `H`  
 Ein Funktionsobjekt, das einen Hashwert für einen Schlüssel haben kann. Standardmäßig [std::hash\<K\>](http://msdn.microsoft.com/de-de/54f67435-af9d-4217-a29d-fa4d2491a104) für die Typen, die von `std::hash` unterstützt werden.  
  
 `P`  
 Ein Typ, der ein Funktionsobjekt bereitstellt, das zwei Schlüssel vergleichen kann, um deren Gleichheit zu bestimmen. Standardmäßig [std::equal\_to \<K\>](../standard-library/equal-to-struct.md).  
  
 `m`  
 Ein Verweis oder [Lvalues und Rvalues](~/cpp/lvalues-and-rvalues-visual-cpp.md) zu einer [std::unordered\_map](../standard-library/unordered-map-class.md), die verwendet wird, um die UnorderedMapView zu initialisieren.  
  
 `first`  
 Der Eingabeiterator des ersten Elements in einem Bereich von Elementen, die verwendet werden, um die UnorderedMapView zu initialisieren.  
  
 `last`  
 Der Eingabeiterator des ersten Elements nach einem Bereich von Elementen, die verwendet werden, um die UnorderedMapView zu initialisieren.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::UnorderedMapView\-Klasse](../cppcx/platform-collections-unorderedmapview-class.md)