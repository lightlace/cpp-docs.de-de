---
title: "Aktivieren und Deaktivieren von OLE&#160;DB-Diensten"
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
ms.assetid: 445f97eb-32a8-41c2-ad26-1169f78a074f
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Aktivieren und Deaktivieren von OLE&#160;DB-Diensten
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Komponenten\-Manager für OLE DB\-Dienste vergleicht die vom Consumer festgelegten Eigenschaften mit den vom Anbieter unterstützten Eigenschaften, um festzustellen, ob einzelne Dienstkomponenten aufgerufen werden können, um eine vom Consumer angeforderte, erweiterte Funktionalität bereitzustellen.  Wenn eine Anwendung beispielsweise einen bildlauffähigen Cursor anfordert, der Anbieter jedoch nur einen Vorwärtscursor unterstützt, ruft der Dienstkomponenten\-Manager die Client Cursor Engine\-Dienstkomponente auf, um Bildlauffähigkeit zu implementieren.  Wenn die Anwendung auf der vom Anbieterrowset standardmäßig unterstützten, erweiterten Funktionalität basiert und die Eigenschaften zum Anfordern dieser Funktionen von der Anwendung nicht explizit festgelegt wurden, sind diese Funktionen u. U. nicht in dem von der Client Cursor Engine zurückgegebenen Rowset enthalten.  Aus Gründen der Interoperabilität sollten Anwendungen immer Eigenschaften festlegen, durch die erweiterte Funktionen ggf. explizit angefordert werden können.  
  
 In einigen Fällen kann es erforderlich sein, einzelne OLE DB\-Dienste zu deaktivieren, um die erfolgreiche Kooperation zwischen vorhandenen Anwendungen, die Annahmen hinsichtlich der Merkmale eines Anbieters anstellen, zu gewährleisten.  OLE DB\-Dienste sind in der Lage, einzelne Dienste oder alle Dienste zu deaktivieren. Dies ist auf der Basis einzelner Verbindungen oder für alle Anwendungen möglich, die einen einzelnen Anbieter verwenden.  
  
## Siehe auch  
 [OLE DB\-Ressourcenpooling und \-Dienste](../../data/oledb/ole-db-resource-pooling-and-services.md)