---
title: "WriteOnlyArray::set-Funktion | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::WriteOnlyArray::set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WriteOnlyArray::set-Funktion"
ms.assetid: 0359f922-f25e-47d1-b7df-87e7fd0f76e5
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WriteOnlyArray::set-Funktion
Legt den angegebenen Wert am angegebenen Index im Array fest.  
  
## Syntax  
  
```cpp  
T& set(  
   unsigned int indexArg,  
   T valueArg);  
```  
  
#### Parameter  
 `indexArg`  
 Der Index des festzulegenden Elements.  
  
 `valueArg`  
 Der bei `indexArg` festzulegende Wert.  
  
## Rückgabewert  
 Ein Verweis auf das Element, das gerade festgelegt wurde.  
  
## Anforderungen  
 **Header:** vccorlib.h  
  
 **Namespace:** Platform  
  
## Siehe auch  
 [Platform::WriteOnlyArray\-Klasse](../cppcx/platform-writeonlyarray-class.md)   
 [Array und WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)