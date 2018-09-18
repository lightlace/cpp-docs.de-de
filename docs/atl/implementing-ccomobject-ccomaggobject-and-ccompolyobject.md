---
title: Implementieren von CComObject, CComAggObject und CComPolyObject | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c4eed55a90d05728c6625b49454ef4297b878975
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067908"
---
# <a name="implementing-ccomobject-ccomaggobject-and-ccompolyobject"></a>Implementieren von CComObject, CComAggObject und CComPolyObject

Die Vorlagenklassen [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md), und [CComPolyObject](../atl/reference/ccompolyobject-class.md) werden immer am weitesten abgeleiteten Klassen in der Vererbungskette. Es liegt in ihrer Verantwortung, zur Behandlung aller Methoden in `IUnknown`: `QueryInterface`, `AddRef`, und `Release`. Darüber hinaus `CComAggObject` und `CComPolyObject` (bei Verwendung für aggregierte Objekte) bereitstellen, die spezielle verweiszählung und `QueryInterface` Semantik, die für die innere unbekannte erforderlich sind.

Ob `CComObject`, `CComAggObject`, oder `CComPolyObject` wird verwendet, hängt von, ob Sie eine (oder keine) der folgenden Makros deklarieren:

|Makro|Effekt|
|-----------|------------|
|DECLARE_NOT_AGGREGATABLE|Verwendet immer `CComObject`.|
|DECLARE_AGGREGATABLE|Verwendet `CComAggObject` , wenn das Objekt aggregiert wird und `CComObject` ist dies nicht. `CComCoClass` Dieses Makro enthält, wenn keine der welchen Einfluss die DECLARE_ * _AGGREGATABLE Makros in der Klasse deklariert werden diese als Standardeinstellung verwendet wird.|
|DECLARE_ONLY_AGGREGATABLE|Verwendet immer `CComAggObject`. Gibt einen Fehler zurück, wenn das Objekt nicht aggregiert werden.|
|DECLARE_POLY_AGGREGATABLE|ATL-erstellt eine Instanz des **CComPolyObject\<CYourClass >** beim `IClassFactory::CreateInstance` aufgerufen wird. Während der Erstellung wird der Wert, der die äußere unbekannte überprüft. Wenn auf NULL, `IUnknown` für einen zusammengesetzten Objekt implementiert wird. Wenn die äußere unbekannte ungleich NULL ist `IUnknown` wird für ein zusammengesetztes Objekt implementiert.|

Der Vorteil der Verwendung `CComAggObject` und `CComObject` ist, die die Implementierung der `IUnknown` ist optimiert für die Art des zu erstellenden Objekts. Ein zusammengesetzten Objekts benötigt z. B. nur einen Verweiszähler während ein aggregierten Objekts sowohl einen Verweiszähler für den inneren unbekannt und einen Zeiger auf die äußere unbekannte benötigt.

Der Vorteil der Verwendung `CComPolyObject` besteht darin, dass Sie vermeiden, dass beide `CComAggObject` und `CComObject` innerhalb des Moduls, die aggregierte und zusammengesetzten Fälle zu behandeln. Ein einzelnes `CComPolyObject` Objekt behandelt beide Fälle. Dies bedeutet, dass nur eine Kopie der Vtable und eine Kopie der Funktionen, die innerhalb des Moduls vorhanden sind. Wenn Ihre Vtable groß ist, kann dies Modulgröße erheblich verringern. Die Vtable klein ist, jedoch verwenden `CComPolyObject` kann dazu führen, etwas Modul größer, da sie nicht für ein Objekt zusammengesetzten oder aggregiert, optimiert ist wie `CComAggObject` und `CComObject`.

## <a name="see-also"></a>Siehe auch

[Grundlagen von ARL COM-Objekten](../atl/fundamentals-of-atl-com-objects.md)<br/>
[Aggregation und Klassenfactory-Makros](../atl/reference/aggregation-and-class-factory-macros.md)

