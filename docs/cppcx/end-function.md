---
title: "end-Funktion | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Windows::Foundation::Collections::end"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "end-Funktion"
ms.assetid: fb837bff-fc76-4bae-9096-facf0e03041c
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# end-Funktion
Gibt einen Iterator zurück, der über das Ende einer Auflistung hinaus zeigt, auf die über den angegebenen Schnittstellenparameter zugegriffen wird.  
  
## Syntax  
  
```  
  
template <typename T>  
    ::Platform::Collections::VectorIterator<T>   
    end(  
        IVector<T>^ v       );  
  
template <typename T>  
    ::Platform::Collections::VectorViewIterator<T>   
    end(  
        IVectorView<T>^ v  
       );  
template <typename T>   
    ::Platform::Collections::InputIterator<T>   
    end(  
        IIterable<T>^ i  
       );  
  
```  
  
#### Parameter  
 `T`  
 Ein Vorlagentyp\-Parameter.  
  
 `v`  
 Eine Auflistung von Vektor\<T\>\- oder VectorView\<T\>\-Objekten, auf die durch eine IVector\<T\>\- oder IVectorView\<T\>\-Schnittstelle zugegriffen wird.  
  
 `i`  
 Eine Auflistung von beliebigen [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Objekten, auf die von einer IIterable\<T\>\-Schnittstelle zugegriffen wird.  
  
## Rückgabewert  
 Ein Iterator, der über das Ende der Auflistung hinaus zeigt.  
  
## Hinweise  
 Die ersten beiden Vorlagenfunktionen geben Iteratoren zurück und die dritte Vorlagenfunktion gibt einen Eingabeiterator zurück.  
  
 Das Objekt [Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md), das von `end` zurückgegeben wird, ist ein Proxyiterator, der Elemente des Typs `VectorProxy<T>` speichert. Allerdings ist das Proxyobjekt fast nie für Benutzercode sichtbar. Weitere Informationen finden Sie unter [Auflistungen \(C\+\+\/CX\)](../cppcx/collections-c-cx.md).  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Windows::Foundation::Collections  
  
## Siehe auch  
 [Windows::Foundation::Collections\-Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)