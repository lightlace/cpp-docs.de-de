---
title: "CComObject Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComObject<Base>"
  - "ATL::CComObject"
  - "ATL::CComObject<Base>"
  - "ATL.CComObject"
  - "CComObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObject class"
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CComObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert **IUnknown** für ein nicht aggregiertes Objekt.  
  
## Syntax  
  
```  
  
      template<  
   class Base   
>  
class CComObject :  
   public Base  
```  
  
#### Parameter  
 `Base`  
 Die Klasse, die von abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder von [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) sowie beliebiger anderer Schnittstellen möchten Sie auf das Objekt unterstützen.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComObject::CComObject](../Topic/CComObject::CComObject.md)|Der \-Konstruktor.|  
|[CComObject::~CComObject](../Topic/CComObject::~CComObject.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComObject::AddRef](../Topic/CComObject::AddRef.md)|Inkrementiert den Verweiszähler für das Objekt.|  
|[CComObject::CreateInstance](../Topic/CComObject::CreateInstance.md)|\(Statisch\) erstellt ein neues `CComObject`\-Objekt.|  
|[CComObject::QueryInterface](../Topic/CComObject::QueryInterface.md)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|  
|[CComObject::Release](../Topic/CComObject::Release.md)|Dekrementiert den Verweiszähler für das Objekt.|  
  
## Hinweise  
 `CComObject` implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) für ein nicht aggregiertes Objekt.  Allerdings werden Aufrufe `QueryInterface`, zu `AddRef` und zu **Release** zu `CComObjectRootEx` delegiert.  
  
 Weitere Informationen zur Verwendung von `CComObject`, finden Sie im Artikel [Grundlagen von ATL\-COM\-Objekten](../../atl/fundamentals-of-atl-com-objects.md).  
  
## Vererbungshierarchie  
 `Base`  
  
 `CComObject`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [CComAggObject Class](../../atl/reference/ccomaggobject-class.md)   
 [CComPolyObject Class](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md)   
 [DECLARE\_NOT\_AGGREGATABLE](../Topic/DECLARE_NOT_AGGREGATABLE.md)   
 [Class Overview](../../atl/atl-class-overview.md)