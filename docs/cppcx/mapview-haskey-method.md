---
title: "MapView::HasKey-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView::HasKey"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MapView::HasKey-Methode"
ms.assetid: c1a24f63-e6fd-4cfd-90ce-b89352b98324
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# MapView::HasKey-Methode
Ermittelt, ob die aktuelle MapView den angegebenen Schlüssel enthält.  
  
## Syntax  
  
```  
  
bool HasKey(  
   K key  
);  
```  
  
#### Parameter  
 `key`  
 Der zum Suchen des MapView\-Elements verwendete Schlüssel. Der Typ von `key` lautet Typname *K*.  
  
## Rückgabewert  
 `true`, wenn der Schlüssel gefunden wurde, andernfalls `false`.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::MapView\-Klasse](../cppcx/platform-collections-mapview-class.md)