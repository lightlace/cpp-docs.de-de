---
title: "UnorderedMap::UnorderedMap-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "01/25/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::UnorderedMap"
ms.assetid: bd62e663-7f3a-43ef-ad6d-8266128c778b
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::UnorderedMap-Konstruktor
Initialisiert eine neue Instanz der UnorderedMap\-Klasse.  
  
## Syntax  
  
```scr  
UnorderedMap();  
  
  explicit UnorderedMap(  
      size_t n  
      );  
  
  UnorderedMap(  
      size_t n,  
      const H& h  
      );  
  
  UnorderedMap(  
      size_t n,  
      const H& h,  
      const P& p  
      );  
  
  explicit UnorderedMap(  
      const std::unordered_map<K, V, H, P>& m  
      );  
  
  explicit UnorderedMap(  
      std::unordered_map<K, V, H, P>&& m  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last,  
      size_t n  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last,  
      size_t n,  
      const H& h  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last,  
      size_t n,  
      const H& h,  
      const P& p  
      );  
  
  UnorderedMap(std::initializer_list<  
      std::pair<const K, V>> il  
      );  
  
  UnorderedMap(::std::initializer_list<  
      std::pair<const K, V>> il,  
      size_t n  
      );  
  
  UnorderedMap(  
      ::std::initializer_list< ::std::pair<const K, V>> il,  
      size_t n,  
      const H& h  
      );  
  
  UnorderedMap(::std::initializer_list<  
      ::std::pair<const K, V>> il,  
      size_t n,  
      const H& h,  
      const P& p  
      );  
```  
  
#### Parameter  
 `InIt`  
 Der Typname der aktuellen UnorderedMap.  
  
 `P`  
 Ein Funktionsobjekt, das zwei Schlüssel vergleichen kann, um zu bestimmen, ob sie gleich sind. Dieser Parameter ist standardmäßig [std::equal\_to \<K\>](../standard-library/equal-to-struct.md).  
  
 `H`  
 Ein Funktionsobjekt, das einen Hashwert für Schlüssel erzeugt. Dieser Parameter ist standardmäßig [hash\-Klasse](../Topic/hash%20Class%201.md) für die Typen, die diese Klasse unterstützt.  
  
 `m`  
 Ein Verweis oder [Lvalues und Rvalues](~/cpp/lvalues-and-rvalues-visual-cpp.md) zu einer [std::unordered\_map](../standard-library/unordered-map-class.md), die verwendet wird, um die aktuelle UnorderedMap zu initialisieren.  
  
 il  
 [std::initializer\_list](../standard-library/initializer-list-class.md) von [std::pair](../standard-library/pair-structure.md)\-Objekten, die verwendet werden, um die Zuordnung zu initialisieren.  
  
 `first`  
 Der Eingabeiterator des ersten Elements in einem Bereich von Elementen, die verwendet werden, um die aktuelle UnorderedMap zu initialisieren.  
  
 `last`  
 Der Eingabeiterator des ersten Elements nach einem Bereich von Elementen, die verwendet werden, um die aktuelle UnorderedMap zu initialisieren.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections\-Namespace](../cppcx/platform-collections-namespace.md)   
 [Auflistungen](../cppcx/collections-c-cx.md)