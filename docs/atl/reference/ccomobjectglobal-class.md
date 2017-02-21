---
title: "CComObjectGlobal Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComObjectGlobal"
  - "ATL::CComObjectGlobal<Base>"
  - "ATL::CComObjectGlobal"
  - "ATL.CComObjectGlobal"
  - "ATL.CComObjectGlobal<Base>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObjectGlobal class"
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComObjectGlobal Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse verwaltet einen Verweiszähler für das Modul, das das `Base`\-Objekt enthält.  
  
## Syntax  
  
```  
  
      template<  
   class Base   
>  
class CComObjectGlobal :  
   public Base  
```  
  
#### Parameter  
 `Base`  
 Die Klasse, die von abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder von [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) sowie von jeder anderen Schnittstelle möchten Sie auf das Objekt unterstützen.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComObjectGlobal::CComObjectGlobal](../Topic/CComObjectGlobal::CComObjectGlobal.md)|Der \-Konstruktor.|  
|[CComObjectGlobal::~CComObjectGlobal](../Topic/CComObjectGlobal::~CComObjectGlobal.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComObjectGlobal::AddRef](../Topic/CComObjectGlobal::AddRef.md)|Implementiert globales `AddRef`.|  
|[CComObjectGlobal::QueryInterface](../Topic/CComObjectGlobal::QueryInterface.md)|Implementiert globales `QueryInterface`.|  
|[CComObjectGlobal::Release](../Topic/CComObjectGlobal::Release.md)|Implementiert globales **Release**.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CComObjectGlobal::m\_hResFinalConstruct](../Topic/CComObjectGlobal::m_hResFinalConstruct.md)|Enthält  **HRESULT**, das während der Konstruktion des `CComObjectGlobal`\-Objekts zurückgegeben wird.|  
  
## Hinweise  
 `CComObjectGlobal` verwaltet einen Verweiszähler für das Modul, das das `Base`\-Objekt enthält.  `CComObjectGlobal` stellt sicher, dass das Objekt nicht gelöscht wird, solange das Modul nicht freigegeben wird.  Das Objekt wird nur entfernt, wenn der Verweiszähler auf dem gesamten Modul auf null wechselt.  
  
 Bei Verwendung `CComObjectGlobal`, kann eine Klassenfactory ein allgemeines globales Objekt enthalten, das von allen seinen Clients freigegeben wird.  
  
## Vererbungshierarchie  
 `Base`  
  
 `CComObjectGlobal`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [CComObjectStack Class](../../atl/reference/ccomobjectstack-class.md)   
 [CComAggObject Class](../../atl/reference/ccomaggobject-class.md)   
 [CComObject Class](../../atl/reference/ccomobject-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)