---
title: "UnorderedMap::First-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::First"
ms.assetid: 915e771a-cec1-4905-8ecb-76501f63c143
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::First-Methode
Gibt einen Iterator zurück, der das erste [Windows::Foundation::Collections::IKeyValuePair\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br226031.aspx)\-Element in der ungeordneten Zuordnung angibt.  
  
## Syntax  
  
```cpp  
  
virtual Windows::Foundation::Collections::IIterator<  
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();  
```  
  
## Rückgabewert  
 Ein Iterator, der das erste Element in der Zuordnung angibt.  
  
## Hinweise  
 Eine einfache Möglichkeit, den von First\(\) zurückgegeben Iterator zu halten, ist, den Rückgabewert einer Variablen zuzuweisen, die mit dem [automatischen](~/cpp/auto-cpp.md) Typableitungsschlüsselwort deklariert wird. Beispielsweise `auto x = myUnorderedMap->First();`.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::UnorderedMap\-Klasse](../cppcx/platform-collections-unorderedmap-class.md)   
 [Auflistungen](../cppcx/collections-c-cx.md)