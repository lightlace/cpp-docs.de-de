---
title: "CComDynamicUnkArray Class"
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
  - "ATL.CComDynamicUnkArray"
  - "CComDynamicUnkArray"
  - "ATL::CComDynamicUnkArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComDynamicUnkArray class"
  - "Verbindungspunkte [C++], Verwalten"
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
caps.latest.revision: 17
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# CComDynamicUnkArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse speichert ein Array **IUnknown** Zeiger.  
  
## Syntax  
  
```  
class CComDynamicUnkArray  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComDynamicUnkArray::CComDynamicUnkArray](../Topic/CComDynamicUnkArray::CComDynamicUnkArray.md)|Konstruktor.  Initialisiert die Auflistungswerte zu **NULL** und die Auflistungsgröße auf Null fest.|  
|[CComDynamicUnkArray::~CComDynamicUnkArray](../Topic/CComDynamicUnkArray::~CComDynamicUnkArray.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComDynamicUnkArray::Add](../Topic/CComDynamicUnkArray::Add.md)|Rufen Sie diese Methode auf, um einen Zeiger `IUnknown` dem Array hinzuzufügen.|  
|[CComDynamicUnkArray::begin](../Topic/CComDynamicUnkArray::begin.md)|Gibt einen Zeiger auf den ersten `IUnknown` Zeiger in der Auflistung zurück.|  
|[CComDynamicUnkArray::clear](../Topic/CComDynamicUnkArray::clear.md)|Leert das Array.|  
|[CComDynamicUnkArray::end](../Topic/CComDynamicUnkArray::end.md)|Gibt einen Zeiger auf eine Vergangenheit der letzte **IUnknown** Zeiger in der Auflistung zurück.|  
|[CComDynamicUnkArray::GetAt](../Topic/CComDynamicUnkArray::GetAt.md)|Entfernt das Element am angegebenen Index.|  
|[CComDynamicUnkArray::GetCookie](../Topic/CComDynamicUnkArray::GetCookie.md)|Rufen Sie diese Methode auf, um das Cookie abzurufen, das mit einem angegebenen **IUnknown** Zeiger zugeordnet ist.|  
|[CComDynamicUnkArray::GetSize](../Topic/CComDynamicUnkArray::GetSize.md)|Gibt die Länge eines Arrays zurück.|  
|[CComDynamicUnkArray::GetUnknown](../Topic/CComDynamicUnkArray::GetUnknown.md)|Rufen Sie diese Methode auf, um den **IUnknown** Zeiger abzurufen, der mit einem angegebenen Cookies zugeordnet ist.|  
|[CComDynamicUnkArray::Remove](../Topic/CComDynamicUnkArray::Remove.md)|Rufen Sie diese Methode auf, um einen Zeiger **IUnknown** aus dem Array zu entfernen.|  
  
## Hinweise  
 **CComDynamicUnkArray** enthält ein Array dynamisch zugeordnete **IUnknown** Zeiger an, jedes eine Schnittstelle in einem Verbindungspunkt.  **CComDynamicUnkArray** kann als Parameter an die [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) Vorlagenklasse verwendet werden.  
  
 Die **CComDynamicUnkArray**\-Methoden [Starten Sie](../Topic/CComDynamicUnkArray::begin.md) und [Ende](../Topic/CComDynamicUnkArray::end.md) können verwendet werden, um durch alle Verbindungspunkte durchlaufen werden \(beispielsweise, wenn ein Ereignis ausgelöst wird.\)  
  
 Siehe [Adding Connection Points to an Object](../../atl/adding-connection-points-to-an-object.md) für Informationen zum Automatisieren der Erstellung der Verbindungspunktproxy.  
  
> [!NOTE]
>  **Hinweis** die Klasse **CComDynamicUnkArray** wird vom Assistenten **Klasse hinzufügen** verwendet, wenn Sie ein Steuerelement erstellen, das Verbindungspunkte verfügt.  Wenn Sie die Anzahl von Verbindungspunkten manuell angeben möchten, ändern Sie den Verweis aus **CComDynamicUnkArray** zu `CComUnkArray<``>`*n* , wobei *n* die Anzahl der erforderlichen Verbindungspunkten ist.  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [CComUnkArray Class](../../atl/reference/ccomunkarray-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)