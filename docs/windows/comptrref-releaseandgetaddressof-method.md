---
title: "ComPtrRef::ReleaseAndGetAddressOf-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::Details::ComPtrRef::ReleaseAndGetAddressOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseAndGetAddressOf-Methode"
ms.assetid: 004aac42-e135-41ce-8d1d-4c5969d55004
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ComPtrRef::ReleaseAndGetAddressOf-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
InterfaceType** ReleaseAndGetAddressOf();  
```  
  
## Rückgabewert  
 Zeiger auf die Schnittstelle, der das gelöschte ComPtrRef\-Objekt dargestellt wird.  
  
## Hinweise  
 Löscht das aktuelle ComPtrRef\-Objekt und gibt ein Zeiger\-zu\-einZeiger zur Schnittstelle zurück, die vom ComPtrRef\-Objekt dargestellt wird.  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [ComPtrRef\-Klasse](../windows/comptrref-class.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)