---
title: "UnorderedMapView::HasKey-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView::HasKey"
ms.assetid: 4704da18-8606-4df7-be51-d125b2e4aee0
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMapView::HasKey-Methode
Ermittelt, ob die aktuelle ungeordnete Zuordnung den angegebenen Schlüssel enthält.  
  
## Syntax  
  
```cpp  
  
bool HasKey(  
   K key  
);  
```  
  
#### Parameter  
 `key`  
 Der zum Suchen des Elements verwendete Schlüssel. Der Typ von `key` lautet Typname *K*.  
  
## Rückgabewert  
 `true`, wenn der Schlüssel gefunden wurde, andernfalls `false`.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::UnorderedMap\-Klasse](../cppcx/platform-collections-unorderedmap-class.md)   
 [Auflistungen](../cppcx/collections-c-cx.md)   
 [Windows::Foundation::Collections::IKeyValuePair\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br226031.aspx)