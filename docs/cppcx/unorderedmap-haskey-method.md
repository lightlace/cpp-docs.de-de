---
title: "UnorderedMap::HasKey-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::HasKey"
ms.assetid: 7c397cdc-82f6-470a-8a3c-f5ba2cc58ed6
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::HasKey-Methode
Ermittelt, ob die aktuelle ungeordnete Zuordnung den angegebenen Schlüssel enthält.  
  
## Syntax  
  
```scr  
  
bool HasKey(  
   K key  
);  
```  
  
#### Parameter  
 `key`  
 Der zum Suchen des UnorderedMap\-Elements verwendete Schlüssel. Der Typ von `key` lautet Typname *K*.  
  
## Rückgabewert  
 `true`, wenn der Schlüssel gefunden wurde, andernfalls `false`.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::UnorderedMap\-Klasse](../cppcx/platform-collections-unorderedmap-class.md)   
 [Auflistungen](../cppcx/collections-c-cx.md)   
 [Windows::Foundation::Collections::IKeyValuePair\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br226031.aspx)