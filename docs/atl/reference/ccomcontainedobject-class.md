---
title: "CComContainedObject Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComContainedObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregate objects [C++], in ATL"
  - "aggregation [C++], ATL-Objekte"
  - "CComContainedObject class"
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CComContainedObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), indem auf **IUnknown** des Besitzersobjekts delegiert.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template<  
class Base   
>  
class CComContainedObject :  
public Base  
```  
  
#### Parameter  
 `Base`  
 Die Klasse, die von abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder von [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md).  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComContainedObject::CComContainedObject](../Topic/CComContainedObject::CComContainedObject.md)|Der \-Konstruktor.  Initialisiert den Memberzeiger zu `IUnknown` des Besitzersobjekts.|  
|[CComContainedObject::~CComContainedObject](../Topic/CComContainedObject::~CComContainedObject.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComContainedObject::AddRef](../Topic/CComContainedObject::AddRef.md)|Inkrementiert den Verweiszähler für das Besitzersobjekt.|  
|[CComContainedObject::GetControllingUnknown](../Topic/CComContainedObject::GetControllingUnknown.md)|Ruft `IUnknown` des Besitzersobjekts ab.|  
|[CComContainedObject::QueryInterface](../Topic/CComContainedObject::QueryInterface.md)|Ruft einen Zeiger auf die Schnittstelle ab, die auf dem Besitzersobjekt angefordert wird.|  
|[CComContainedObject::Release](../Topic/CComContainedObject::Release.md)|Dekrementiert den Verweiszähler für das Besitzersobjekt.|  
  
## Hinweise  
 ATL verwendet `CComContainedObject` in Klassen [CComAggObject](../../atl/reference/ccomaggobject-class.md), [CComPolyObject](../../atl/reference/ccompolyobject-class.md) und [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md).  `CComContainedObject` implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), indem es **IUnknown** des Besitzersobjekts delegiert.  \(Der Besitzer ist entweder das äußere Objekt einer Aggregation, oder das Objekt, für das eine Tearoff\-Schnittstelle. erstellt wird.\) `CComContainedObject` ruft `OuterQueryInterface`, `OuterAddRef` und `OuterRelease` von `CComObjectRootEx` auf, die alle durch `Base` geerbt wurden.  
  
## Vererbungshierarchie  
 `Base`  
  
 `CComContainedObject`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)