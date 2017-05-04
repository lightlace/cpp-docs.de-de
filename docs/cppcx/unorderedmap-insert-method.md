---
title: "UnorderedMap::Insert-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::Insert"
ms.assetid: 89d55301-3cad-4877-825b-35096a1dd740
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::Insert-Methode
Fügt das angegebene Schlüssel\-Wert\-Paar dem aktuellen UnorderedMap\-Objekt hinzu.  
  
## Syntax  
  
```cpp  
  
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
 `true`, wenn der Schlüssel eines vorhandenen Elements in der aktuellen Map `key` entspricht und der Wertteil dieses Elements auf `value` festgelegt ist.`false`, wenn kein vorhandenes Element in der aktuellen Zuordnung `key` entspricht und die `key`\- und `value`\-Parameter zu einem Schlüssel\-Wert\-Paar gemacht und anschließend zur aktuellen ungeordneten Zuordnung hinzugefügt werden.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections