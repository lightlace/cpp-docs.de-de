---
title: "Array::get-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::Array::get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Array::get-Methode"
ms.assetid: 3bbcd829-35e7-4912-99ba-6ab9de407287
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Array::get-Methode
Ruft einen Verweis auf das Arrayelement an der angegebenen Indexposition ab.  
  
## Syntax  
  
```  
  
T& get(  
unsigned int index  
)  const;  
```  
  
#### Parameter  
 `index`  
 Ein nullbasierter Index, der ein Element im Array identifiziert. Der minimale Index ist 0 und der maximale Index ist der Wert, der vom `size`\-Parameter im [Arraykonstruktor](../cppcx/array-constructors.md) angegeben wird.  
  
## Rückgabewert  
 Das durch den `index`\-Parameter spezifizierte Arrayelement.  
  
## Anforderungen  
 **Header:** vccorlib.h  
  
 **Namespace:** Platform  
  
## Siehe auch  
 [Platform::Array\-Klasse](../cppcx/platform-array-class.md)