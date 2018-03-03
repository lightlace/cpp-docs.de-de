---
title: Implementieren von CComObject, CComAggObject und CComPolyObject | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CComPolyObject
- CComAggObject
- CComObject
dev_langs:
- C++
helpviewer_keywords:
- CComPolyObject class, implementing
- CreateInstance method
- CComAggObject class
- CComObject class, implementing
ms.assetid: 5aabe938-104d-492e-9c41-9f7fb1c62098
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 54f237a629c4af9ea7ae30aeca21c03786abcd97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-ccomobject-ccomaggobject-and-ccompolyobject"></a>Implementieren von CComObject, CComAggObject und CComPolyObject
Die Vorlagenklassen [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md), und [CComPolyObject](../atl/reference/ccompolyobject-class.md) sind immer die am stärksten abgeleiteten Klassen in der Vererbungskette. Es liegt in ihrer Verantwortung zur Behandlung aller Methoden in **IUnknown**: `QueryInterface`, `AddRef`, und **Version**. Darüber hinaus `CComAggObject` und `CComPolyObject` (Wenn für aggregierte Objekte verwendet wird) bereitstellen, die spezielle verweiszählung und `QueryInterface` Semantik für die innere unbekannte erforderlich sind.  
  
 Ob `CComObject`, `CComAggObject`, oder `CComPolyObject` wird verwendet, richtet sich nach, ob Sie eine (oder keine) der folgenden Makros deklarieren:  
  
|Makro|Effekt|  
|-----------|------------|  
|`DECLARE_NOT_AGGREGATABLE`|Verwendet immer `CComObject`.|  
|`DECLARE_AGGREGATABLE`|Verwendet `CComAggObject` , wenn das Objekt aggregiert wird und `CComObject` wird jedoch nicht. `CComCoClass`Dieses Makro enthält, wenn keines der **DECLARE_\*_AGGREGATABLE** Makros werden dies ist der Standardwert wird in der Klasse deklariert.|  
|`DECLARE_ONLY_AGGREGATABLE`|Verwendet immer `CComAggObject`. Gibt einen Fehler zurück, wenn das Objekt nicht aggregiert werden.|  
|`DECLARE_POLY_AGGREGATABLE`|ATL erstellt eine Instanz des **CComPolyObject\<CYourClass >** Wenn **IClassFactory:: CreateInstance** aufgerufen wird. Während der Erstellung wird der Wert, der die äußere unbekannte überprüft. Ist er **NULL**, **IUnknown** für eine aggregierte Objekt implementiert wird. Wenn die äußere unbekannte nicht **NULL**, **IUnknown** für ein zusammengesetztes Objekt implementiert wird.|  
  
 Der Vorteil der Verwendung `CComAggObject` und `CComObject` ist, die die Implementierung der **IUnknown** ist optimiert für die Art des zu erstellenden Objekts. Ein aggregierte Objekt benötigt z. B. nur einen Verweiszähler während ein zusammengesetzten Objekts einen Verweiszähler für den inneren unbekannt und ein Zeiger auf die äußere unbekannte benötigt.  
  
 Der Vorteil der Verwendung `CComPolyObject` ist, dass Sie vermeiden, dass beide `CComAggObject` und `CComObject` innerhalb des Moduls, die zusammengefasste und aggregierte Fälle zu behandeln. Ein einzelnes `CComPolyObject` Objekt verarbeitet die beiden Fällen. Dies bedeutet, dass nur eine Kopie der Vtable und eine Kopie der Funktionen, die innerhalb des Moduls vorhanden sind. Wenn Ihre Vtable groß ist, kann dies die Modulgröße erheblich verringern. Jedoch verwenden, wenn die Vtable klein ist, `CComPolyObject` kann dazu führen, etwas Modul größer, da sie nicht für ein Objekt aggregierten oder aggregierte optimiert ist wie `CComAggObject` und `CComObject`.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen von ATL-COM-Objekten](../atl/fundamentals-of-atl-com-objects.md)   
 [Aggregation und Klassenfactory-Makros](../atl/reference/aggregation-and-class-factory-macros.md)

