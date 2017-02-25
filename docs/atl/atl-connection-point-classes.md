---
title: "ATL Connection Point Classes | Microsoft Docs"
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
  - "ATL, Verbindungspunkte"
  - "CComDynamicUnkArray class, connection point classes"
  - "CComUnkArray class, connection point classes"
  - "CFirePropNotifyEvent class"
  - "CFirePropNotifyEvent class, connection point classes"
  - "Verbindungspunkte [C++], ATL-Klassen"
ms.assetid: 9582ba71-7ace-4df4-9c9b-1b0636953efc
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ATL Connection Point Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL verwendet die folgenden Klassen, um Verbindungspunkte zu unterstützen:  
  
-   [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) implementiert einen Verbindungspunkt.  Das IID der Ausgangsschnittstelle, die es darstellt, wird als Vorlagenparameter übergeben.  
  
-   [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md) implementiert den Verbindungspunktcontainer und verwaltet die Liste der `IConnectionPointImpl`\-Objekten.  
  
-   [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) implementiert einen Verbindungspunkt, der die [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)\-Schnittstelle darstellt.  
  
-   [CComDynamicUnkArray](../atl/reference/ccomdynamicunkarray-class.md) verwaltet eine beliebige Anzahl von Verbindungen zwischen dem Verbindungspunkt und dessen Senken.  
  
-   [CComUnkArray](../atl/reference/ccomunkarray-class.md) verwaltet eine vordefinierte Anzahl von Verbindungen, wie durch den Vorlagenparameter angegeben.  
  
-   [CFirePropNotifyEvent](../atl/reference/cfirepropnotifyevent-class.md) benachrichtigt die Senke eines Clients, dass die Eigenschaft eines Objekts geändert hat oder ist im Begriff zu ändern.  
  
-   [IDispEventImpl](../atl/reference/idispeventimpl-class.md) bietet Unterstützung für Verbindungspunkte für ein ATL COM\-Objekt.  Diese Verbindungspunkte werden mit einer Ereignissenkenzuordnung zugeordnet, die von dem COM\-Objekt bereitgestellt wird.  
  
-   [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) funktioniert in Verbindung mit der Ereignissenkenzuordnung in der Klasse, um Ereignisse der entsprechenden Handlerfunktion weiterzuleiten.  
  
## Siehe auch  
 [Verbindungspunkt](../atl/atl-connection-points.md)