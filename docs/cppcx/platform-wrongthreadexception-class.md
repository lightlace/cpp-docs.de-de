---
title: "Platform::WrongThreadException-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::WrongThreadException"
  - "Platform/Platform::WrongThreadException::WrongThreadException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::WrongThreadException"
ms.assetid: c193f97e-0392-4535-a4c4-0711e4e4a836
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Platform::WrongThreadException-Klasse
Wird ausgelöst, wenn ein Thread über einen Schnittstellenzeiger einen Aufruf für ein Proxyobjekt tätigt, das nicht zu dem Apartment des Threads gehört.  
  
## Syntax  
  
```cpp  
public ref class WrongThreadException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
## Hinweise  
 Weitere Informationen finden Sie unter [COMException](../cppcx/platform-comexception-class.md).  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## Siehe auch  
 [Platform::COMException\-Klasse](../cppcx/platform-comexception-class.md)