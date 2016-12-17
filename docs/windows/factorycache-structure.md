---
title: "FactoryCache-Struktur"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::FactoryCache"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FactoryCache-Struktur"
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# FactoryCache-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die Infrastruktur von [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] und ist nicht für die direkte Verwendung im Code bestimmt.  
  
## Syntax  
  
```  
struct FactoryCache;  
```  
  
## Hinweise  
 Enthält den Speicherort einer Klassenfactorys und des Werts, der ein registriertes oder WRT COM\-Klassenobjekt identifiziert.  
  
## Member  
  
### Öffentliche Datenmember  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[FactoryCache::cookie\-Datenmember](../windows/factorycache-cookie-data-member.md)|Enthält einen Wert, der registrierten [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] oder COM\-Klassenobjekt identifiziert, und zum Aufheben der Registrierung ist das Objekt später verwendet.|  
|[FactoryCache::factory\-Datenmember](../windows/factorycache-factory-data-member.md)|Punkte auf [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] oder TO COM\-Klassenfactory.|  
  
## Vererbungshierarchie  
 `FactoryCache`  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)