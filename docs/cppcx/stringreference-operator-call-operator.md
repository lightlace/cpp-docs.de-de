---
title: "StringReference::operator()-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::StringReference::operator()"
dev_langs: 
  - "C++"
ms.assetid: d5c65e82-300c-44aa-b826-0afe1e3645b1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# StringReference::operator()-Operator
Konvertiert ein `StringReference`\-Objekt in ein `Platform::String^`\-Objekt.  
  
## Syntax  
  
```cpp  
  
__declspec(no_release_return) __declspec(no_refcount)  
         operator ::Platform::String^() const  
  
```  
  
## Rückgabewert  
 Ein Handle für ein Objekt des Typs `Platform::String`  
  
## Hinweise  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Header:** vccorlib.h  
  
## Siehe auch  
 [Platform::StringReference\-Klasse](../cppcx/platform-stringreference-class.md)