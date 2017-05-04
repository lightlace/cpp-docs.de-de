---
title: "WriteOnlyArray::begin-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::WriteOnlyArray::begin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WriteOnlyArray::begin-Methode"
ms.assetid: 25025fa0-8f55-4abf-93ad-71db45ddfae3
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WriteOnlyArray::begin-Methode
Gibt einen Zeiger auf das erste Element im Array zurück.  
  
## Syntax  
  
```cpp  
T* begin() const;  
```  
  
## Rückgabewert  
 Ein Zeiger auf das erste Element im Array.  
  
## Hinweise  
 Dieser Iterator kann mit STL\-Algorithmen wie `std::sort` verwendet werden, um Vorgänge auf Elemente im Array auszuführen.  
  
## Anforderungen  
 **Header:** vccorlib.h  
  
 **Namespace:** Platform  
  
## Siehe auch  
 [Platform::WriteOnlyArray\-Klasse](../cppcx/platform-writeonlyarray-class.md)   
 [Array und WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)