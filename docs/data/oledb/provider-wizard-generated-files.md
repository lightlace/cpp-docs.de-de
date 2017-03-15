---
title: "Vom Anbieter-Assistenten generierte Dateien | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB-Anbieter, Assistentengenerierte Dateien"
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Vom Anbieter-Assistenten generierte Dateien
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der ATL\-OLE DB\-Anbieter\-Assistent generiert die folgenden Dateien.  In den folgenden Themen wird der kurze Name "MyProvider" verwendet, die exakten Dateinamen hängen jedoch von den Optionen ab, die beim Erstellen des Anbieters ausgewählt wurden.  
  
|Dateiname|**Beschreibung**|  
|---------------|----------------------|  
|MyProviderRS.cpp|Enthält die `Execute`\-Befehlshilfsmethode und die Anbieterspaltenzuordnung.|  
|MyProviderDS.h|Implementiert das Datenquellenobjekt.  Diese Headerdatei enthält die Eigenschaftenzuordnung für Datenquelleneigenschaften.|  
|MyProviderRS.h|Implementiert das Befehls\- und das Rowsetobjekt.  Diese Headerdatei enthält die Eigenschaftenzuordnung für Rowset\- und Befehlseigenschaften.|  
|MyProviderSess.h|Implementiert das Sitzungsobjekt.  Diese Headerdatei enthält die Eigenschaftenzuordnung für Sitzungseigenschaften.|  
|MyProvider.rgs|Enthält die registrierten Objekte, die vom OLE DB\-Anbieter\-Assistenten generiert wurden.|  
  
## Siehe auch  
 [Erstellen eines OLE DB\-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)