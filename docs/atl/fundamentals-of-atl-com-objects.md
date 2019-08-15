---
title: Grundlagen von ATL-COM-Objekten
ms.date: 11/19/2018
helpviewer_keywords:
- COM, and ATL
- ATL, COM
- ATL COM objects
- COM objects, ATL
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
ms.openlocfilehash: ec83539b2d7101c534bbc1df33577df422e76152
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492367"
---
# <a name="fundamentals-of-atl-com-objects"></a>Grundlagen von ATL-COM-Objekten

Die folgende Abbildung zeigt die Beziehung zwischen den Klassen und Schnittstellen, die verwendet werden, um ein ATL-COM-Objekt zu definieren.

![ATL-Struktur](../atl/media/vc307y1.gif "ATL-Struktur")

> [!NOTE]
>  Dieses Diagramm zeigt, `CComObject` dass `CComAggObject` von `CYourClass` abgeleitet ist und `CComPolyObject` als `CYourClass` Element Variable enthalten ist.

Es gibt drei Möglichkeiten, ein ATL-COM-Objekt zu definieren. Die Standardoption ist die Verwendung der `CComObject` -Klasse, die von `CYourClass`abgeleitet wird. Die zweite Option ist das Erstellen eines aggregierten Objekts mithilfe der `CComAggObject` -Klasse. Die dritte Option ist die Verwendung der `CComPolyObject` -Klasse. `CComPolyObject`fungiert als Hybrid: Es kann als `CComObject` Klasse oder `CComAggObject` als Klasse fungieren, je nachdem, wie es erstellt wird. Weitere Informationen zur Verwendung der `CComPolyObject` -Klasse finden Sie unter [CComPolyObject Class](../atl/reference/ccompolyobject-class.md).

Wenn Sie Standard-ATL-COM verwenden, verwenden Sie zwei Objekte: ein äußeres Objekt und ein internes Objekt. Externe Clients greifen über die Wrapper Funktionen, die im äußeren Objekt definiert sind, auf die Funktionalität des inneren Objekts zu. Das äußere Objekt ist vom Typ `CComObject`.

Wenn Sie ein aggregiertes Objekt verwenden, stellt das äußere Objekt keine Wrapper für die Funktionalität des inneren Objekts bereit. Stattdessen stellt das äußere Objekt einen Zeiger bereit, auf den direkt von externen Clients zugegriffen wird. In diesem Szenario ist das äußere Objekt vom Typ `CComAggObject`. Das innere Objekt ist eine Element Variable des äußeren Objekts und weist den Typ `CYourClass`auf.

Da der Client das äußere Objekt nicht durchlaufen muss, um mit dem inneren Objekt zu interagieren, sind aggregierte Objekte in der Regel effizienter. Außerdem muss das äußere Objekt die Funktionalität des aggregierten Objekts nicht kennen, da die-Schnittstelle des aggregierten Objekts direkt für den Client verfügbar ist. Allerdings können nicht alle Objekte aggregiert werden. Für ein Objekt, das aggregiert werden soll, muss es im Hinblick auf die Aggregation entworfen werden.

ATL implementiert [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) in zwei Phasen:

- [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md)oder [CComPolyObject](../atl/reference/ccompolyobject-class.md) implementiert die `IUnknown` -Methoden.

- [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) verwaltet den Verweis Zähler und äußere Zeiger von `IUnknown`.

Andere Aspekte des ATL-COM-Objekts werden von anderen Klassen behandelt:

- [CComCoClass](../atl/reference/ccomcoclass-class.md) definiert die Standardklassenfactory und das Aggregations Modell des Objekts.

- [IDispatchImpl](../atl/reference/idispatchimpl-class.md) stellt eine Standard Implementierung des `IDispatch Interface` -Teils aller Dual-Schnittstellen für das-Objekt bereit.

- [Isupporterrorinfoimpl](../atl/reference/isupporterrorinfoimpl-class.md) implementiert die `ISupportErrorInfo` -Schnittstelle, mit der sichergestellt wird, dass Fehlerinformationen ordnungsgemäß nach oben übermittelt werden können.

## <a name="in-this-section"></a>In diesem Abschnitt

[Implementieren von CComObjectRootEx](../atl/implementing-ccomobjectrootex.md)<br/>
Zeigt Beispiel-com-Zuordnungs `CComObjectRootEx`Einträge zum Implementieren von.

[Implementieren von CComObject, CComAggObject und CComPolyObject](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)<br/>
Erläutert, wie sich die **DECLARE_\*_AGGREGATABLE** -Makros auf `CComObject`die Verwendung von `CComPolyObject`, `CComAggObject`und auswirken.

[Unterstützen von IDispatch und IErrorInfo](../atl/supporting-idispatch-and-ierrorinfo.md)<br/>
Listet die ATL-Implementierungsklassen auf, die zur `IDispatch` unter `IErrorInfo` Stützung der Schnittstellen und verwendet werden.

[Unterstützen von IDispEventImpl](../atl/supporting-idispeventimpl.md)<br/>
Erläutert die Schritte zum Implementieren eines Verbindungs Punkts für die-Klasse.

[Ändern der Standardklassenfactory und Aggregationmodell](../atl/changing-the-default-class-factory-and-aggregation-model.md)<br/>
Zeigt an, welche Makros zum Ändern der Standardklassenfactory und des Aggregations Modells verwendet werden sollen.

[Erstellen eines aggregierten Objekts](../atl/creating-an-aggregated-object.md)<br/>
Listet die Schritte zum Erstellen eines aggregierten Objekts auf.

## <a name="related-sections"></a>Verwandte Abschnitte

[Erstellen eines ATL-Projekts](../atl/reference/creating-an-atl-project.md)<br/>
Stellt Informationen zum Erstellen eines ATL-COM-Objekts bereit.

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Enthält Links zu konzeptionellen Themen über die Programmierung mit der Active Template Library.

## <a name="see-also"></a>Siehe auch

[Konzepte](../atl/active-template-library-atl-concepts.md)
