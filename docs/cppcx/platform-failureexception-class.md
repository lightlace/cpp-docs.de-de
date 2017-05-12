---
title: "Platform::FailureException-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::FailureException::FailureException"
  - "Platform/Platform::FailureException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::FailureException"
ms.assetid: 1729cd07-bfc2-448e-9db5-185d5cbf5b81
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 3
---
# Platform::FailureException-Klasse
Wird ausgelöst, wenn bei dem Vorgang ein Fehler aufgetreten ist. Dies entspricht dem E\_FAIL HRESULT.  
  
## Syntax  
  
```cpp  
public ref class FailureException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
## Hinweise  
 Weitere Informationen finden Sie unter der [COMException](../cppcx/platform-comexception-class.md)\-Klasse.  
  
## Anforderungen  
 **Unterstützter Client \(Mindestversion\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Mindestversion\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## Siehe auch  
 [Platform::COMException\-Klasse](../cppcx/platform-comexception-class.md)