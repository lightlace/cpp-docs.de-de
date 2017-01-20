---
title: "Aktivieren und Deaktivieren von Diensten f&#252;r einen Anbieter"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB-Dienste [OLE DB], Aktivieren und Deaktivieren"
  - "Serviceanbieter [OLE DB]"
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Aktivieren und Deaktivieren von Diensten f&#252;r einen Anbieter
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Einzelne OLE DB\-Dienste können standardmäßig für alle Anwendungen, die auf einen einzelnen Anbieter zugreifen, aktiviert oder deaktiviert werden.  Dazu wird unter der Anbieter\-CLSID ein **OLEDB\_SERVICES**\-Registrierungseintrag eingefügt, der einen `DWORD`\-Wert enthält, durch den die zu aktivierenden oder zu deaktivierenden Dienste angegeben werden, wie in der folgenden Tabelle dargestellt:  
  
|Aktivierte Standarddienste|Schlüsselwortwert|  
|--------------------------------|-----------------------|  
|Alle Dienste \(Standard\)|0xffffffff|  
|Alle Dienste außer Pooling und AutoEnlistment|0xfffffffe|  
|Alle Dienste außer Client Cursor|0xfffffffb|  
|Alle Dienste außer Pooling, AutoEnlistment und Client Cursor|0xfffffff0|  
|Keine Dienste|0x00000000|  
|Keine Aggregation, alle Dienste deaktiviert|\<fehlende Schlüssel\>|  
  
## Siehe auch  
 [Aktivieren und Deaktivieren von OLE DB\-Diensten](../../data/oledb/enabling-and-disabling-ole-db-services.md)