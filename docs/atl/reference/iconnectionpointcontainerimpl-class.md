---
title: "IConnectionPointContainerImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::IConnectionPointContainerImpl"
  - "ATL.IConnectionPointContainerImpl"
  - "ATL.IConnectionPointContainerImpl<T>"
  - "IConnectionPointContainerImpl"
  - "ATL::IConnectionPointContainerImpl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "connectable objects"
  - "Verbindungspunkte [C++], container"
  - "IConnectionPointContainerImpl class"
ms.assetid: 10db5a8d-8be9-4d9d-8a82-8ab9ffe3e9d6
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# IConnectionPointContainerImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert einen Verbindungspunktcontainer, um eine Auflistung [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)\-Objekte zu verwalten.  
  
## Syntax  
  
```  
  
      template<  
   class T   
>  
class ATL_NO_VTABLE IConnectionPointContainerImpl :   
   public IConnectionPointContainer  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `IConnectionPointContainerImpl`.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IConnectionPointContainerImpl::EnumConnectionPoints](../Topic/IConnectionPointContainerImpl::EnumConnectionPoints.md)|Erstellt einen Enumerator, um die Verbindungspunkte zu durchlaufen, die in das verbindungsfähige Objekt unterstützt werden.|  
|[IConnectionPointContainerImpl::FindConnectionPoint](../Topic/IConnectionPointContainerImpl::FindConnectionPoint.md)|Ruft einen Schnittstellenzeiger an den Verbindungspunkt ab, der das angegebene IID unterstützt.|  
  
## Hinweise  
 `IConnectionPointContainerImpl` implementiert einen Verbindungspunktcontainer, um eine Auflistung [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)\-Objekte zu verwalten.  `IConnectionPointContainerImpl` stellt zwei Methoden, die ein Client aufrufen können, um weitere Informationen über ein verbindungsfähiges Objekt abzurufen:  
  
-   `EnumConnectionPoints` ermöglicht es dem Client, um zu bestimmen, welche Ausgangsschnittstellen das Objekt unterstützt.  
  
-   `FindConnectionPoint` ermöglicht es dem Client, um zu bestimmen, ob das Objekt eine bestimmte Ausgangsschnittstelle unterstützt.  
  
 Informationen zur Verwendung von Verbindungspunkten in ATL, finden Sie im Artikel [Verbindungspunkte](../../atl/atl-connection-points.md).  
  
## Vererbungshierarchie  
 `IConnectionPointContainer`  
  
 `IConnectionPointContainerImpl`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)   
 [Class Overview](../../atl/atl-class-overview.md)