---
title: "VectorView::VectorView-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "01/25/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::VectorView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::VectorView-Konstruktor"
ms.assetid: 5ec14dbc-5f6f-44b6-8fc4-f5a31053eb5f
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::VectorView-Konstruktor
Initialisiert eine neue Instanz der VectorView\-Klasse.  
  
## Syntax  
  
```  
VectorView();  
explicit VectorView(  
   UInt32 size  
);  
VectorView(  
   UInt32 size,  
   T value  
);  
explicit VectorView(  
   const ::std::vector<T>& v  
);  
explicit VectorView(  
   ::std::vector<T>&& v  
);  
VectorView(  
   const T * ptr,  
   UInt32 size  
);  
  
template <  
   size_t N  
>  
explicit VectorView(  
   const T (&arr)[N]  
);  
  
template <  
   size_t N  
>  
explicit VectorView(  
   const ::std::array<T,  
   N>& a  
);  
  
explicit VectorView(  
   const ::Platform::Array<T>^ arr  
);  
  
template <  
   typename InIt  
>  
VectorView(  
   InItfirst,  
   InItlast  
);  
  
VectorView(  
   std::initializer_list<T> il  
);  
```  
  
#### Parameter  
 `InIt`  
 Der Typ einer Auflistung von Objekten, die verwendet wird, um die aktuelle VectorView zu initialisieren.  
  
 il  
 Eine [std::initializer\_list](../standard-library/initializer-list-class.md), deren Elemente verwendet werden, um die VectorView zu initialisieren.  
  
 `N`  
 Die Anzahl von Elementen in einer Auflistung von Objekten, die verwendet wird, um die aktuelle VectorView zu initialisieren.  
  
 `size`  
 Die Anzahl von Elementen in der VectorView.  
  
 `value`  
 Ein Wert, der verwendet wird, um die einzelnen Elemente in der aktuellen VectorView zu initialisieren.  
  
 `v`  
 Ein [Lvalues und Rvalues](~/cpp/lvalues-and-rvalues-visual-cpp.md) zu [::std::vector](../Topic/vector%20Class%201.md), der verwendet wird, um die aktuelle VectorView zu initialisieren.  
  
 `ptr`  
 Zeiger zu `std::vector`, der verwendet wird, um die aktuelle VectorView zu initialisieren.  
  
 `arr`  
 Ein [Platform::Array](../cppcx/platform-array-class.md)\-Objekt, das verwendet wird, um die aktuelle VectorView zu initialisieren.  
  
 `a`  
 Ein [std::array](../Topic/vector%20Class%201.md)\-Objekt, das verwendet wird, um die aktuelle VectorView zu initialisieren.  
  
 `first`  
 Das erste Element in einer Sequenz von Objekten, die verwendet werden, um die aktuelle VectorView zu initialisieren. Der Typ von `first` wird mittels *perfekter Weiterleitung* übergeben. Weitere Informationen finden Sie unter [Rvalue\-Verweisdeklarator: &&](~/cpp/rvalue-reference-declarator-amp-amp.md).  
  
 `last`  
 Das letzte Element in einer Sequenz von Objekten, die verwendet werden, um die aktuelle VectorView zu initialisieren. Der Typ von `last` wird mittels *perfekter Weiterleitung* übergeben. Weitere Informationen finden Sie unter [Rvalue\-Verweisdeklarator: &&](~/cpp/rvalue-reference-declarator-amp-amp.md).  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::Vector\-Klasse](../cppcx/platform-collections-vector-class.md)