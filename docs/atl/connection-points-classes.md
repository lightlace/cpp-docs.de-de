---
title: Punkte Verbindungsklassen (ATL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.connection
dev_langs:
- C++
helpviewer_keywords:
- classes [C++], connection points
- connection points classes
ms.assetid: 076365fa-299a-4dce-84c3-a5dff0e0da1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6d458fb5805b99c8dcc5cc25abc9f85f88f08e92
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957651"
---
# <a name="connection-points-classes"></a>Verbindungspunkteklassen
Die folgenden Klassen bieten Unterstützung für Verbindungspunkte an:  
  
-   [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md) eine Verbindungspunktcontainer implementiert.  
  
-   [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) implementiert einen Verbindungspunkt.  
  
-   [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) implementiert ein Connection Point, die [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) Schnittstelle.  
  
-   [CComDynamicUnkArray](../atl/reference/ccomdynamicunkarray-class.md) verwaltet unbegrenzte Verbindungen zwischen einem Verbindungspunkt und die senken.  
  
-   [CComUnkArray](../atl/reference/ccomunkarray-class.md) verwaltet eine feste Anzahl von Verbindungen zwischen einem Verbindungspunkt und die senken.  
  
-   [CFirePropNotifyEvent](../atl/reference/cfirepropnotifyevent-class.md) benachrichtigt der Senke eines Clients, die die Eigenschaft eines Objekts geändert hat oder zu ändern.  
  
-   [IDispEventImpl](../atl/reference/idispeventimpl-class.md) bietet Unterstützung für die Verbindungspunkte für ein ATL-COM-Objekt. Mit einer Ereignis-Senke-Karte, die von COM-Objekts bereitgestellt wird, werden diese Verbindungspunkte zugeordnet.  
  
-   [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) funktioniert in Verbindung mit die Ereignissenke zugeordnet, in der Klasse zum Weiterleiten von Ereignissen an die entsprechenden Handler-Funktion.  
  
## <a name="related-articles"></a>Verwandte Artikel  
 [Verbindungspunkte](../atl/atl-connection-points.md)  
  
 [Ereignisbehandlung und ATL](../atl/event-handling-and-atl.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../atl/atl-class-overview.md)   
 [Verbindungspunkt-Makros](../atl/reference/connection-point-macros.md)   
 [Globale Verbindungspunkt-Funktionen](../atl/reference/connection-point-global-functions.md)

