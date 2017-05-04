---
title: "to_vector-Funktion | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Windows::Foundation::Collections::to_vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "to_vector-Funktion"
ms.assetid: 9cdd5123-7243-4def-a1d3-162e0bf6219e
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 3
---
# to_vector-Funktion
Gibt `std::vector` zurück, dessen Wert der Auflistung entspricht, die dem angegebenen IVector\- oder IVectorView\-Parameter zugrunde liegt.  
  
## Syntax  
  
```  
template <  
   typename T  
>  
inline ::std::vector<T> to_vector(  
   IVector<T>^ v  
);  
template <  
   typename T  
>  
inline ::std::vector<T> to_vector(  
   IVectorView<T>^ v  
);  
```  
  
#### Parameter  
 `T`  
 Der Vorlagentyp\-Parameter.  
  
 `v`  
 Eine IVector\- oder IVectorView\-Schnittstelle, die Zugriff auf ein zugrunde liegendes Vektor\- oder VectorView\-Objekt bietet.  
  
## Rückgabewert  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Windows::Foundation::Collections  
  
## Siehe auch  
 [Windows::Foundation::Collections\-Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)