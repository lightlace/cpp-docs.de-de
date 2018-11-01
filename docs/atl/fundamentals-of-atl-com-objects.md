---
title: Grundlagen von ARL COM-Objekten
ms.date: 11/04/2016
helpviewer_keywords:
- COM, and ATL
- ATL, COM
- ATL COM objects
- COM objects, ATL
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
ms.openlocfilehash: 243b7f84fc20e1c002e866ae0720ab9521d24748
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50437234"
---
# <a name="fundamentals-of-atl-com-objects"></a>Grundlagen von ARL COM-Objekten

Die folgende Abbildung zeigt die Beziehung zwischen Klassen und Schnittstellen, die verwendet werden, um ein ATL-COM-Objekt zu definieren.

![ATL-Struktur](../atl/media/vc307y1.gif "vc307y1")

> [!NOTE]
>  Dieses Diagramm zeigt, dass `CComObject` ergibt sich aus `CYourClass` während `CComAggObject` und `CComPolyObject` enthalten `CYourClass` als eine Membervariable.

Es gibt drei Möglichkeiten zum Definieren eines ATL-COM-Objekts. Die Option "standard" ist die Verwendung der `CComObject` Klasse abgeleitet ist `CYourClass`. Die zweite Option ist die Erstellung ein aggregierten Objekts unter Verwendung der `CComAggObject` Klasse. Die dritte Option ist die Verwendung der `CComPolyObject` Klasse. `CComPolyObject` fungiert als eine hybride: ordnungsgemäß als ein `CComObject` Klasse oder eine `CComAggObject` -Klasse, je nachdem, wie es zuerst erstellt wird. Weitere Informationen zur Verwendung der `CComPolyObject` Klasse, finden Sie unter [CComPolyObject-Klasse](../atl/reference/ccompolyobject-class.md).

Bei Verwendung von standard-ATL-COM-verwenden Sie zwei Objekte: eine äußere Objekt und einer inneren Objekts. Externe Clients auf die Funktionalität des inneren Objekts zugreifen, durch die Wrapperfunktionen, die in das äußere Objekt definiert sind. Das äußere Objekt ist vom Typ `CComObject`.

Wenn Sie ein zusammengesetztes Objekt verwenden, bietet das äußere Objekt keine Wrapper für die Funktionalität des inneren Objekts. Stattdessen stellt das äußere Objekt einen Zeiger, der direkt von externen Clients zugegriffen wird. In diesem Szenario ist das äußere Objekt vom Typ `CComAggObject`. Das innere Objekt ist eine Membervariable des das äußere Objekt und ist vom Typ `CYourClass`.

Da der Client keine durchlaufen, das äußere Objekt, das das innere Objekt interagieren, sind die aggregierten Objekte in der Regel effizienter. Darüber hinaus das äußere Objekt keine wissen, die Funktionalität des aggregierten Objekts, angesichts der Tatsache, dass die Schnittstelle des aggregierten Objekts direkt an den Client verfügbar ist. Allerdings können nicht von allen Objekten aggregiert werden. Für ein Objekt, aggregiert werden sollen muss sie mit Aggregation, denken Sie daran so entworfen werden.

ATL implementiert [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) in zwei Phasen:

- [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md), oder [CComPolyObject](../atl/reference/ccompolyobject-class.md) implementiert die `IUnknown` Methoden.

- [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) verwaltet den Verweiszähler und die äußeren Zeiger `IUnknown`.

Andere Aspekte des ATL-COM-Objekts werden von anderen Klassen verarbeitet:

- [CComCoClass](../atl/reference/ccomcoclass-class.md) Factory und Aggregation des Objekts standardmäßige Klasse-Modell definiert.

- [IDispatchImpl](../atl/reference/idispatchimpl-class.md) stellt eine Standardimplementierung von der `IDispatch Interface` Teil aller duale Schnittstellen für das Objekt.

- [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) implementiert die `ISupportErrorInfo` Schnittstelle, die sicherstellt Fehlerinformationen kann ordnungsgemäß der Aufrufkette weitergegeben werden.

## <a name="in-this-section"></a>In diesem Abschnitt

[Implementieren von CComObjectRootEx](../atl/implementing-ccomobjectrootex.md)<br/>
Beispiel zum Implementieren von COM-Zuordnungseinträgen anzeigen `CComObjectRootEx`.

[Implementieren von CComObject, CComAggObject und CComPolyObject](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)<br/>
Erläutert, wie die **DECLARE_\*_AGGREGATABLE** Makros wirken sich auf die der `CComObject`, `CComAggObject`, und `CComPolyObject`.

[Unterstützen von IDispatch und IErrorInfo](../atl/supporting-idispatch-and-ierrorinfo.md)<br/>
Listet die ATL-Implementierung-Klassen für die Verwendung für die Unterstützung der `IDispatch` und `IErrorInfo` Schnittstellen.

[Unterstützen von IDispEventImpl](../atl/supporting-idispeventimpl.md)<br/>
Erläutert die Schritte, um einen Verbindungspunkt für die Klasse zu implementieren.

[Ändern der Standardklassenfactory und Aggregationmodell](../atl/changing-the-default-class-factory-and-aggregation-model.md)<br/>
Zeigen Sie an, welche Makros zu verwenden, um das standardmäßige Klasse-Factory und Aggregation-Modell zu ändern.

[Erstellen eines aggregierten Objekts](../atl/creating-an-aggregated-object.md)<br/>
Listet die Schritte zum Erstellen eines aggregierten Objekts.

## <a name="related-sections"></a>Verwandte Abschnitte

[Erstellen eines ATL-Projekts](../atl/reference/creating-an-atl-project.md)<br/>
Enthält Informationen zum Erstellen eines ATL-COM-Objekts.

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Enthält Links zu konzeptionellen Themen über die Programmierung mit der Active Template Library.

## <a name="see-also"></a>Siehe auch

[Konzepte](../atl/active-template-library-atl-concepts.md)

