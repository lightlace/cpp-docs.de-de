---
title: Punkte Verbindungsklassen (ATL) | Microsoft Docs
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
ms.openlocfilehash: 8c0d75c101bb23b3e7b788e607e325c18d729c81
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32355078"
---
# <a name="connection-points-classes"></a>Verbindungspunkte Klassen
Die folgenden Klassen bieten Unterstützung für Verbindungspunkte an:  
  
-   [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md) Connection Point Container implementiert.  
  
-   [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) implementiert einen Verbindungspunkt.  
  
-   [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) implementiert, ein Verbindung Punkt, der [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) Schnittstelle.  
  
-   [CComDynamicUnkArray](../atl/reference/ccomdynamicunkarray-class.md) verwaltet unbegrenzte Verbindungen zwischen einem Verbindungspunkt und seine senken.  
  
-   [CComUnkArray](../atl/reference/ccomunkarray-class.md) verwaltet eine feste Anzahl von Verbindungen zwischen einem Verbindungspunkt und seine senken.  
  
-   [CFirePropNotifyEvent](../atl/reference/cfirepropnotifyevent-class.md) benachrichtigt der Senke eines Clients, die die Eigenschaft eines Objekts geändert wurde oder zu ändern.  
  
-   [IDispEventImpl](../atl/reference/idispeventimpl-class.md) bietet Unterstützung für Verbindungspunkte für ein ATL-COM-Objekt. Diese Verbindungspunkte werden mit einer ereigniszuordnung Senke zugeordnet, die von COM-Objekt bereitgestellt wird.  
  
-   [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) funktioniert in Verbindung mit der Ereignissenke in die Klasse, um Ereignisse weiterzuleiten, an die entsprechenden Handler-Funktion zuzuordnen.  
  
## <a name="related-articles"></a>Verwandte Artikel  
 [Verbindungspunkte](../atl/atl-connection-points.md)  
  
 [Ereignisbehandlung und ATL](../atl/event-handling-and-atl.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../atl/atl-class-overview.md)   
 [Connection Point-Makros](../atl/reference/connection-point-macros.md)   
 [Globale Verbindungspunkt-Funktionen](../atl/reference/connection-point-global-functions.md)

