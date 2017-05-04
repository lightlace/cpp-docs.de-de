---
title: "Array-Konstruktoren | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::Array::Array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Array::Array"
ms.assetid: befb8088-3915-4b5c-b7fd-90f79961412d
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Array-Konstruktoren
Initialisiert ein eindimensionales, änderbares Array von Typen, die vom Klassenvorlagenparameter *T* angegeben werden.  
  
## Syntax  
  
```  
  
Array(unsigned int size);  
Array(T* data, unsigned int size);  
  
```  
  
#### Parameter  
 `T`  
 Klassenvorlagenparameter.  
  
 `size`  
 Die Anzahl der Elemente im Array.  
  
 `data`  
 Ein Zeiger auf ein Array von Daten des Typs `T`, der verwendet wird, um dieses Arrayobjekt zu initialisieren.  
  
## Hinweise  
 Weitere Informationen zum Erstellen von Platform::Array\-Instanzen finden Sie unter [Array und WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).  
  
## Anforderungen  
 **Header:** vccorlib.h  
  
 **Namespace:** Platform  
  
## Siehe auch  
 [Platform::Array\-Klasse](../cppcx/platform-array-class.md)