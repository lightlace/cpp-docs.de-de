---
title: "WriteOnlyArray::end-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::WriteOnlyArray::end"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WriteOnlyArray::end-Methode"
ms.assetid: 045045fe-f210-400b-b688-7abb95fc702a
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WriteOnlyArray::end-Methode
Gibt einen Zeiger auf einen Punkt hinter dem letzten Element im Array zurück.  
  
## Syntax  
  
```cpp  
T* end() const;  
```  
  
## Rückgabewert  
 Ein Zeigeriterator auf einen Punkt hinter dem letzten Element im Array.  
  
## Hinweise  
 Dieser Iterator kann mit STL\-Algorithmen verwendet werden, um Vorgänge wie `std::sort` auf die Array\-Elemente auszuführen.  
  
## Anforderungen  
 **Header:** vccorlib.h  
  
 **Namespace:** Platform  
  
## Siehe auch  
 [Platform::WriteOnlyArray\-Klasse](../cppcx/platform-writeonlyarray-class.md)   
 [Array und WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)