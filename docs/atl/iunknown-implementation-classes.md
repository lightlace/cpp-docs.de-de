---
title: IUnknown-Implementierungsklassen (ATL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.Iunknown
dev_langs:
- C++
helpviewer_keywords:
- IUnknown implementation classes
ms.assetid: 47b69bb5-69d8-4a9c-84a8-329bdde2bb3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b4cd2f2473249271285d6b8812dac1b924e5a172
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848534"
---
# <a name="iunknown-implementation-classes"></a>IUnknown-Implementierung-Klassen
Die folgenden Klassen implementieren `IUnknown` und verwandten Methoden:  
  
-   [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) verweiszählung für aggregierte und zusammengesetzten Objekte verwaltet. Ermöglicht Ihnen die Angabe ein Threadingmodell.  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) verweiszählung für aggregierte und zusammengesetzten Objekte verwaltet. Der Standardhost threading-Modell des Servers verwendet.  
  
-   [CComAggObject](../atl/reference/ccomaggobject-class.md) implementiert `IUnknown` für ein zusammengesetztes Objekt.  
  
-   [CComObject](../atl/reference/ccomobject-class.md) implementiert `IUnknown` für einen zusammengesetzten Objekt.  
  
-   [CComPolyObject](../atl/reference/ccompolyobject-class.md) implementiert `IUnknown` für aggregierte Daten und zusammengesetzten Objekte. Mithilfe von `CComPolyObject` wird vermieden, dass beide `CComAggObject` und `CComObject` innerhalb des Moduls. Ein einzelnes `CComPolyObject` Objekt behandelt, aggregierte und zusammengesetzten Fälle.  
  
-   [CComObjectNoLock](../atl/reference/ccomobjectnolock-class.md) implementiert `IUnknown` für eines zusammengesetzten Objekts, ohne die Sperrenanzahl des Moduls zu ändern.  
  
-   [CComTearOffObject](../atl/reference/ccomtearoffobject-class.md) implementiert `IUnknown` für eine Tearoff Schnittstelle.  
  
-   [CComCachedTearOffObject](../atl/reference/ccomcachedtearoffobject-class.md) implementiert `IUnknown` für eine "zwischengespeicherten" abtrennbare-Schnittstelle.  
  
-   [CComContainedObject](../atl/reference/ccomcontainedobject-class.md) implementiert `IUnknown` für das inneren Objekt eine Aggregation oder eine Tearoff Schnittstelle.  
  
-   [CComObjectGlobal](../atl/reference/ccomobjectglobal-class.md) verwaltet ein Verweiszähler für das Modul, um sicherzustellen, dass das Objekt wird nicht gelöscht.  
  
-   [CComObjectStack](../atl/reference/ccomobjectstack-class.md) erstellt ein temporäre COM-Objekt, mit eine skeletal-Implementierung des `IUnknown`.  
  
## <a name="related-articles"></a>Verwandte Artikel  
 [Grundlagen von ARL COM-Objekten](../atl/fundamentals-of-atl-com-objects.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../atl/atl-class-overview.md)   
 [Aggregation und Klassenfactory-Makros](../atl/reference/aggregation-and-class-factory-macros.md)   
 [COM-Zuordnungs-Makros](../atl/reference/com-map-macros.md)   
 [Globale COM-Zuordnungs-Funktionen](../atl/reference/com-map-global-functions.md)

