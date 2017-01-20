---
title: "IUnknown Implementation Classes"
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
  - "vc.atl.Iunknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUnknown implementation classes"
ms.assetid: 47b69bb5-69d8-4a9c-84a8-329bdde2bb3f
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# IUnknown Implementation Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Klassen implementieren **IUnknown** und verwandte Methoden:  
  
-   [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) verwaltet Verweiszählung für die aggregierten und nicht aggregierten Objekte.  Ermöglicht es Ihnen, ein Threadingmodell festzulegen.  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) verwaltet Verweiszählung für die aggregierten und nicht aggregierten Objekte.  Wird das standardmäßige Threadingmodell des Servers.  
  
-   [CComAggObject](../atl/reference/ccomaggobject-class.md) implementiert **IUnknown** für ein zusammengesetztes Objekt.  
  
-   [CComObject](../atl/reference/ccomobject-class.md) implementiert **IUnknown** für ein nicht aggregiertes Objekt.  
  
-   [CComPolyObject](../atl/reference/ccompolyobject-class.md) implementiert **IUnknown** für die aggregierten und nicht aggregierten Objekte.  Verwenden `CComPolyObject` vermieden werden, `CComAggObject` und `CComObject` im Modul zu haben.  Einzelne `CComPolyObject`\-Objekthandles aggregiert und nicht aggregierte Fälle.  
  
-   [CComObjectNoLock](../atl/reference/ccomobjectnolock-class.md) implementiert **IUnknown** für ein Objekt nicht aggregiertes, ohne die Modulsperrenanzahl zu ändern.  
  
-   [CComTearOffObject](../atl/reference/ccomtearoffobject-class.md) implementiert **IUnknown** für eine Tearoff\-Schnittstelle.  
  
-   [CComCachedTearOffObject](../atl/reference/ccomcachedtearoffobject-class.md) implementiert **IUnknown** für eine "zwischengespeicherte" Tearoff\-Schnittstelle.  
  
-   [CComContainedObject](../atl/reference/ccomcontainedobject-class.md) implementiert **IUnknown** für das innere Objekt einer Aggregation oder der Tearoff\-Schnittstelle.  
  
-   [CComObjectGlobal](../atl/reference/ccomobjectglobal-class.md) erreicht einen Verweiszähler für das Modul, um sicherzustellen, dass das Objekt nicht gelöscht.  
  
-   [CComObjectStack](../atl/reference/ccomobjectstack-class.md) erstellt ein temporäres COM\-Objekt, mit einer skelettartigen Implementierung von **IUnknown**.  
  
## Verwandte Elemente  
 [Grundlagen von ATL\-COM\-Objekten](../atl/fundamentals-of-atl-com-objects.md)  
  
## Siehe auch  
 [Class Overview](../atl/atl-class-overview.md)   
 [Aggregation and Class Factory Macros](../atl/reference/aggregation-and-class-factory-macros.md)   
 [COM Map Macros](../atl/reference/com-map-macros.md)   
 [COM Map Global Functions](../atl/reference/com-map-global-functions.md)