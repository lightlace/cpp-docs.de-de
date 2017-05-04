---
title: "Platform::AccessDeniedException-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::AccessDeniedException"
  - "Platform/Platform::AccessDeniedException::AccessDeniedException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::AccessDeniedException"
ms.assetid: 6ae2155b-7b16-4587-8d2d-da05eab4c7e9
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Platform::AccessDeniedException-Klasse
Wird ausgelöst, wenn der Zugriff auf eine Ressource oder eine Funktion verweigert wird.  
  
## Syntax  
  
```cpp  
public ref class AccessDeniedException : COMException,    IException,    IPrintable,   IEquatable  
```  
  
## Hinweise  
 Wenn Sie diese Ausnahme erreicht haben, stellen Sie sicher, dass Sie die entsprechende Funktion angefordert und die erforderlichen Deklarationen im Paketmanifest der App angegeben haben. Weitere Informationen finden Sie unter [Konfigurieren eines Windows 8.1\-App\-Pakets mit dem Manifest\-Designer](http://msdn.microsoft.com/library/24c58b7f-9c6d-41c3-b385-c1e8497d5b2d) sowie unter der Klasse [COMException](../cppcx/platform-comexception-class.md).  
  
## Anforderungen  
 **Unterstützter Client \(Mindestversion\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Mindestversion\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## Siehe auch  
 [Platform::COMException\-Klasse](../cppcx/platform-comexception-class.md)