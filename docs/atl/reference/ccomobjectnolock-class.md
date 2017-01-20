---
title: "CComObjectNoLock Class"
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
  - "ATL.CComObjectNoLock"
  - "ATL::CComObjectNoLock"
  - "ATL.CComObjectNoLock<Base>"
  - "CComObjectNoLock"
  - "ATL::CComObjectNoLock<Base>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObjectNoLock class"
ms.assetid: 288c6506-7da8-4127-8d58-7f4bd779539a
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CComObjectNoLock Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert **IUnknown** für ein nicht aggregiertes Objekt, aber nicht erhöht die Modulsperrenanzahl im Konstruktor.  
  
## Syntax  
  
```  
  
      template<  
   class Base   
>  
class CComObjectNoLock :  
   public Base  
```  
  
#### Parameter  
 `Base`  
 Die Klasse, die von abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder von [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) sowie von jeder anderen Schnittstelle möchten Sie auf das Objekt unterstützen.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComObjectNoLock::CComObjectNoLock](../Topic/CComObjectNoLock::CComObjectNoLock.md)|Konstruktor.|  
|[CComObjectNoLock::~CComObjectNoLock](../Topic/CComObjectNoLock::~CComObjectNoLock.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComObjectNoLock::AddRef](../Topic/CComObjectNoLock::AddRef.md)|Inkrementiert den Verweiszähler für das Objekt.|  
|[CComObjectNoLock::QueryInterface](../Topic/CComObjectNoLock::QueryInterface.md)|Gibt einen Zeiger auf die angeforderte Schnittstelle zurück.|  
|[CComObjectNoLock::Release](../Topic/CComObjectNoLock::Release.md)|Dekrementiert den Verweiszähler für das Objekt.|  
  
## Hinweise  
 `CComObjectNoLock` ist zu [CComObject](../../atl/reference/ccomobject-class.md) insofern ähnlich, dass es [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) für ein nicht aggregiertes Objekt implementiert; `CComObjectNoLock` erhöht jedoch nicht die Modulsperrenanzahl im Konstruktor.  
  
 ATL verwendet `CComObjectNoLock` intern für Class Factory.  Im Allgemeinen verwenden Sie diese Klasse nicht direkt.  
  
## Vererbungshierarchie  
 `Base`  
  
 `CComObjectNoLock`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)