---
title: "Platform::IBox-Schnittstelle | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IBox"
dev_langs: 
  - "C++"
ms.assetid: 774df45d-f8a7-45a3-ae24-eecc3c681040
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Platform::IBox-Schnittstelle
Die [Platform::IBox](../cppcx/platform-ibox-interface.md)\-Schnittstelle ist in C\+\+ der Name für die `Windows::Foundation::IReference`\-Schnittstelle.  
  
## Syntax  
  
```cpp  
template <typename T>  
interface class IBox  
```  
  
#### Parameter  
 `T`  
 Der Typ des geschachtelten Werts.  
  
## Hinweise  
 Die `IBox<T>`\-Schnittstelle wird hauptsächlich intern zur Darstellung von Werttypen verwendet, die NULL\-Werte zulassen, wie in [Wertklassen und Strukturen \(C\+\+\/CX\)](../cppcx/value-classes-and-structs-c-cx.md) beschrieben. Die Schnittstelle wird auch zum Schachteln von Werttypen verwendet, die an C\+\+\-Methoden übergeben werden, die Parameter des Typs `Object^` akzeptieren. Sie können einen Eingabeparameter explizit als `IBox<SomeValueType>` deklarieren. Ein Beispiel finden Sie unter [Boxing](../cppcx/boxing-c-cx.md).  
  
## Anforderungen  
  
## Member  
 Die `Platform::IBox`\-Schnittstelle erbt von der [Platform::IValueType](../cppcx/platform-ivaluetype-interface.md)\-Schnittstelle.`IBox` umfasst folgende Member:  
  
 **Eigenschaften**  
  
|Methode|Beschreibung|  
|-------------|------------------|  
|Wert|Gibt den nicht geschachtelten Wer zurück, der zuvor in dieser `IBox`\-Instanz gespeichert wurde.|  
  
## Siehe auch  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)