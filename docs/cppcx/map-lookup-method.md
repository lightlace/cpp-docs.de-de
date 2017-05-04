---
title: "Map::Lookup-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::Lookup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map::Lookup-Methode"
ms.assetid: c56773ae-2df0-4d21-a6ab-9603529547b0
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::Lookup-Methode
Ruft den Wert des Typs V ab, der mit dem angegebenen Schlüssel des Typs K verknüpft ist, sofern der Schlüssel vorhanden ist.  
  
## Syntax  
  
```  
V Lookup(  
   K key  
);  
```  
  
#### Parameter  
 `key`  
 Der zum Suchen eines in der Zuordnung vorhandenen Elements verwendete Schlüssel. Der Typ von `key` lautet Typname *K*.  
  
## Rückgabewert  
 Der Wert, der dem `key` zugeordnet ist. Der Typ des Rückgabewerts ist der Typname *V*.  
  
## Hinweise  
 Wenn der Schlüssel nicht vorhanden ist, wird eine [Platform::OutOfBoundsException](../cppcx/platform-outofboundsexception-class.md) ausgelöst.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::Map\-Klasse](../cppcx/platform-collections-map-class.md)   
 [Auflistungen \(C\+\+\/CX\)](../cppcx/collections-c-cx.md)