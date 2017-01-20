---
title: "Implementing CComObject, CComAggObject, and CComPolyObject"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CComPolyObject"
  - "CComAggObject"
  - "CComObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComAggObject class"
  - "CComObject class, Implementieren"
  - "CComPolyObject class, Implementieren"
  - "CreateInstance-Methode"
ms.assetid: 5aabe938-104d-492e-9c41-9f7fb1c62098
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Implementing CComObject, CComAggObject, and CComPolyObject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklassen [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md) und [CComPolyObject](../atl/reference/ccompolyobject-class.md) sind immer die meisten abgeleitete Klassen in der Vererbungskette.  Es ist ihre Zuständigkeiten, alle Methoden in **IUnknown** zu behandeln: `QueryInterface`, `AddRef` und **Release**.  Außerdem stellen `CComAggObject` und `CComPolyObject` \(wenn Sie für zusammengesetzte Objekte verwendet werden\), die spezielle Verweiszählung und die `QueryInterface` Semantik, die für das innere Unbekannte erforderlich sind.  
  
 Ob `CComObject`, `CComAggObject` oder `CComPolyObject` verwendet wird, hängt davon ab, ob Sie eine \(oder keine\) der folgenden Makros deklarieren:  
  
|Makro|Effect|  
|-----------|------------|  
|`DECLARE_NOT_AGGREGATABLE`|Wird immer `CComObject`.|  
|`DECLARE_AGGREGATABLE`|Wird `CComAggObject`, wenn das Objekt und `CComObject` aggregiert wird, wenn nicht ist.  `CComCoClass` enthält dieses Makro so, wenn keine der **DECLARE\_\*\_AGGREGATABLE**\-Makros in der Klasse deklariert werden, dies ist die Standardeinstellung.|  
|`DECLARE_ONLY_AGGREGATABLE`|Wird immer `CComAggObject`.  Gibt einen Fehler zurück, wenn das Objekt nicht aggregiert wird.|  
|`DECLARE_POLY_AGGREGATABLE`|ATL erstellt eine Instanz von **CComPolyObject\<CYourClass\>**, wenn **IClassFactory::CreateInstance** aufgerufen wird.  Bei der Erstellung wird der Wert des äußeren Unbekannten überprüft.  Wenn es **NULL** ist, wird **IUnknown** für ein aggregiertes Objekt nicht implementiert.  Wenn das äußere Unbekannte nicht **NULL** ist, wird **IUnknown** für ein zusammengesetztes Objekt implementiert.|  
  
 Der Vorteil der Verwendung von `CComAggObject` und von `CComObject` ist, dass die Implementierung von **IUnknown** für die Art des Objekts optimiert ist, das erstellt wird.  Beispielsweise muss für ein aggregiertes Objekt nicht nur einen Verweiszähler, während ein zusammengesetztes Objekt einen Verweiszähler für das innere unbekannte und einen Zeiger auf den äußeren Unbekannten erfordert.  
  
 Der Vorteil der Verwendung von `CComPolyObject` ist, dass Sie vermeiden, `CComAggObject` und `CComObject` im Modul verfügen, um die aggregierten und nicht aggregierten Fälle zu behandeln.  Einzelne `CComPolyObject`\-Objekthandles beide Fälle.  Dies bedeutet, dass nur eine Kopie des vtable und eine Kopie der Funktionen im Modul vorhanden sind.  Wenn das vtable groß ist, kann dies die Modulgröße erheblich beeinträchtigt.  Wenn das vtable ist, mit `CComPolyObject` eine einige größere Modulgröße führen klein, da sie nicht für ein aggregiertes oder nicht aggregiertes Objekt optimiert wird, wie können `CComAggObject` und `CComObject`.  
  
## Siehe auch  
 [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md)   
 [Aggregation and Class Factory Macros](../atl/reference/aggregation-and-class-factory-macros.md)