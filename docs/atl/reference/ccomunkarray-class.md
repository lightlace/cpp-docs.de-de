---
title: "CComUnkArray Class"
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
  - "ATL.CComUnkArray"
  - "ATL.CComUnkArray<nMaxSize>"
  - "ATL::CComUnkArray<nMaxSize>"
  - "ATL::CComUnkArray"
  - "CComUnkArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComUnkArray class"
  - "Verbindungspunkte [C++], Verwalten"
ms.assetid: 5fd4b378-a7b5-4cc1-8866-8ab72a73639e
caps.latest.revision: 17
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# CComUnkArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse speichert **IUnknown** Zeiger und sind so konzipiert, als Parameter an die [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) Vorlagenklasse verwendet werden.  
  
## Syntax  
  
```  
template<  
   unsigned int nMaxSize  
>  
class CComUnkArray  
```  
  
#### Parameter  
 *nMaxSize*  
 Die maximale Anzahl von **IUnknown** Zeigern, die im statischen Array verwendet werden können.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComUnkArray::CComUnkArray](../Topic/CComUnkArray::CComUnkArray.md)|Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComUnkArray::Add](../Topic/CComUnkArray::Add.md)|Rufen Sie diese Methode auf, um einen Zeiger **IUnknown** dem Array hinzuzufügen.|  
|[CComUnkArray::begin](../Topic/CComUnkArray::begin.md)|Gibt einen Zeiger auf den ersten **IUnknown** Zeiger in der Auflistung zurück.|  
|[CComUnkArray::end](../Topic/CComUnkArray::end.md)|Gibt einen Zeiger auf eine Vergangenheit der letzte **IUnknown** Zeiger in der Auflistung zurück.|  
|[CComUnkArray::GetCookie](../Topic/CComUnkArray::GetCookie.md)|Rufen Sie diese Methode auf, um das Cookie abzurufen, das mit einem angegebenen **IUnknown** Zeiger zugeordnet ist.|  
|[CComUnkArray::GetUnknown](../Topic/CComUnkArray::GetUnknown.md)|Rufen Sie diese Methode auf, um den **IUnknown** Zeiger abzurufen, der mit einem angegebenen Cookies zugeordnet ist.|  
|[CComUnkArray::Remove](../Topic/CComUnkArray::Remove.md)|Rufen Sie diese Methode auf, um einen Zeiger **IUnknown** aus dem Array zu entfernen.|  
  
## Hinweise  
 **CComUnkArray** enthält eine feste Anzahl von **IUnknown** Zeiger an, jede eine Schnittstelle in einem Verbindungspunkt.  **CComUnkArray** kann als Parameter an die [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) Vorlagenklasse verwendet werden.  **CComUnkArray\<1\>** ist eine Vorlagenspezialisierung von **CComUnkArray**, die für einen Verbindungspunkt optimiert wurde.  
  
 Die **CComUnkArray**\-Methoden [Starten Sie](../Topic/CComUnkArray::begin.md) und [Ende](../Topic/CComUnkArray::end.md) können verwendet werden, um durch alle Verbindungspunkte durchlaufen werden \(beispielsweise, wenn ein Ereignis ausgelöst wird.\)  
  
 Siehe [Adding Connection Points to an Object](../../atl/adding-connection-points-to-an-object.md) für Informationen zum Automatisieren der Erstellung der Verbindungspunktproxy.  
  
> [!NOTE]
>  **Hinweis** die Klasse [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md) wird vom Assistenten **Klasse hinzufügen** verwendet, wenn Sie ein Steuerelement erstellen, das Verbindungspunkte verfügt.  Wenn Sie die Anzahl von Verbindungspunkten manuell angeben möchten, ändern Sie den Verweis aus **CComDynamicUnkArray** zu `CComUnkArray<``>`*n* , wobei *n* die Anzahl der erforderlichen Verbindungspunkten ist.  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [CComDynamicUnkArray Class](../../atl/reference/ccomdynamicunkarray-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)