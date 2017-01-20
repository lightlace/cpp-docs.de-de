---
title: "CComPolyObject Class"
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
  - "CComPolyObject"
  - "ATL.CComPolyObject<contained>"
  - "ATL::CComPolyObject"
  - "ATL::CComPolyObject<contained>"
  - "ATL.CComPolyObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregate objects [C++], in ATL"
  - "aggregation [C++], ATL-Objekte"
  - "CComPolyObject class"
ms.assetid: eaf67c18-e855-48ca-9b15-f1df3106121b
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CComPolyObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert **IUnknown** für ein aggregiertes oder nicht aggregiertes Objekt.  
  
## Syntax  
  
```  
  
      template<  
   class contained   
>  
class CComPolyObject : public IUnknown, public CComObjectRootEx  
   < contained::_ThreadModel::ThreadModelNoCS >  
```  
  
#### Parameter  
 `contained`  
 Die Klasse, die von abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder von [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) sowie beliebiger anderer Schnittstellen möchten Sie auf das Objekt unterstützen.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComPolyObject::CComPolyObject](../Topic/CComPolyObject::CComPolyObject.md)|Der \-Konstruktor.|  
|[CComPolyObject::~CComPolyObject](../Topic/CComPolyObject::~CComPolyObject.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComPolyObject::AddRef](../Topic/CComPolyObject::AddRef.md)|Inkrementiert den Verweiszählerwert des Objekts.|  
|[CComPolyObject::CreateInstance](../Topic/CComPolyObject::CreateInstance.md)|\(Statisch\) ermöglicht Ihnen, um ein neues Objekt **CComPolyObject\<** `contained`**\>** ohne den Mehraufwand von [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615) zu erstellen.|  
|[CComPolyObject::FinalConstruct](../Topic/CComPolyObject::FinalConstruct.md)|Führt abschließende Initialisierungsschritte von `m_contained` aus.|  
|[CComPolyObject::FinalRelease](../Topic/CComPolyObject::FinalRelease.md)|Führt endgültige Zerstörung von `m_contained` aus.|  
|[CComPolyObject::QueryInterface](../Topic/CComPolyObject::QueryInterface.md)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|  
|[CComPolyObject::Release](../Topic/CComPolyObject::Release.md)|Dekrementiert den Verweiszählerwert des Objekts.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CComPolyObject::m\_contained](../Topic/CComPolyObject::m_contained.md)|Delegaten\-**IUnknown**\-Aufrufe des äußeren Unbekannten, wenn das Objekt aggregiert wird oder zu **IUnknown** des Objekts, wenn das Objekt nicht aggregiert wird.|  
  
## Hinweise  
 `CComPolyObject` implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) für ein aggregiertes oder nicht aggregiertes Objekt.  
  
 Wenn eine Instanz von `CComPolyObject` erstellt wird, wird der Wert des äußeren Unbekannten überprüft.  Wenn es **NULL** ist, wird **IUnknown** für ein aggregiertes Objekt nicht implementiert.  Wenn das äußere Unbekannte nicht **NULL** ist, wird **IUnknown** für ein zusammengesetztes Objekt implementiert.  
  
 Der Vorteil der Verwendung von `CComPolyObject` ist, dass Sie vermeiden, [CComAggObject](../../atl/reference/ccomaggobject-class.md) und [CComObject](../../atl/reference/ccomobject-class.md) im Modul verfügen, um die aggregierten und nicht aggregierten Fälle zu behandeln.  Einzelne `CComPolyObject`\-Objekthandles beide Fälle.  Dies bedeutet, dass nur eine Kopie des vtable und eine Kopie der Funktionen im Modul vorhanden sind.  Wenn das vtable groß ist, kann dies die Modulgröße erheblich beeinträchtigt.  Wenn das vtable ist, mit `CComPolyObject` eine einige größere Modulgröße führen klein, da sie nicht für ein aggregiertes oder nicht aggregiertes Objekt optimiert wird, wie können `CComAggObject` und `CComObject`.  
  
 Wenn das `DECLARE_POLY_AGGREGATABLE`\-Makro in der Klassendefinition des Objekts angegeben wird, wird `CComPolyObject` verwendet, um das Objekt zu erstellen.  `DECLARE_POLY_AGGREGATABLE` wird automatisch deklariert, wenn Sie den ATL\-Projekt\-Assistenten verwenden, um einen Kontrolle oder ein Internet Explorer\-Steuerelement zu erstellen.  
  
 Wenn es aggregiert wird, verfügt das `CComPolyObject`\-Objekt sein eigenes **IUnknown**, getrennt von **IUnknown** des äußeren Objekts und wird ein eigener Verweiszähler bei.  `CComPolyObject` verwendet [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md), um dem äußeren Unbekannten zu delegieren.  
  
 Weitere Informationen zur Aggregation, finden Sie im Artikel [Grundlagen von ATL\-COM\-Objekten](../../atl/fundamentals-of-atl-com-objects.md).  
  
## Vererbungshierarchie  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComPolyObject`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [DECLARE\_POLY\_AGGREGATABLE](../Topic/DECLARE_POLY_AGGREGATABLE.md)   
 [Class Overview](../../atl/atl-class-overview.md)