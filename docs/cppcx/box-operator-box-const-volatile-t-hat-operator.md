---
title: "Box::operator Box&lt;const volatile T&gt;^-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::operator Box<const volatile T>^"
dev_langs: 
  - "C++"
ms.assetid: 3c91cf0f-1e90-4daf-8468-a7d8aedb6784
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Box::operator Box&lt;const volatile T&gt;^-Operator
Ermöglicht Boxingkonvertierungen von einer `const volatile`\-Wertklasse `T` oder einem `enum`\-Typ `T` in `Box<T>`.  
  
## Syntax  
  
```cpp  
operator Box<const volatile T>^(const volatile T valueType);  
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