---
title: "begin-Funktion | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Windows::Foundation::Collections::begin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "begin-Funktion"
ms.assetid: 5a44fb33-e247-49fd-b7a1-4a5b42e9e1e4
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# begin-Funktion
Gibt einen Iterator zurück, der an den Anfang einer Auflistung zeigt, auf die über den angegebenen Schnittstellenparameter zugegriffen wird.  
  
## Syntax  
  
```  
  
template <typename T>   
    ::Platform::Collections::VectorIterator<T>   
    begin(  
          IVector<T>^ v         );  
  
template <typename T>   
    ::Platform::Collections::VectorViewIterator<T>   
    begin(  
          IVectorView<T>^ v  
         );   
  
template <typename T>   
    ::Platform::Collections::InputIterator<T>   
    begin(  
          IIterable<T>^ i         );  
  
```  
  
#### Parameter  
 `T`  
 Ein Vorlagentyp\-Parameter.  
  
 `v`  
 Eine Auflistung von Vector\<T\>\- oder VectorView\<T\>\-Objekten, auf die durch eine IVector\<T\>\- oder IVectorView\<T\>\-Schnittstelle zugegriffen wird.  
  
 `i`  
 Eine Auflistung von beliebigen [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Objekten, auf die von einer IIterable\<T\>\-Schnittstelle zugegriffen wird.  
  
## Rückgabewert  
 Ein Iterator, der zum Anfang der Auflistung zeigt.  
  
## Hinweise  
 Die ersten beiden Vorlagenfunktionen geben Iteratoren zurück und die dritte Vorlagenfunktion gibt einen Eingabeiterator zurück.  
  
 Das VectorIterator\-Objekt, das vom Anfang zurückgegeben wird, ist ein Proxyiterator, der Elemente des Typs VectorProxy\<T\> speichert. Allerdings ist das Proxyobjekt fast nie für Benutzercode sichtbar. Weitere Informationen finden Sie unter [Auflistungen \(C\+\+\/CX\)](../cppcx/collections-c-cx.md).  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Windows::Foundation::Collections  
  
## Siehe auch  
 [Windows::Foundation::Collections\-Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)