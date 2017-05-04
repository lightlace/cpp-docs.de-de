---
title: "Box::operator Box&lt;const T&gt;^ Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::operator Box<const T>^"
dev_langs: 
  - "C++"
ms.assetid: c43a2e8f-7e9d-4587-960f-1bab48923f82
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Box::operator Box&lt;const T&gt;^ Operator
Ermöglicht Boxingkonvertierungen von einer `const`\-Wertklasse `T` oder `enum`\-Klasse `T` in `Box<T>`.  
  
## Syntax  
  
```cpp  
operator Box<const T>^(const T valueType);  
```  
  
#### Parameter  
 `T`  
 Eine Wertklasse, eine Wertstruktur oder ein Enumerationstyp. Schließt die integrierten Typen im [Standardnamespace](../cppcx/default-namespace.md) ein.  
  
## Rückgabewert  
 Eine `Platform::Box<T>``^`\-Instanz, die den ursprünglichen Wert in einer Verweisklasse geschachtelt darstellt.  
  
## Anforderungen  
 **Header:** vccorlib.h  
  
 **Namespace:** Platform  
  
## Siehe auch  
 [Platform::Box\-Klasse](../cppcx/platform-box-class.md)   
 [Platform::IBox\-Schnittstelle](../cppcx/platform-ibox-interface.md)