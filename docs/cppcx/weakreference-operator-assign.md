---
title: "WeakReference::operator= | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/WeakReference::operator="
ms.assetid: 20b034d1-8f4f-46ae-81f0-73b76599f86b
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WeakReference::operator=
Weist einem schwachen Verweis einen Wert zu.  
  
## Syntax  
  
```cpp  
WeakReference& operator=(decltype(__nullptr));  
  
WeakReference& operator=(const WeakReference& __otherArg);  
  
WeakReference& operator=(WeakReference&& __otherArg);  
  
WeakReference& operator=(const volatile ::Platform::Object^ const __otherArg);  
  
```  
  
## Hinweise  
 Die letzte Überladung in der Liste oben ermöglicht es Ihnen, einer WeakReference\-Variable eine Verweisklasse zuzuweisen. In diesem Fall wird die Verweisklasse in [Platform::Object](../cppcx/platform-object-class.md)^ umgewandelt. Sie stellen den ursprünglichen Typ später wieder her, indem Sie ihn als das Argument für den Typparameter in der Memberfunktion [WeakReference::Resolve\<T\>](../cppcx/weakreference-resolve-method-platform-namespace.md) angeben.  
  
## Anforderungen  
 Windows 8.0 oder höher  
  
## Siehe auch  
 [Platform::WeakReference\-Klasse](../cppcx/platform-weakreference-class.md)