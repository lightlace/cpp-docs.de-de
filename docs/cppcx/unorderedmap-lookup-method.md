---
title: "UnorderedMap::Lookup-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::Lookup"
ms.assetid: 6f9bb393-3791-423d-bfee-925e0531e1a5
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::Lookup-Methode
Ruft den Wert des Typs V ab, der dem angegebenen Schlüssel des Typs K zugeordnet ist.  
  
## Syntax  
  
```scr  
V Lookup(  
   K key  
);  
```  
  
#### Parameter  
 `key`  
 Der zum Suchen eines in der UnorderedMap vorhandenen Elements verwendete Schlüssel. Der Typ von `key` lautet Typname *K*.  
  
## Rückgabewert  
 Der Wert, der dem `key` zugeordnet ist. Der Typ des Rückgabewerts ist der Typname *V*.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Auflistungen](../cppcx/collections-c-cx.md)   
 [Platform::Collections::UnorderedMap\-Klasse](../cppcx/platform-collections-unorderedmap-class.md)