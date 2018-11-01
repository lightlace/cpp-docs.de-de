---
title: Implementieren der Ereignisbehandlungsschnittstelle
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, event handling
- event handling, ATL
- interfaces, event and event sink
ms.assetid: eb2a5b33-88dc-4ce3-bee0-c5c38ea050d7
ms.openlocfilehash: 0e676076e09620cb3e69e788549d808be4f6df1c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50455457"
---
# <a name="implementing-the-event-handling-interface"></a>Implementieren der Ereignisbehandlungsschnittstelle

ATL unterstützt Sie bei allen drei Elementen, die für die Behandlung von Ereignissen erforderlich sind: die Schnittstelle implementieren, Anmelden der Ereignisquelle und Abmelden der Ereignisquelle. Die genauen Schritte, die Sie ergreifen müssen, richten sich nach dem die Schnittstelle und die Erfüllung der leistungsanforderungen Ihrer Anwendung.

Die am häufigsten verwendeten Methoden zum Implementieren einer Schnittstelle, die mit ATL sind:

- Direkt Ableiten von einer benutzerdefinierten Schnittstelle.

- Ableiten von [IDispatchImpl](../atl/reference/idispatchimpl-class.md) für duale Schnittstellen, die in einer Typbibliothek beschrieben.

- Ableiten von [IDispEventImpl](../atl/reference/idispeventimpl-class.md) für Disp-Schnittstellen in einer Typbibliothek beschrieben.

- Ableiten von [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) für Dispatchschnittstellen nicht beschrieben, in einer Typbibliothek oder wenn Effizienz steigern, indem Sie die Typinformationen zur Laufzeit nicht geladen werden sollen.

Wenn Sie eine benutzerdefinierte oder duale Schnittstelle implementieren, sollten Sie die Ereignisquelle empfehlen, durch den Aufruf [AtlAdvise](reference/connection-point-global-functions.md#atladvise) oder [CComPtrBase:: Advise](../atl/reference/ccomptrbase-class.md#advise). Sie benötigen, um zu verfolgen das Cookie, das vom Aufruf zurückgegebene selbst. Rufen Sie [AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise) um die Verbindung trennen.

Wenn Sie eine Dispinterface mit implementieren `IDispEventImpl` oder `IDispEventSimpleImpl`, informiert Sie die Ereignisquelle durch den Aufruf [IDispEventSimpleImpl:: DispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise). Rufen Sie [IDispEventSimpleImpl::DispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise) um die Verbindung trennen.

Bei Verwendung von `IDispEventImpl` als eine Basisklasse eines zusammengesetzten Steuerelements, die Ereignisquellen in der Zuordnung der Senke aufgelistet werden empfohlen und abzumelden, automatisch mit [:: AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap).

Die `IDispEventImpl` und `IDispEventSimpleImpl` Klassen verwaltet das Cookie für Sie.

## <a name="see-also"></a>Siehe auch

[Ereignisbehandlung](../atl/event-handling-and-atl.md)
