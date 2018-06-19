---
title: IUnknown-Implementierungsklassen (ATL) | Microsoft Docs
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
ms.openlocfilehash: 3d67b2a7b9769acd7d6e596e4fcdf1aec30bbf74
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357215"
---
# <a name="iunknown-implementation-classes"></a>IUnknown-Implementierungsklassen
Die folgenden Klassen implementieren **IUnknown** und die zugehörigen Methoden:  
  
-   [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) verweiszählung für zusammengefasste und aggregierte Objekte verwaltet. Ermöglicht Ihnen die Angabe ein Threadingmodell.  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) verweiszählung für zusammengefasste und aggregierte Objekte verwaltet. Verwendet den standardmäßigen Threadingmodell des Servers.  
  
-   [CComAggObject](../atl/reference/ccomaggobject-class.md) implementiert **IUnknown** für ein zusammengesetztes Objekt.  
  
-   [CComObject](../atl/reference/ccomobject-class.md) implementiert **IUnknown** für eine aggregierte Objekt.  
  
-   [CComPolyObject](../atl/reference/ccompolyobject-class.md) implementiert **IUnknown** für zusammengefasste und aggregierte Objekte. Mit `CComPolyObject` vermeidet beide `CComAggObject` und `CComObject` innerhalb des Moduls. Ein einzelnes `CComPolyObject` Objekt verarbeitet die zusammengefasste und aggregierte Fälle.  
  
-   [CComObjectNoLock](../atl/reference/ccomobjectnolock-class.md) implementiert **IUnknown** für eine aggregierte Objekt ohne Änderung der Anzahl der Module Sperre.  
  
-   [CComTearOffObject](../atl/reference/ccomtearoffobject-class.md) implementiert **IUnknown** für eine abtrennbare-Schnittstelle.  
  
-   [CComCachedTearOffObject](../atl/reference/ccomcachedtearoffobject-class.md) implementiert **IUnknown** für eine "zwischengespeicherte" abtrennbare-Schnittstelle.  
  
-   [CComContainedObject](../atl/reference/ccomcontainedobject-class.md) implementiert **IUnknown** für das innere Objekt des eine Aggregation oder eine abtrennbare-Schnittstelle.  
  
-   [CComObjectGlobal](../atl/reference/ccomobjectglobal-class.md) Management ein Verweiszähler für das Modul, um sicherzustellen, dass das Objekt nicht gelöscht werden wird.  
  
-   [CComObjectStack](../atl/reference/ccomobjectstack-class.md) erstellt ein temporäres COM-Objekt, mit einem skeletal-Implementierung des **IUnknown**.  
  
## <a name="related-articles"></a>Verwandte Artikel  
 [Grundlagen von ARL COM-Objekten](../atl/fundamentals-of-atl-com-objects.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../atl/atl-class-overview.md)   
 [Aggregation und Klasse Factory-Makros](../atl/reference/aggregation-and-class-factory-macros.md)   
 [COM-Zuordnungsmakros](../atl/reference/com-map-macros.md)   
 [Globale COM-Zuordnungs-Funktionen](../atl/reference/com-map-global-functions.md)

