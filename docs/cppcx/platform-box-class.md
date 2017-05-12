---
title: "Platform::Box-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box"
dev_langs: 
  - "C++"
ms.assetid: b3d7ea37-e98a-4fbc-80b0-ad35e50250c6
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Platform::Box-Klasse
Aktiviert einen Werttyp wie `Windows::Foundation::DateTime` oder einen skalaren Typ wie `int`, der in einem `Platform::Object`\-Typ gespeichert wird. Es ist normalerweise nicht erforderlich, `Box` explizit zu verwenden, da das Boxing implizit geschieht, wenn Sie einen Werttyp in `Object^` umwandeln.  
  
## Syntax  
  
```cpp  
ref class Box abstract;  
```  
  
## Hinweise  
  
## Anforderungen  
 **Header:** vccorlib.h  
  
 **Namespace:** Platform  
  
## Siehe auch  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)   
 [Boxing](../cppcx/boxing-c-cx.md)