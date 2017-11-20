---
title: Grundlagen von ATL-COM-Objekten | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- COM, and ATL
- ATL, COM
- ATL COM objects
- COM objects, ATL
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 30527a705d880e96620edfee5f7ad7897f9371a7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="fundamentals-of-atl-com-objects"></a>Grundlagen von ATL-COM-Objekten
Die folgende Abbildung zeigt die Beziehung zwischen Klassen und Schnittstellen, die zum Definieren eines ATL-COM-Objekts verwendet werden.  
  
 ![ATL-Struktur](../atl/media/vc307y1.gif "vc307y1")  
  
> [!NOTE]
>  Dieses Diagramm zeigt, dass `CComObject` stammt aus `CYourClass` während `CComAggObject` und `CComPolyObject` enthalten `CYourClass` als einer Membervariablen gespeichert.  
  
 Es gibt drei Möglichkeiten zum Definieren eines ATL-COM-Objekts. Die standard-Option ist die Verwendung der `CComObject` Klasse abgeleitet ist `CYourClass`. Die zweite Möglichkeit besteht, erstellen Sie ein zusammengesetztes Objekt mithilfe der `CComAggObject` Klasse. Die dritte Option ist die Verwendung der `CComPolyObject` Klasse. `CComPolyObject`fungiert als eine hybride: ordnungsgemäß als eine `CComObject` Klasse oder als eine `CComAggObject` -Klasse, je nachdem, wie es zuerst erstellt wird. Weitere Informationen zur Verwendung der `CComPolyObject` Klasse, finden Sie unter [CComPolyObject Klasse](../atl/reference/ccompolyobject-class.md).  
  
 Bei Verwendung von standard ATL-COM-verwenden Sie zwei Objekte: eine äußere Objekt und eine innere Objekt. Externe Clients auf die Funktionalität des inneren Objekts zugreifen, durch die Wrapperfunktionen, die in das äußere Objekt definiert sind. Das äußere Objekt ist vom Typ `CComObject`.  
  
 Wenn Sie ein zusammengesetztes Objekt verwenden, stellt das äußere Objekt keine Wrapper für die Funktionalität des inneren Objekts bereit. Stattdessen stellt das äußere Objekt einen Zeiger, der durch externe Clients direkt zugegriffen wird. In diesem Szenario ist das äußere Objekt vom Typ `CComAggObject`. Das innere Objekt wird eine Membervariable des äußeren Objekts und eigentlicher Typ ist `CYourClass`.  
  
 Da der Client keine durchlaufen das äußere Objekt, das das innere Objekt interagieren, sind aggregierte Objekten in der Regel effizienter. Darüber hinaus muss das äußere Objekt nicht wissen, die Funktionalität des aggregierten-Objekts, davon ausgehend, dass die Schnittstelle des aggregierten Objekts direkt an den Client verfügbar ist. Allerdings können nicht alle Objekte aggregiert werden. Für ein Objekt, das aggregiert werden muss er mit Bedenken Aggregation entworfen werden.  
  
 ATL implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) in zwei Phasen:  
  
-   [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md), oder [CComPolyObject](../atl/reference/ccompolyobject-class.md) implementiert die **IUnknown** Methoden.  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) verwaltet den Verweiszähler dieser Planergruppe und die äußere Zeiger **IUnknown**.  
  
 Andere Aspekte Ihres ATL-COM-Objekts werden von anderen Klassen verarbeitet:  
  
-   [CComCoClass](../atl/reference/ccomcoclass-class.md) definiert das Objekt Klasse Factory und Aggregation Standardmodell.  
  
-   [IDispatchImpl](../atl/reference/idispatchimpl-class.md) stellt eine Standardimplementierung von der `IDispatch Interface` Teil jeder dualen Schnittstellen für das Objekt.  
  
-   [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) implementiert die **ISupportErrorInfo** Schnittstelle, die Fehlerinformationen wird sichergestellt, dass kann ordnungsgemäß der Aufrufkette weitergegeben werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Implementieren von CComObjectRootEx](../atl/implementing-ccomobjectrootex.md)  
 Enthalten Beispiele für COM-Zuordnungseinträge für die Implementierung `CComObjectRootEx`.  
  
 [Implementieren von CComObject, CComAggObject und CComPolyObject](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)  
 Erläutert, wie die **DECLARE_\*_AGGREGATABLE** Makros Auswirkungen auf die Verwendung von `CComObject`, `CComAggObject`, und `CComPolyObject`.  
  
 [Unterstützen von IDispatch und IErrorInfo](../atl/supporting-idispatch-and-ierrorinfo.md)  
 Listet die ATL-Implementierungsklassen verwendet für die Unterstützung der `IDispatch` und **IErrorInfo** Schnittstellen.  
  
 [Unterstützen von IDispEventImpl](../atl/supporting-idispeventimpl.md)  
 Erläutert die Schritte, um einen Verbindungspunkt für die Klasse zu implementieren.  
  
 [Ändern der Standardklassenfactory und Aggregationmodell](../atl/changing-the-default-class-factory-and-aggregation-model.md)  
 Zeigen Sie an, welche Makros verwenden, um die Factory und Aggregation Standardmodell von Klasse zu ändern.  
  
 [Erstellen eines aggregierten Objekts](../atl/creating-an-aggregated-object.md)  
 Listet die Schritte zum Erstellen eines zusammengesetzten Objekts.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Erstellen eines ATL-Projekts](../atl/reference/creating-an-atl-project.md)  
 Enthält Informationen zum Erstellen eines ATL-COM-Objekts.  
  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Enthält Links zu konzeptionellen Themen über die Programmierung mit der Active Template Library.  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)

