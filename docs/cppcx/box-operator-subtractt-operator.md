---
title: "Box::operator T-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::operator T"
dev_langs: 
  - "C++"
ms.assetid: 7445ef5b-563c-4ff0-829d-f22aa558b5ec
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Box::operator T-Operator
Ermöglicht Boxingkonvertierungen von einer `T`\-Wertklasse oder `enum`\-Klasse `T` in `Box<T>`.  
  
## Syntax  
  
```cpp  
operator Box<T>^(T valueType);  
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