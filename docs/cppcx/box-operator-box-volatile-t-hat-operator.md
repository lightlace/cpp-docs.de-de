---
title: "Box::operator Box&lt;volatile T&gt;^ Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::operator Box<volatile T>^"
dev_langs: 
  - "C++"
ms.assetid: 90fffbf6-3429-46d0-bfaf-d99b7f48de6f
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Box::operator Box&lt;volatile T&gt;^ Operator
Ermöglicht Boxingkonvertierungen von einer `volatile`\-Wertklasse `T` oder einem `enum`\-Typ `T` in `Box<T>`.  
  
## Syntax  
  
```cpp  
operator Box<volatile T>^(volatile T valueType);  
```  
  
#### Parameter  
 `T`  
 Ein Enumerationstyp, eine Wertklasse oder eine Wertstruktur. Schließt die integrierten Typen im [Standardnamespace](../cppcx/default-namespace.md) ein.  
  
## Rückgabewert  
 Eine `Platform::Box<T>``^`\-Instanz, die den ursprünglichen Wert in einer Verweisklasse geschachtelt darstellt.  
  
## Anforderungen  
 **Header:** vccorlib.h  
  
 **Namespace:** Platform  
  
## Siehe auch  
 [Platform::Box\-Klasse](../cppcx/platform-box-class.md)   
 [Platform::IBox\-Schnittstelle](../cppcx/platform-ibox-interface.md)   
 [Boxing](../cppcx/boxing-c-cx.md)