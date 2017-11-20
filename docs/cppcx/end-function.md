---
title: End-Funktion | Microsoft Docs
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: collection/Windows::Foundation::Collections::end
dev_langs: C++
helpviewer_keywords: end Function
ms.assetid: fb837bff-fc76-4bae-9096-facf0e03041c
caps.latest.revision: "4"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: f4030728c296a6dd234b6ad181d83ef072b06dd9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="end-function"></a>end-Funktion
Gibt einen Iterator zurück, der über das Ende einer Auflistung hinaus zeigt, auf die über den angegebenen Schnittstellenparameter zugegriffen wird.  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Ein Vorlagentyp-Parameter.  
  
 `v`  
 Eine Auflistung von Vektor\<T >- oder VectorView\<T >-Objekten, die durch eine IVector zugegriffen werden\<T >, oder IVectorView\<T >-Schnittstelle.  
  
 `i`  
 Eine Auflistung von beliebigen Windows-Runtime-Objekten, die von einer IIterable zugegriffen\<T >-Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der über das Ende der Auflistung hinaus zeigt.  
  
### <a name="remarks"></a>Hinweise  
 Die ersten beiden Vorlagenfunktionen geben Iteratoren zurück und die dritte Vorlagenfunktion gibt einen Eingabeiterator zurück.  
  
 Das Objekt [Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md) , das von `end` zurückgegeben wird, ist ein Proxyiterator, der Elemente des Typs `VectorProxy<T>`speichert. Allerdings ist das Proxyobjekt fast nie für Benutzercode sichtbar. Weitere Informationen finden Sie unter [Auflistungen (C++/CX)](../cppcx/collections-c-cx.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Windows::Foundation::Collections  
  
## <a name="see-also"></a>Siehe auch  
 [Collections-Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)