---
title: Verbindungspunkt Klassen (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- classes [C++], connection points
- connection points classes
ms.assetid: 076365fa-299a-4dce-84c3-a5dff0e0da1f
ms.openlocfilehash: 0dba06b072e1e9ca545ccbea196fcfe371b02157
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492443"
---
# <a name="connection-points-classes"></a>Klassen für Verbindungspunkte

Die folgenden Klassen unterstützen Verbindungspunkte:

- [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md) Implementiert einen Verbindungspunkt Container.

- [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) Implementiert einen Verbindungspunkt.

- [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) Implementiert einen Verbindungspunkt, der die [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) -Schnittstelle darstellt.

- [Ccomdynamicunkarray](../atl/reference/ccomdynamicunkarray-class.md) Verwaltet unbegrenzte Verbindungen zwischen einem Verbindungspunkt und seinen senken.

- [Ccomunkarray](../atl/reference/ccomunkarray-class.md) Verwaltet eine Fixed Anzahl von Verbindungen zwischen einem Verbindungspunkt und seinen senken.

- [Cfirepropnotischyevent](../atl/reference/cfirepropnotifyevent-class.md) Benachrichtigt die Senke eines Clients, dass die-Eigenschaft eines Objekts geändert wurde oder gerade geändert wird.

- [IDispEventImpl](../atl/reference/idispeventimpl-class.md) Bietet Unterstützung für Verbindungspunkte für ein ATL-COM-Objekt. Diese Verbindungspunkte werden einer Ereignis Senk Karte zugeordnet, die von Ihrem com-Objekt bereitgestellt wird.

- [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) Arbeitet in Verbindung mit der Ereignis senkenzuordnung in der-Klasse, um Ereignisse an die entsprechende Handlerfunktion weiterzuleiten.

## <a name="related-articles"></a>Verwandte Artikel

[Verbindungspunkte](../atl/atl-connection-points.md)

[Ereignisbehandlung und ATL](../atl/event-handling-and-atl.md)

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../atl/atl-class-overview.md)<br/>
[Verbindungspunkt-Makros](../atl/reference/connection-point-macros.md)<br/>
[Globale Verbindungspunkt-Funktionen](../atl/reference/connection-point-global-functions.md)
