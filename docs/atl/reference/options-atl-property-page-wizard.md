---
title: "Optionen, ATL-Eigenschaftenseiten-Assistent | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.ppg.options"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Eigenschaftenseiten-Assistent, Optionen"
ms.assetid: a7107779-b2ea-4f99-b84b-7f3e0c504bc8
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Optionen, ATL-Eigenschaftenseiten-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Auf dieser Seite des Assistenten können Sie das Threadmodell und die Aggregationsebene der zu erstellenden Eigenschaftenseite definieren.  
  
 **Threadmodell**  
 Legt das von der Eigenschaftenseite verwendete Threadmodell fest.  
  
 Weitere Informationen finden Sie unter [Festlegen des Threadingmodells des Projekts](../../atl/specifying-the-threading-model-for-a-project-atl.md).  
  
|Option|Description|  
|------------|-----------------|  
|`Single`|Die Eigenschaftenseite wird nur im primären COM\-Thread ausgeführt.|  
|**Apartment**|Die Eigenschaftenseite kann in jedem beliebigen Singlethreadapartment erstellt werden.  Der Standardwert.|  
  
 **Aggregation**  
 Fügt der erstellten Eigenschaftenseite Aggregationsunterstützung hinzu.  Weitere Informationen finden Sie unter [Aggregation](../../atl/aggregation.md).  
  
|Option|Description|  
|------------|-----------------|  
|**Ja**|Erstellt eine Eigenschaftenseite, die aggregiert werden kann.|  
|**Nein**|Erstellt eine Eigenschaftenseite, die nicht aggregiert werden kann.|  
|**Nur**|Erstellt eine Eigenschaftenseite, die nur durch die Aggregation instanziiert werden kann.|  
  
## Siehe auch  
 [ATL\-Eigenschaftenseiten\-Assistent](../../atl/reference/atl-property-page-wizard.md)   
 [Zeichenfolgen, ATL\-Eigenschaftenseiten\-Assistent](../../atl/reference/strings-atl-property-page-wizard.md)