---
title: "Map::Insert-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::Insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map::Insert"
ms.assetid: 3acb2221-c12f-407a-a570-2e52df3569f6
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::Insert-Methode
Fügt das angegebene Schlüssel\-Wert\-Paar dem aktuellen Map\-Objekt hinzu.  
  
## Syntax  
  
```  
  
virtual bool Insert(  
   K key,   
   V value  
);  
```  
  
#### Parameter  
 `key`  
 Der Schlüsselteil des Schlüssel\-Wert\-Paars. Der Typ von `key` lautet Typname *K*.  
  
 `value`  
 Der Wertteil des Schlüssel\-Wert\-Paars. Der Typ von `value` lautet Typname *V*.  
  
## Rückgabewert  
 `true`, wenn der Schlüssel eines vorhandenen Elements in der aktuellen Map `key` entspricht und der Wertteil dieses Elements auf `value` festgelegt ist.`false`, wenn kein vorhandenes Element in der aktuellen Map `key` entspricht und die `key`\- und `value`\-Parameter zu einem Schlüssel\-Wert\-Paar gemacht und anschließend zur aktuellen Map hinzugefügt werden.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::Map\-Klasse](../cppcx/platform-collections-map-class.md)