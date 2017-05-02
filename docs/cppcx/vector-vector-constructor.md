---
title: "Vector::Vector-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "01/25/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::Vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::Vector-Konstruktor"
ms.assetid: 5454433d-e206-45ea-bc8b-bb5a7bf38c17
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::Vector-Konstruktor
Initialisiert eine neue Instanz der Vector\-Klasse.  
  
## Syntax  
  
```  
Vector();  
  
explicit Vector(  
    unsigned int size  
    );  
  
Vector(  
    unsigned int size,  
    T value  
    );  
  
template <typename U> explicit Vector(  
    const ::std::vector<U>& v  
    );  
  
template <typename U> explicit Vector(  
    std::vector<U>&& v  
    );  
  
Vector(  
    const T * ptr,  
    unsigned int size  
    );  
  
template <size_t N> explicit Vector(  
    const T(&arr)[N]  
    );  
  
template <size_t N> explicit Vector(  
    const std::array<T, N>& a  
    );  
  
explicit Vector(  
    const Array<T>^ arr  
    );  
  
template <typename InIt> Vector(  
    InIt first,  
    InIt last  
    );  
  
Vector(  
    std::initializer_list<T> il  
    );  
```  
  
#### Parameter  
 a  
 Ein [std::array](../standard-library/array-class-stl.md), das verwendet wird, um den Vector zu initialisieren.  
  
 a  
 Ein [Platform::Array](../cppcx/platform-array-class.md), das verwendet wird, um den Vector zu initialisieren.  
  
 `InIt`  
 Der Typ einer Auflistung von Objekten, die verwendet werden, um den aktuelle Vector zu initialisieren.  
  
 il  
 Eine [std::initializer\_list](../standard-library/initializer-list-class.md) von Objekten des Typs `T`, die verwendet werden, um den Vektor zu initialisieren.  
  
 `N`  
 Die Anzahl von Elementen in einer Auflistung von Objekten, die verwendet wird, um den aktuellen Vector zu initialisieren.  
  
 `size`  
 Die Anzahl von Elementen im Vector.  
  
 `value`  
 Ein Wert, der verwendet wird, um die einzelnen Elemente im aktuellen Vector zu initialisieren.  
  
 `v`  
 Ein [Lvalues und Rvalues](../Topic/Lvalues%20and%20Rvalues%20\(Visual%20C++\).md) zu einem [::std::vector](../Topic/vector%20Class%201.md), der verwendet wird, um den aktuellen Vector zu initialisieren.  
  
 `ptr`  
 Zeiger zu `std::vector`, der verwendet wird, um den aktuellen Vector zu initialisieren.  
  
 `arr`  
 Ein [Platform::Array](../cppcx/platform-array-class.md)\-Objekt, das verwendet wird, um den aktuellen Vector zu initialisieren.  
  
 `a`  
 Ein [std::array](../Topic/vector%20Class%201.md)\-Objekt, das verwendet wird, um den aktuellen Vector zu initialisieren.  
  
 `first`  
 Das erste Element in einer Sequenz von Objekten, die verwendet werden, um den aktuellen Vector zu initialisieren. Der Typ von `first` wird mittels *perfekter Weiterleitung* übergeben. Weitere Informationen finden Sie unter [Rvalue\-Verweisdeklarator: &&](../Topic/Rvalue%20Reference%20Declarator:%20&&.md).  
  
 `last`  
 Das letzte Element in einer Sequenz von Objekten, die verwendet werden, um den aktuellen Vector zu initialisieren. Der Typ von `last` wird mittels *perfekter Weiterleitung* übergeben. Weitere Informationen finden Sie unter [Rvalue\-Verweisdeklarator: &&](../Topic/Rvalue%20Reference%20Declarator:%20&&.md).  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::Vector\-Klasse](../cppcx/platform-collections-vector-class.md)   
 [Auflistungen \(C\+\+\/CX\)](../cppcx/collections-c-cx.md)