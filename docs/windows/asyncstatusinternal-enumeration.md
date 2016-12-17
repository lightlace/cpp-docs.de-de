---
title: "AsyncStatusInternal-Enumeration"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::Details::AsyncStatusInternal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsyncStatusInternal-Enumeration"
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# AsyncStatusInternal-Enumeration
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
enum AsyncStatusInternal;  
```  
  
## Hinweise  
 Gibt eine Zuordnung zwischen internen Enumerationen für den Zustand von asynchronen Vorgängen und Enumeration der **Windows::Foundation::AsyncStatus** an.  
  
## Member  
 `_Created`  
 Entspricht ::Windows::Foundation::AsyncStatus::Created  
  
 `_Started`  
 Entspricht ::Windows::Foundation::AsyncStatus::Started  
  
 `_Completed`  
 Entspricht ::Windows::Foundation::AsyncStatus::Completed  
  
 `_Cancelled`  
 Entspricht ::Windows::Foundation::AsyncStatus::Cancelled  
  
 `_Error`  
 Entsprechung zum ::Windows::Foundation::AsyncStatus::Error  
  
## Anforderungen  
 **Header:**  async.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)