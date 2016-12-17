---
title: "ComPtrRef::GetAddressOf-Methode"
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
  - "client/Microsoft::WRL::Details::ComPtrRef::GetAddressOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetAddressOf-Methode"
ms.assetid: 797df323-a2fa-412b-ab60-32cce3721096
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtrRef::GetAddressOf-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
InterfaceType* const * GetAddressOf() const;  
```  
  
## Rückgabewert  
 Adresse eines Zeigers zur Schnittstelle dargestellt durch das aktuelle ComPtrRef\-Objekt.  
  
## Hinweise  
 Ruft die Adresse eines Zeigers zur Schnittstelle ab, die durch das aktuelle ComPtrRef\-Objekt dargestellt wird.  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [ComPtrRef\-Klasse](../windows/comptrref-class.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)