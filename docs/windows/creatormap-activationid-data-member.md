---
title: "CreatorMap::activationId-Datenmember | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::CreatorMap::activationId"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "activationId-Datenmember"
ms.assetid: 77518b76-6e6a-4b48-8e2e-a4c7c67769e0
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# CreatorMap::activationId-Datenmember
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
union {   
   const IID* clsid;  
   const wchar_t* (*getRuntimeName)();  
} activationId;  
```  
  
## Parameter  
 `clsid`  
 Eine Schnittstelle ID  
  
 `getRuntimeName`  
 Eine Funktion, die den Windows\-Ablaufnamen eines Objekts abgerufen.  
  
## Hinweise  
 Stellt eine Objekt\-ID dar, die entweder durch einer herkömmlichen COM\-Klassen\-ID oder einen Windows\-Ablaufnamen identifiziert wird.  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [CreatorMap\-Struktur](../windows/creatormap-structure.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)