---
title: ATL-Connection Point-Klassen
ms.date: 11/04/2016
helpviewer_keywords:
- CFirePropNotifyEvent class, connection point classes
- connection points [C++], ATL classes
- ATL, connection points
- CComDynamicUnkArray class, connection point classes
- CFirePropNotifyEvent class
- CComUnkArray class, connection point classes
ms.assetid: 9582ba71-7ace-4df4-9c9b-1b0636953efc
ms.openlocfilehash: 8644fc087d7f0a651724c40d2868e96c9b6ec96a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491822"
---
# <a name="atl-connection-point-classes"></a>ATL-Connection Point-Klassen

ATL verwendet die folgenden Klassen, um Verbindungspunkte zu unterstützen:

- [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) implementiert einen Verbindungspunkt. Die IID der ausgehenden Schnittstelle, die Sie darstellt, wird als Vorlagen Parameter übergeben.

- [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md) implementiert den Verbindungspunkt Container und verwaltet die Liste der `IConnectionPointImpl` Objekte.

- [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) implementiert einen Verbindungspunkt, der die [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) -Schnittstelle darstellt.

- [Ccomdynamicunkarray](../atl/reference/ccomdynamicunkarray-class.md) verwaltet eine beliebige Anzahl von Verbindungen zwischen dem Verbindungspunkt und seinen senken.

- [Ccomunkarray](../atl/reference/ccomunkarray-class.md) verwaltet eine vordefinierte Anzahl von Verbindungen, wie im Vorlagen Parameter angegeben.

- [Cfirepropnotifyevent](../atl/reference/cfirepropnotifyevent-class.md) benachrichtigt die Senke eines Clients, dass die-Eigenschaft eines Objekts geändert wurde oder gerade geändert wird.

- [IDispEventImpl](../atl/reference/idispeventimpl-class.md) bietet Unterstützung für Verbindungspunkte für ein ATL-COM-Objekt. Diese Verbindungspunkte werden einer Ereignis Senk Karte zugeordnet, die von Ihrem com-Objekt bereitgestellt wird.

- [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) funktioniert in Verbindung mit der Ereignis senkenzuordnung in der-Klasse, um Ereignisse an die entsprechende Handlerfunktion weiterzuleiten.

## <a name="see-also"></a>Siehe auch

[Verbindungspunkt](../atl/atl-connection-points.md)
