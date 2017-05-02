---
title: "Map::First-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::First"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map::First-Methode"
ms.assetid: bb1a4458-ecc3-43b0-b808-1693f853ad82
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::First-Methode
Gibt einen Iterator zurück, der das erste Element in der Zuordnung angibt, oder `nullptr`, wenn die Zuordnung leer ist.  
  
## Syntax  
  
```  
  
virtual Windows::Foundation::Collections::IIterator<  
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();  
```  
  
## Rückgabewert  
 Ein Iterator, der das erste Element in der Zuordnung angibt.  
  
## Hinweise  
 Eine einfache Möglichkeit, den von First\(\) zurückgegeben Iterator zu halten, ist, den Rückgabewert einer Variablen zuzuweisen, die mit dem [automatischen](../Topic/auto%20\(C++\).md) Typableitungsschlüsselwort deklariert wird. Beispielsweise `auto x = myMap->First();`.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::Map\-Klasse](../cppcx/platform-collections-map-class.md)   
 [Auflistungen \(C\+\+\/CX\)](../cppcx/collections-c-cx.md)