---
title: "CComAggObject Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComAggObject<contained>"
  - "ATL.CComAggObject"
  - "ATL.CComAggObject<contained>"
  - "CComAggObject"
  - "ATL::CComAggObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregate objects [C++], in ATL"
  - "aggregation [C++], ATL-Objekte"
  - "CComAggObject class"
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CComAggObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert die Schnittstelle [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) für ein zusammengesetztes Objekt.  Definitionsgemäß ist ein zusammengesetztes Objekt innerhalb eines äußeren Objekts enthalten.  Die Klasse ist `CComAggObject` zu [CComObject Class](../../atl/reference/ccomobject-class.md) vergleichbar, außer dass sie eine Schnittstelle verfügbar macht die direkt für Clients verfügbar ist.  
  
## Syntax  
  
```  
  
      template<  
   class contained  
>  
class CComAggObject :  
   public IUnknown, public CComObjectRootEx  
   < contained::_ThreadModel::ThreadModelNoCS >  
```  
  
#### Parameter  
 `contained`  
 Die Klasse, die von abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder von [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) sowie beliebiger anderer Schnittstellen möchten Sie auf das Objekt unterstützen.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComAggObject::CComAggObject](../Topic/CComAggObject::CComAggObject.md)|Der \-Konstruktor.|  
|[CComAggObject::~CComAggObject](../Topic/CComAggObject::~CComAggObject.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComAggObject::AddRef](../Topic/CComAggObject::AddRef.md)|Inkrementiert den Verweiszähler für das zusammengesetzten Objekt.|  
|[CComAggObject::CreateInstance](../Topic/CComAggObject::CreateInstance.md)|Diese statische Funktion ermöglicht es Ihnen, ein neues Objekt **CComAggObject\<** `contained`**\>** ohne den Mehraufwand von [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615) zu erstellen.|  
|[CComAggObject::FinalConstruct](../Topic/CComAggObject::FinalConstruct.md)|Führt abschließende Initialisierungsschritte von `m_contained` aus.|  
|[CComAggObject::FinalRelease](../Topic/CComAggObject::FinalRelease.md)|Führt endgültige Zerstörung von `m_contained` aus.|  
|[CComAggObject::QueryInterface](../Topic/CComAggObject::QueryInterface.md)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|  
|[CComAggObject::Release](../Topic/CComAggObject::Release.md)|Dekrementiert den Verweiszähler für das zusammengesetzten Objekt.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CComAggObject::m\_contained](../Topic/CComAggObject::m_contained.md)|Delegaten\-`IUnknown`\-Aufrufe des äußeren Unbekannten.|  
  
## Hinweise  
 `CComAggObject` implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) für ein zusammengesetztes Objekt.  `CComAggObject` verfügt über eine eigene **IUnknown**\-Schnittstelle, getrennt von der äußeren **IUnknown**\-Schnittstelle des Objekts und wird ein eigener Verweiszähler bei.  
  
 Weitere Informationen zur Aggregation, finden Sie im Artikel [Grundlagen von ATL\-COM\-Objekten](../../atl/fundamentals-of-atl-com-objects.md).  
  
## Vererbungshierarchie  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComAggObject`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [CComObject Class](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject Class](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md)   
 [DECLARE\_ONLY\_AGGREGATABLE](../Topic/DECLARE_ONLY_AGGREGATABLE.md)   
 [DECLARE\_NOT\_AGGREGATABLE](../Topic/DECLARE_NOT_AGGREGATABLE.md)   
 [Class Overview](../../atl/atl-class-overview.md)