---
title: "Fundamentals of ATL COM Objects"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL COM objects"
  - "ATL, COM"
  - "COM-Objekte, ATL"
  - "COM, und ATL"
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
caps.latest.revision: 25
caps.handback.revision: "20"
ms.author: "mblome"
manager: "ghogen"
---
# Fundamentals of ATL COM Objects
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgende Abbildung stellt die Beziehung zwischen den Klassen und Schnittstellen dar, die verwendet werden, um ein ATL COM\-Objekt zu definieren.  
  
 ![ATL&#45;Struktur](../atl/media/vc307y1.png "vc307Y1")  
  
> [!NOTE]
>  Dieses Diagramm zeigt, dass `CComObject` von `CYourClass` abgeleitet wird, während `CComAggObject` und `CComPolyObject``CYourClass` als Membervariable einschließen.  
  
 Es gibt drei Möglichkeiten, ein ATL COM\-Objekt zu definieren.  Die Standardoption ist, die `CComObject`\-Klasse zu verwenden, die von `CYourClass` abgeleitet wird.  Die zweite Option ist, ein zusammengesetztes Objekt erstellen, indem sie die `CComAggObject`\-Klasse verwendet.  Die dritte Option besteht darin, die `CComPolyObject`\-Klasse zu verwenden.  `CComPolyObject` fungiert als ein Hybrid aus auf: kann nur als `CComObject`\-Klasse oder als `CComAggObject`\-Klasse, je nachdem, wie sie zuerst erstellt wird.  Weitere Informationen über die Verwendung der `CComPolyObject`\-Klasse finden Sie unter [CComPolyObject Class](../atl/reference/ccompolyobject-class.md).  
  
 Wenn Sie Standard ATL COM verwenden, verwenden Sie zwei Objekte: ein äußeres Objekt und ein inneres Objekt.  Durch externe Clients greifen auf die Funktionalität des inneren Objekts durch die Wrapperfunktionen zu, die im äußeren Objekt definiert werden.  Das äußere Objekt ist vom Typ `CComObject`.  
  
 Wenn Sie ein zusammengesetztes Objekt verwenden, erstellt das äußere Objekt Wrapper nicht für die Funktionalität des inneren Objekts bereit.  Stattdessen stellt das äußere Objekt einen Zeiger, auf den direkt von Clients zugegriffen wird.  In diesem Szenario ist das äußere Objekt vom Typ `CComAggObject`.  Das innere Objekt ist eine Membervariable des äußeren Objekts, und es ist vom Typ `CYourClass`.  
  
 Da der Client nicht das äußere Objekt durchlaufen, muss mit dem inneren Objekt zu interagieren, sind zusammengesetzte Objekte normalerweise effizienter.  Außerdem wird das äußere Objekt muss die Funktionalität des zusammengesetzten Objekts nicht kennen, vorausgesetzt, die Schnittstelle des zusammengesetzten Objekts direkt an den Client verfügbar ist.  Allerdings können nicht alle Objekte aggregiert werden.  Damit ein Objekt aggregiert werden kann, muss es mit Aggregation im Auge entworfen.  
  
 ATL implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) in zwei Phasen:  
  
-   [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md) oder [CComPolyObject](../atl/reference/ccompolyobject-class.md) implementiert die **IUnknown**\-Methoden.  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) verwaltet den Verweiszähler und die äußeren Zeiger von **IUnknown**.  
  
 Andere Aspekte des ATL\-COM\-Objekts werden durch andere Klassen behandelt:  
  
-   [CComCoClass](../atl/reference/ccomcoclass-class.md) definiert Standardklassendie factory des Objekts und zum Aggregationsmodell.  
  
-   [IDispatchImpl](../atl/reference/idispatchimpl-class.md) stellt eine Standardimplementierung des `IDispatch Interface` Teils aller duale Schnittstellen für das Objekt bereit.  
  
-   [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) **ISupportErrorInfo**  implementiert die Schnittstelle, die sicherstellt, dass Fehlerinformationen in der Aufrufkette ordnungsgemäß weitergegeben werden können.  
  
## In diesem Abschnitt  
 [Implementieren von CComObjectRootEx](../atl/implementing-ccomobjectrootex.md)  
 wird eine COM\-Zuordnungs\-Einträge zum Implementieren von `CComObjectRootEx`.  
  
 [Implementieren von CComObject, von CComAggObject und von CComPolyObject](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)  
 Erläutert, wie die **DECLARE\_\*\_AGGREGATABLE**\-Makros die Verwendung von `CComObject`, von `CComAggObject` und von `CComPolyObject` auswirken.  
  
 [Sichern von IDispatch und von IErrorInfo](../atl/supporting-idispatch-and-ierrorinfo.md)  
 Listet die ATL\-Implementierungsklassen auf, um zum Sichern `IDispatch` und der **IErrorInfo**\-Schnittstellen.  
  
 [Unterstützung von IDispEventImpl](../atl/supporting-idispeventimpl.md)  
 Erläutert die Schritte, um einen Verbindungspunkt für die Klasse implementieren.  
  
 [Ändern der Standardklassen\-Factorys und des Aggregations\-Modells](../atl/changing-the-default-class-factory-and-aggregation-model.md)  
 Erläutert, welche, um die Standardklassenfactory und \-Aggregation ändern zu verwenden Sie Makros modellieren.  
  
 [Erstellen eines zusammengesetzten Objekts](../atl/creating-an-aggregated-object.md)  
 Führt die Schritte zum Erstellen eines zusammengesetzten Objekts auf.  
  
## Verwandte Abschnitte  
 [Erstellen eines ATL\-Projekts](../atl/reference/creating-an-atl-project.md)  
 Stellt Informationen zum Erstellen eines ATL\-COM\-Objekts bereit.  
  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Enthält Links zu konzeptionellen Themen darüber, wie mit Active Template Library Programmierung.  
  
## Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)