---
title: "CreatorMap-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::CreatorMap"
  - "implements/Microsoft::WRL::Details::CreatorMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreatorMap-Struktur"
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# CreatorMap-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die Infrastruktur von [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] und ist nicht für die direkte Verwendung im Code bestimmt.  
  
## Syntax  
  
```  
struct CreatorMap;  
```  
  
## Hinweise  
 Enthält Informationen dazu, wie und Registrierung Objekte initialisiert, registriert.  
  
 CreatorMap enthält folgende Informationen:  
  
-   Wie und Registrierung Objekte initialisiert, registriert.  
  
-   Erstellen Aktivierungsdaten abhängig von einer klassischen COM\- oder [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] vergleicht Factory.  
  
-   Informationen zum Factorycache und Servername für eine Schnittstelle.  
  
## Member  
  
### Öffentliche Datenmember  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[CreatorMap::activationId\-Datenmember](../windows/creatormap-activationid-data-member.md)|Stellt eine Objekt\-ID dar, die entweder durch einer herkömmlichen COM\-Klassen\-ID oder einen [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] Namen identifiziert wird.|  
|[CreatorMap::factoryCache\-Datenmember](../windows/creatormap-factorycache-data-member.md)|Speichert den Zeiger auf Factorycache für das CreatorMap.|  
|[CreatorMap::factoryCreator\-Datenmember](../windows/creatormap-factorycreator-data-member.md)|Stellt eine Factory für das angegebene CreatorMap erstellt.|  
|[CreatorMap::serverName\-Datenmember](../windows/creatormap-servername-data-member.md)|Speichert den Servernamen zum CreatorMap.|  
  
## Vererbungshierarchie  
 `CreatorMap`  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)