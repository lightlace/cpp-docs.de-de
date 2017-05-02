---
title: "UnorderedMapView::First-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView::First"
ms.assetid: 385f2a46-90ee-412b-817b-b5a0f2f57022
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMapView::First-Methode
Gibt einen Iterator zurück, der das erste [Windows::Foundation::Collections::IKeyValuePair \<K,V\>](http://msdn.microsoft.com/library/windows/apps/br226031.aspx)\-Element in der ungeordneten Zuordnung angibt.  
  
## Syntax  
  
```cpp  
  
virtual Windows::Foundation::Collections::IIterator<  
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^   
First();  
```  
  
## Rückgabewert  
 Ein Iterator, der das erste Element in der Kartenansicht angibt.  
  
## Hinweise  
 Eine einfache Möglichkeit, den von First\(\) zurückgegeben Iterator zu halten, ist, den Rückgabewert einer Variablen zuzuweisen, die mit dem [automatischen](../Topic/auto%20\(C++\).md) Typableitungsschlüsselwort deklariert wird. Beispielsweise `auto x = myMapView->First();`.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::UnorderedMapView\-Klasse](../cppcx/platform-collections-unorderedmapview-class.md)