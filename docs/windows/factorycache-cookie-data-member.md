---
title: "FactoryCache::cookie-Datenmember | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::FactoryCache::cookie"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cookie-Datenmember"
ms.assetid: b1bc79af-a896-4e3b-8afa-64733022eddf
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# FactoryCache::cookie-Datenmember
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die Infrastruktur von [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] und ist nicht für die direkte Verwendung im Code bestimmt.  
  
## Syntax  
  
```  
union {   
   WINRT_REGISTRATION_COOKIE winrt;  
   DWORD com;   
} cookie;  
```  
  
## Hinweise  
 Enthält einen Wert, der registrierten [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] oder COM\-Klassenobjekt identifiziert, und zum Aufheben der Registrierung ist das Objekt später verwendet.  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [FactoryCache\-Struktur](../windows/factorycache-structure.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)