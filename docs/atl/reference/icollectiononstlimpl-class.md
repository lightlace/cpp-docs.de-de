---
title: "ICollectionOnSTLImpl Class"
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
  - "ATL.ICollectionOnSTLImpl"
  - "ATL::ICollectionOnSTLImpl"
  - "ICollectionOnSTLImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICollectionOnSTLImpl class"
ms.assetid: 683c88b0-0d97-4779-a762-e493334ba7f9
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# ICollectionOnSTLImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt die Methoden, die durch eine Auflistungsklasse verwendet werden.  
  
## Syntax  
  
```  
  
      template <  
   class T,  
   class CollType,  
   class ItemType,  
   class CopyItem,  
   class EnumType  
>  
class ICollectionOnSTLImpl :  
   public T  
```  
  
#### Parameter  
 `T`  
 Eine COM\-Auflistungsschnittstelle.  
  
 `CollType`  
 Eine STL\-Containerklasse.  
  
 *ItemType*  
 Der Typ des Elements verfügbar gemacht die Containerschnittstelle.  
  
 *CopyItem*  
 [Kopierrichtlinienklasse](../../atl/atl-copy-policy-classes.md).  
  
 *EnumType*  
 [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)\- kompatiblen Enumeratorklasse.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[ICollectionOnSTLImpl::get\_\_NewEnum](../Topic/ICollectionOnSTLImpl::get__NewEnum.md)|Gibt ein Enumeratorobjekt für die Auflistung zurück.|  
|[ICollectionOnSTLImpl::get\_Count](../Topic/ICollectionOnSTLImpl::get_Count.md)|Gibt die Anzahl der Elemente in der Auflistung zurück.|  
|[ICollectionOnSTLImpl::get\_Item](../Topic/ICollectionOnSTLImpl::get_Item.md)|Gibt das angeforderte Element aus der Auflistung zurück.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[ICollectionOnSTLImpl::m\_coll](../Topic/ICollectionOnSTLImpl::m_coll.md)|Die Auflistung.|  
  
## Hinweise  
 Diese Klasse stellt die Implementierung für drei Methoden einer Auflistungsschnittstelle bereit: [get\_Count](../Topic/ICollectionOnSTLImpl::get_Count.md), [get\_Item](../Topic/ICollectionOnSTLImpl::get_Item.md) und [get\_\_NewEnum](../Topic/ICollectionOnSTLImpl::get__NewEnum.md).  
  
 Um diese Klasse verwenden:  
  
-   Definieren Sie \(oder\) Bürgschaft eine Auflistungsschnittstelle, die Sie implementieren möchten.  
  
-   Leiten Sie die Klasse von einer Spezialisierung von `ICollectionOnSTLImpl` auf Grundlage dieser Auflistungsschnittstelle.  
  
-   Verwenden Sie die abgeleitete Klasse, um alle Methoden von der Auflistungsschnittstelle zu implementieren, die nicht von `ICollectionOnSTLImpl` behandelt wird.  
  
> [!NOTE]
>  Wenn die Auflistungsschnittstelle eine duale Schnittstelle ist, leiten Sie die Klasse von [IDispatchImpl](../../atl/reference/idispatchimpl-class.md) und die `ICollectionOnSTLImpl` Spezialisierung als der erste Vorlagenparameter übergeben, wenn Sie ATL die Implementierung der `IDispatch`\-Methoden bereitstellen möchten.  
  
-   Fügen Sie Elemente dem [m\_coll](../Topic/ICollectionOnSTLImpl::m_coll.md)\-Member hinzu, um die Auflistung zu füllen.  
  
 Weitere Informationen und Beispiele finden Sie unter [ATL\-Auflistungen und \-Enumeratoren](../../atl/atl-collections-and-enumerators.md).  
  
## Vererbungshierarchie  
 `T`  
  
 `ICollectionOnSTLImpl`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [ATLCollections\-Beispiel](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)