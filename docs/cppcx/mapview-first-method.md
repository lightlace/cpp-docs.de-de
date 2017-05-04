---
title: "MapView::First-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView::First"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MapView::First-Methode"
ms.assetid: 9d7c7328-4f55-4ea6-a375-9d4e73707b56
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# MapView::First-Methode
Gibt einen Iterator zurück, der das erste Element in der Kartenansicht angibt.  
  
## Syntax  
  
```  
  
virtual Windows::Foundation::Collections::IIterator<  
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^   
First();  
```  
  
## Rückgabewert  
 Ein Iterator, der das erste Element in der Kartenansicht angibt.  
  
## Hinweise  
 Eine einfache Möglichkeit, den von First\(\) zurückgegeben Iterator zu halten, ist, den Rückgabewert einer Variablen zuzuweisen, die mit dem [automatischen](~/cpp/auto-cpp.md) Typableitungsschlüsselwort deklariert wird. Beispielsweise `auto x = myMapView->First();`.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::MapView\-Klasse](../cppcx/platform-collections-mapview-class.md)