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
ms.openlocfilehash: b3f866d56d0c0ab89a91b13e238d9503c1ca9e02
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43205074"
---
# <a name="connection-points-classes"></a>Verbindungspunkteklassen
Die folgenden Klassen bieten Unterstützung für Verbindungspunkte an:  
  
-   [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md) eine Verbindungspunktcontainer implementiert.  
  
-   [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) implementiert einen Verbindungspunkt.  
  
-   [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) implementiert ein Connection Point, die [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) Schnittstelle.  
  
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

