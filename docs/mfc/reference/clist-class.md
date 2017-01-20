---
title: "CList Class"
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
  - "CList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CList class"
  - "Listen"
  - "Listen, base class for"
ms.assetid: 6f6273c3-c8f6-47f5-ac2a-0a950379ae5d
caps.latest.revision: 23
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unterstützt den nonunique sortierte Listen von Objekten, die sequenziell zugegriffen werden kann oder durch einen Wert.  
  
## Syntax  
  
```  
template< class TYPE, class ARG_TYPE = const TYPE& >   
class CList : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CList::CList](../Topic/CList::CList.md)|Erstellt eine leere sortierte Liste.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CList::AddHead](../Topic/CList::AddHead.md)|Fügt ein Element \(oder alle Elemente in anderen Liste\) den Kopf der Liste hinzu \(erstellt einen neuen Kopf erstellt\).|  
|[CList::AddTail](../Topic/CList::AddTail.md)|Fügt ein Element \(oder alle Elemente in anderen Liste\) dem Ende der Liste hinzu \(erstellt ein neues Ende erstellt\).|  
|[CList::Find](../Topic/CList::Find.md)|Ruft die Position eines Elements ab, das von Zeigerwert angegeben wird.|  
|[CList::FindIndex](../Topic/CList::FindIndex.md)|Ruft die Position eines Elements ab, das durch einen nullbasierten Index angegeben wird.|  
|[CList::GetAt](../Topic/CList::GetAt.md)|Ruft das Element in einer angegebenen Position ab.|  
|[CList::GetCount](../Topic/CList::GetCount.md)|Gibt die Anzahl von Elementen in dieser Liste zurück.|  
|[CList::GetHead](../Topic/CList::GetHead.md)|Gibt das Anfangselement der Liste zurück \(kann nicht leer sein\).|  
|[CList::GetHeadPosition](../Topic/CList::GetHeadPosition.md)|Gibt die Position des Anfangselements der Liste zurück.|  
|[CList::GetNext](../Topic/CList::GetNext.md)|Ruft das folgende Element zum Durchlaufen ab.|  
|[CList::GetPrev](../Topic/CList::GetPrev.md)|Ruft das vorherige Element zum Durchlaufen ab.|  
|[CList::GetSize](../Topic/CList::GetSize.md)|Gibt die Anzahl von Elementen in dieser Liste zurück.|  
|[CList::GetTail](../Topic/CList::GetTail.md)|Gibt das Endeelement der Liste zurück \(kann nicht leer sein\).|  
|[CList::GetTailPosition](../Topic/CList::GetTailPosition.md)|Gibt die Position des Endeelements der Liste zurück.|  
|[CList::InsertAfter](../Topic/CList::InsertAfter.md)|Fügt ein neues Element nach einer angegebenen Position ein.|  
|[CList::InsertBefore](../Topic/CList::InsertBefore.md)|Fügt ein neues Element vor einer angegebenen Position ein.|  
|[CList::IsEmpty](../Topic/CList::IsEmpty.md)|Tests für die leere Listenzustand \(keine Elemente\).|  
|[CList::RemoveAll](../Topic/CList::RemoveAll.md)|Entfernt alle Elemente aus dieser Liste.|  
|[CList::RemoveAt](../Topic/CList::RemoveAt.md)|Entfernt ein Element aus dieser Liste, die durch Position angegeben ist.|  
|[CList::RemoveHead](../Topic/CList::RemoveHead.md)|Entfernt das Element aus dem Anfang der Liste.|  
|[CList::RemoveTail](../Topic/CList::RemoveTail.md)|Entfernt das Element aus dem Ende der Liste.|  
|[CList::SetAt](../Topic/CList::SetAt.md)|Legt das Element in einer angegebenen Position fest.|  
  
#### Parameter  
 `TYPE`  
 Typ des Objekts in der Liste.  
  
 `ARG` *\_* `TYPE`  
 Geben Sie verwendet, um die Objekte zu verweisen, die in der Liste gespeichert werden.  Kann ein Verweis.  
  
## Hinweise  
 `CList` Listen verhalten sich wie doppelt\-verknüpfte Listen.  
  
 Eine Variable vom Typ **POSITION** ist eine Schlüssel für die Liste.  Sie können eine **POSITION**\-Variable als Iterator, um eine Liste sequenziell zu durchlaufen und als Lesezeichen verwenden, um einen Ort aufzunehmen.  Eine Position ist nicht identisch mit einem Index, jedoch.  
  
 Elementeinfügung ist sehr schnell am Listenkopf, am Ende bei bekannten **POSITION**.  Eine sequenzielle Suche ist erforderlich, um ein Element als Wert oder Index gesucht wird.  Diese Suche kann langsam sein, wenn die Liste lang ist.  
  
 Wenn Sie eine Dumpdatei einzelner Elemente in der Liste benötigen, müssen Sie die Tiefe des Dumpkontexts auf 1 festlegen oder größer ist.  
  
 Bestimmte Memberfunktionen dieser Klasse rufen globale Hilfsfunktionen auf, die für die meisten Verwendungsmöglichkeiten der Klasse `CList` angepasst werden müssen.  Siehe [Auflistungsklassen\-Hilfen](../../mfc/reference/collection-class-helpers.md) im "Makro\- und Werte" Abschnitt.  
  
 Weitere Informationen zur Verwendung von `CList`, finden Sie im Artikel [Auflistungen](../../mfc/collections.md).  
  
## Beispiel  
 [!CODE [NVC_MFCCollections#35](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#35)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CList`  
  
## Anforderungen  
 **Header:**  afxtempl.h  
  
## Siehe auch  
 [MFC\-Beispiel COLLECT](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMap Class](../../mfc/reference/cmap-class.md)   
 [CArray Class](../../mfc/reference/carray-class.md)