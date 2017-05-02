---
title: "Box::Value-Eigenschaft | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::Value"
dev_langs: 
  - "C++"
ms.assetid: f456b105-6c14-4737-8c27-ad47d1eabd32
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Box::Value-Eigenschaft
Gibt den im `Box`\-Objekt gekapselten Wert zurück.  
  
## Syntax  
  
```cpp  
virtual property T Value{  
   T get();  
}  
```  
  
## Rückgabewert  
 Gibt den durch Boxing konvertierten Wert in dem Typ zurück, den er vor dem Boxing besaß.  
  
## Anforderungen  
 **Header:** vccorlib.h  
  
 **Namespace:** Platform  
  
## Siehe auch  
 [Platform::Box\-Klasse](../cppcx/platform-box-class.md)   
 [Boxing](../cppcx/boxing-c-cx.md)