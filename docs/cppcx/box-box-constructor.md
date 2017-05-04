---
title: "Box::Box-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::Box"
dev_langs: 
  - "C++"
ms.assetid: 3c4777f0-801c-4b24-9426-6d658dfaecf8
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Box::Box-Konstruktor
Erstellt eine `Box`, die einen Wert vom angegebenen Typ kapseln kann.  
  
## Syntax  
  
```cpp  
Box(T valueArg);  
```  
  
#### Parameter  
 `valueArg`  
 Der Typ des Werts, für den eine Boxingkonvertierung ausgeführt werden soll – beispielsweise `int`, `bool`, `float64`, `DateTime`.  
  
## Anforderungen  
 **Header:** vccorlib.h  
  
 **Namespace:** Platform  
  
## Siehe auch  
 [Platform::Box\-Klasse](../cppcx/platform-box-class.md)   
 [Boxing](../cppcx/boxing-c-cx.md)