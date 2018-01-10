---
title: Punkte Verbindungsklassen (ATL) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.atl.connection
dev_langs: C++
helpviewer_keywords:
- classes [C++], connection points
- connection points classes
ms.assetid: 076365fa-299a-4dce-84c3-a5dff0e0da1f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e85194547b78e3d3fa3bba868be02c705fcf9a43
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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

