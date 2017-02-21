---
title: "Connection Points Classes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.atl.connection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Klassen [C++], Verbindungspunkte"
  - "connection points classes"
ms.assetid: 076365fa-299a-4dce-84c3-a5dff0e0da1f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Connection Points Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Klassen bieten Unterstützung für Verbindungspunkte:  
  
-   [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md) implementiert einen Verbindungspunktcontainer.  
  
-   [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) implementiert einen Verbindungspunkt.  
  
-   [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) implementiert einen Verbindungspunkt, der die [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)\-Schnittstelle darstellt.  
  
-   [CComDynamicUnkArray](../atl/reference/ccomdynamicunkarray-class.md) verwaltet unbegrenzte Verbindungen zwischen einem Verbindungspunkt und dessen Senken.  
  
-   [CComUnkArray](../atl/reference/ccomunkarray-class.md) verwaltet eine feste Anzahl von Verbindungen zwischen einem Verbindungspunkt und dessen Senken.  
  
-   [CFirePropNotifyEvent](../atl/reference/cfirepropnotifyevent-class.md) benachrichtigt die Senke eines Clients, dass die Eigenschaft eines Objekts geändert hat oder ist im Begriff zu ändern.  
  
-   [IDispEventImpl](../atl/reference/idispeventimpl-class.md) bietet Unterstützung für Verbindungspunkte für ein ATL COM\-Objekt.  Diese Verbindungspunkte werden mit einer Ereignissenkenzuordnung zugeordnet, die von dem COM\-Objekt bereitgestellt wird.  
  
-   [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) funktioniert in Verbindung mit der Ereignissenkenzuordnung in der Klasse, um Ereignisse der entsprechenden Handlerfunktion weiterzuleiten.  
  
## Verwandte Elemente  
 [Verbindungspunkte](../atl/atl-connection-points.md)  
  
 [Ereignisbehandlung und ATL](../atl/event-handling-and-atl.md)  
  
## Siehe auch  
 [Class Overview](../atl/atl-class-overview.md)   
 [Connection Point Macros](../atl/reference/connection-point-macros.md)   
 [Connection Point Global Functions](../atl/reference/connection-point-global-functions.md)