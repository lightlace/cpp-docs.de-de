---
title: "CAtlList Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAtlList"
  - "CAtlList"
  - "ATL::CAtlList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlList class"
ms.assetid: 09e98053-64b2-4efa-99ab-d0542caaf981
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CAtlList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Erstellen und Verwalten eines Listenobjekts bereit.  
  
## Syntax  
  
```  
  
      template<  
   typename E,  
   class ETraits = CElementTraits< E >  
>  
class CAtlList  
```  
  
#### Parameter  
 `E`  
 Der Elementtyp.  
  
 `ETraits`  
 Der Code verwendet, um Elemente zu kopieren oder verschieben.  Siehe [CElementTraits\-Klasse](../../atl/reference/celementtraits-class.md) für weitere Details.  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlList::INARGTYPE](../Topic/CAtlList::INARGTYPE.md)||  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlList::CAtlList](../Topic/CAtlList::CAtlList.md)|Der \-Konstruktor.|  
|[CAtlList::~CAtlList](../Topic/CAtlList::~CAtlList.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlList::AddHead](../Topic/CAtlList::AddHead.md)|Rufen Sie diese Methode auf, um ein Element am Anfang der Liste hinzuzufügen.|  
|[CAtlList::AddHeadList](../Topic/CAtlList::AddHeadList.md)|Rufen Sie diese Methode auf, um eine vorhandene Liste den Kopf der Liste hinzuzufügen.|  
|[CAtlList::AddTail](../Topic/CAtlList::AddTail.md)|Rufen Sie diese Methode auf, um ein Element am Ende dieser Liste hinzuzufügen.|  
|[CAtlList::AddTailList](../Topic/CAtlList::AddTailList.md)|Rufen Sie diese Methode auf, um eine vorhandene Liste dem Ende der Liste hinzuzufügen.|  
|[CAtlList::AssertValid](../Topic/CAtlList::AssertValid.md)|Rufen Sie diese Methode auf, um die Liste zu bestätigen ist gültig.|  
|[CAtlList::Find](../Topic/CAtlList::Find.md)|Rufen Sie diese Methode auf, um die Liste für das angegebene Element zu suchen.|  
|[CAtlList::FindIndex](../Topic/CAtlList::FindIndex.md)|Rufen Sie diese Methode auf, erhält die Position eines Elements, Indexwert angegeben.|  
|[CAtlList::GetAt](../Topic/CAtlList::GetAt.md)|Rufen Sie diese Methode auf, um das Element in einer angegebenen Position in der Liste zurückgegeben.|  
|[CAtlList::GetCount](../Topic/CAtlList::GetCount.md)|Rufen Sie diese Methode auf, um die Anzahl von Objekten in der Liste zurückgegeben.|  
|[CAtlList::GetHead](../Topic/CAtlList::GetHead.md)|Rufen Sie diese Methode auf, um das Element am Anfang der Liste zurückzugeben.|  
|[CAtlList::GetHeadPosition](../Topic/CAtlList::GetHeadPosition.md)|Rufen Sie diese Methode auf, um zum Abrufen der Position des Kopfes der Liste.|  
|[CAtlList::GetNext](../Topic/CAtlList::GetNext.md)|Rufen Sie diese Methode auf, um das folgende Element aus der Liste zurückgegeben.|  
|[CAtlList::GetPrev](../Topic/CAtlList::GetPrev.md)|Rufen Sie diese Methode auf, um das vorherige Element aus der Liste zurückgegeben.|  
|[CAtlList::GetTail](../Topic/CAtlList::GetTail.md)|Rufen Sie diese Methode auf, um das Element am Ende der Liste zurückgegeben.|  
|[CAtlList::GetTailPosition](../Topic/CAtlList::GetTailPosition.md)|Rufen Sie diese Methode auf, um zum Abrufen der Position des Stapelrahmens der Liste.|  
|[CAtlList::InsertAfter](../Topic/CAtlList::InsertAfter.md)|Rufen Sie diese Methode auf, um ein neues Element in die Liste einzufügen nach den angegebenen Speicherort.|  
|[CAtlList::InsertBefore](../Topic/CAtlList::InsertBefore.md)|Rufen Sie diese Methode auf, um ein neues Element in die Liste einzufügen bevor die angegebene Position.|  
|[CAtlList::IsEmpty](../Topic/CAtlList::IsEmpty.md)|Rufen Sie diese Methode auf, um zu bestimmen, ob die Liste leer ist.|  
|[CAtlList::MoveToHead](../Topic/CAtlList::MoveToHead.md)|Rufen Sie diese Methode auf, um das angegebene Element auf den Anfang der Liste zu verschieben.|  
|[CAtlList::MoveToTail](../Topic/CAtlList::MoveToTail.md)|Rufen Sie diese Methode auf, um das angegebene Element auf das Ende der Liste zu verschieben.|  
|[CAtlList::RemoveAll](../Topic/CAtlList::RemoveAll.md)|Rufen Sie diese Methode auf, um alle Elemente aus der Liste zu entfernen.|  
|[CAtlList::RemoveAt](../Topic/CAtlList::RemoveAt.md)|Rufen Sie diese Methode auf, um ein einzelnes Element aus der Liste zu entfernen.|  
|[CAtlList::RemoveHead](../Topic/CAtlList::RemoveHead.md)|Rufen Sie diese Methode auf, um das Element am Anfang der Liste zu entfernen.|  
|[CAtlList::RemoveHeadNoReturn](../Topic/CAtlList::RemoveHeadNoReturn.md)|Rufen Sie diese Methode auf, um das Element am Anfang der Liste zu entfernen, ohne einen Wert zurückzugeben.|  
|[CAtlList::RemoveTail](../Topic/CAtlList::RemoveTail.md)|Rufen Sie diese Methode auf, um das Element am Ende der Liste zu entfernen.|  
|[CAtlList::RemoveTailNoReturn](../Topic/CAtlList::RemoveTailNoReturn.md)|Rufen Sie diese Methode auf, um das Element am Ende der Liste zu entfernen, ohne einen Wert zurückzugeben.|  
|[CAtlList::SetAt](../Topic/CAtlList::SetAt.md)|Rufen Sie diese Methode auf, um den Wert des Elements in einer angegebenen Position in der Liste.|  
|[CAtlList::SwapElements](../Topic/CAtlList::SwapElements.md)|Rufen Sie diese Methode auf, um Elemente in der Liste auszulagern.|  
  
## Hinweise  
 Die Klasse unterstützt `CAtlList` sortierte Listen von den nonunique Objekten, die sequenziell zugegriffen werden kann oder durch einen Wert.  `CAtlList` Listen verhalten sich wie doppelt verknüpfte Listen.  Jede Liste hat einen Anfang und Ende ein, und neue Elemente \(oder Listen in einigen Fällen\) können am Ende der Liste hinzugefügt werden, oder vor oder nach bestimmten Elementen eingefügt werden.  
  
 Die meisten `CAtlList`\-Methoden nutzen einen Positionswert aus.  Dieser Wert wird durch die Methoden verwendet, um die eigentliche Speicheradresse zu verweisen, in der die Elemente gespeichert werden, und sollte nicht direkt abgeleitet werden oder vorhergesagt werden.  Wenn es erforderlich ist, auf das *n\-te*\-Element in der Liste zuzugreifen, gibt die Methode [CAtlList::FindIndex](../Topic/CAtlList::FindIndex.md) den entsprechenden Positionswert für einen angegebenen Index zurück.  Die Methoden [CAtlList::GetNext](../Topic/CAtlList::GetNext.md) und [CAtlList::GetPrev](../Topic/CAtlList::GetPrev.md) können verwendet werden, um durch die Objekte in der Liste zu durchlaufen.  
  
 Weitere Informationen zu den Auflistungsklassen, die mit ATL verfügbar sind, finden Sie unter [ATL\-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## Anforderungen  
 **Header:** atlcoll.h  
  
## Siehe auch  
 [CList Class](../../mfc/reference/clist-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)