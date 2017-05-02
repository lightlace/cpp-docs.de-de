---
title: "Vector::First-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::First"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::First-Methode"
ms.assetid: ca6b7b55-dd49-4346-bfa4-d8010b228d44
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::First-Methode
Gibt einen Iterator zurück, der auf das erste Element im Vektor verweist.  
  
## Syntax  
  
```  
  
virtual Windows::Foundation::Collections::IIterator <T>^   
   First();  
```  
  
## Rückgabewert  
 Ein Iterator, der auf das erste Element im Vektor verweist.  
  
## Hinweise  
 Eine einfache Möglichkeit, den von First\(\) zurückgegeben Iterator zu halten, ist, den Rückgabewert einer Variablen zuzuweisen, die mit dem [automatischen](../Topic/auto%20\(C++\).md) Typableitungsschlüsselwort deklariert wird. Beispielsweise `auto x = myVector->First();`. Dieser Iterator kennt die Länge der Auflistung.  
  
 Wenn Sie ein Paar von Iteratoren zur Übergabe an eine STL\-Funktion benötigen, verwenden Sie die free\-Funktionen [Windows::Foundation::Collections::begin](../cppcx/begin-function.md) und [Windows::Foundation::Collections::end](../cppcx/end-function.md)  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::Vector\-Klasse](../cppcx/platform-collections-vector-class.md)   
 [Auflistungen](../cppcx/collections-c-cx.md)