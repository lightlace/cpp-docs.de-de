---
title: "CComCachedTearOffObject Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComCachedTearOffObject"
  - "ATL.CComCachedTearOffObject"
  - "ATL.CComCachedTearOffObject<contained>"
  - "CComCachedTearOffObject"
  - "ATL::CComCachedTearOffObject<contained>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Cache, ATL cached tear-off objects"
  - "CComCachedTearOffObject class"
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComCachedTearOffObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) für eine Tearoff\-Schnittstelle.  
  
## Syntax  
  
```  
  
      template <  
   class contained  
>  
class CComCachedTearOffObject : public IUnknown,  
   public CComObjectRootEx< contained::_ThreadModel::ThreadModelNoCS >  
```  
  
#### Parameter  
 `contained`  
 Tearoffe die Klasse, abgeleitet von `CComTearOffObjectBase` und Schnittstellen möchten Sie das Tearoffes Objekt zur Unterstützung.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComCachedTearOffObject::CComCachedTearOffObject](../Topic/CComCachedTearOffObject::CComCachedTearOffObject.md)|Der \-Konstruktor.|  
|[CComCachedTearOffObject::~CComCachedTearOffObject](../Topic/CComCachedTearOffObject::~CComCachedTearOffObject.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComCachedTearOffObject::AddRef](../Topic/CComCachedTearOffObject::AddRef.md)|Inkrementiert den Verweiszähler für ein `CComCachedTearOffObject`\-Objekt.|  
|[CComCachedTearOffObject::FinalConstruct](../Topic/CComCachedTearOffObject::FinalConstruct.md)|Ruft `m_contained::FinalConstruct` auf \(die Tearoffe Methode der Klassen\).|  
|[CComCachedTearOffObject::FinalRelease](../Topic/CComCachedTearOffObject::FinalRelease.md)|Ruft `m_contained::FinalRelease` auf \(die Tearoffe Methode der Klassen\).|  
|[CComCachedTearOffObject::QueryInterface](../Topic/CComCachedTearOffObject::QueryInterface.md)|Gibt einen Zeiger auf `IUnknown``CComCachedTearOffObject` des Objekts oder die angeforderte Schnittstelle in der Klasse Tearoffen zurück \(die Klasse `contained`\).|  
|[CComCachedTearOffObject::Release](../Topic/CComCachedTearOffObject::Release.md)|Dekrementiert den Verweiszähler für ein Objekt `CComCachedTearOffObject` und ihn zerstört, wenn der Verweiszähler 0 ist.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CComCachedTearOffObject::m\_contained](../Topic/CComCachedTearOffObject::m_contained.md)|Ein `CComContainedObject`\-Objekt abgeleitet von der Tearoffen Klasse \(die Klasse `contained`\).|  
  
## Hinweise  
 `CComCachedTearOffObject` implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) für eine Tearoff\-Schnittstelle.  Diese Klasse unterscheidet sich von `CComTearOffObject` darin, dass `CComCachedTearOffObject` sein eigenes **IUnknown** verfügt, getrennt von **IUnknown** des Besitzersobjekts \(Besitzer ist das Objekt, für das das Tearoff erstellt wird\).  `CComCachedTearOffObject` wird ein eigener Verweiszähler auf dem **IUnknown** bei und gelöscht, sobald sich sein Zähler auf Null ist.  Wenn Sie jedoch für seine Tearoff\-Schnittstellen abfragen, wird der Verweiszähler von **IUnknown** des Besitzersobjekts erhöht.  
  
 Wenn das `CComCachedTearOffObject`\-Objekt, das das Tearoff implementiert, bereits instanziiert und die Tearoff\-Schnittstelle für erneut abgefragt wird, wird das gleiche Objekt `CComCachedTearOffObject` wiederverwendet.  Wenn eine Tearoff\-Schnittstelle, die von `CComTearOffObject` implementiert wird, erneut für durch das Besitzersobjekt abgefragt wird, wird ein anderes `CComTearOffObject` instanziiert.  
  
 Die Besitzerklasse muss `FinalRelease` implementieren und **Release** auf zwischengespeicherten **IUnknown** für `CComCachedTearOffObject` aufrufen, die den Verweiszähler heruntergesetzt.  Dadurch wird `FinalRelease` von `CComCachedTearOffObject` aufgerufen und das Tearoff gelöscht.  
  
## Vererbungshierarchie  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComCachedTearOffObject`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [CComTearOffObject Class](../../atl/reference/ccomtearoffobject-class.md)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)