---
title: "MapView::Lookup-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView::Lookup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MapView::Lookup-Methode"
ms.assetid: 93090ac3-3f1d-4b7e-b80e-164b8c65cd29
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# MapView::Lookup-Methode
Ruft den Wert des Typs V ab, der dem angegebenen Schlüssel des Typs K zugeordnet ist.  
  
## Syntax  
  
```  
V Lookup(  
   K key  
);  
```  
  
#### Parameter  
 `key`  
 Der zum Suchen eines in der MapView vorhandenen Elements verwendete Schlüssel. Der Typ von `key` lautet Typname *K*.  
  
## Rückgabewert  
 Der Wert, der dem `key` zugeordnet ist. Der Typ des Rückgabewerts ist der Typname *V*.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::MapView\-Klasse](../cppcx/platform-collections-mapview-class.md)