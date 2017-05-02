---
title: "VectorView::First-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::First"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::First-Methode"
ms.assetid: 543a5c5b-8ce3-4be3-9fad-726928de7855
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::First-Methode
Gibt einen Iterator zurück, der das erste Element in der VectorView angibt.  
  
## Syntax  
  
```  
  
virtual Windows::Foundation::Collections::IIterator<T>^   
   First();  
```  
  
## Rückgabewert  
 Ein Iterator, der das erste Element in der VectorView angibt.  
  
## Hinweise  
 Eine einfache Möglichkeit, den von First\(\) zurückgegeben Iterator zu halten, ist, den Rückgabewert einer Variablen zuzuweisen, die mit dem [automatischen](~/cpp/auto-cpp.md) Typableitungsschlüsselwort deklariert wird. Beispielsweise `auto x = myVectorView->First();`.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [VectorView Class](http://msdn.microsoft.com/de-de/79697692-ae58-40e0-958f-cf1be6347994)