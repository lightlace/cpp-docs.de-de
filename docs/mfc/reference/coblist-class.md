---
title: "CObList Class"
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
  - "CObList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CObList class"
  - "Listen, object"
  - "Objekte [C++], lists of"
ms.assetid: 80699c93-33d8-4f8b-b8cf-7b58aeab64ca
caps.latest.revision: 20
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CObList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unterstützt sortierte Listen von nonunique `CObject` Zeigern, die sequenziell zugegriffen werden kann oder durch Zeigerwert.  
  
## Syntax  
  
```  
class CObList : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CObList::CObList](../Topic/CObList::CObList.md)|Erstellt eine leere Liste für `CObject` Zeiger.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CObList::AddHead](../Topic/CObList::AddHead.md)|Fügt ein Element \(oder alle Elemente in anderen Liste\) den Kopf der Liste hinzu \(erstellt einen neuen Kopf erstellt\).|  
|[CObList::AddTail](../Topic/CObList::AddTail.md)|Fügt ein Element \(oder alle Elemente in anderen Liste\) dem Ende der Liste hinzu \(erstellt ein neues Ende erstellt\).|  
|[CObList::Find](../Topic/CObList::Find.md)|Ruft die Position eines Elements ab, das von Zeigerwert angegeben wird.|  
|[CObList::FindIndex](../Topic/CObList::FindIndex.md)|Ruft die Position eines Elements ab, das durch einen nullbasierten Index angegeben wird.|  
|[CObList::GetAt](../Topic/CObList::GetAt.md)|Ruft das Element in einer angegebenen Position ab.|  
|[CObList::GetCount](../Topic/CObList::GetCount.md)|Gibt die Anzahl von Elementen in dieser Liste zurück.|  
|[CObList::GetHead](../Topic/CObList::GetHead.md)|Gibt das Anfangselement der Liste zurück \(kann nicht leer sein\).|  
|[CObList::GetHeadPosition](../Topic/CObList::GetHeadPosition.md)|Gibt die Position des Anfangselements der Liste zurück.|  
|[CObList::GetNext](../Topic/CObList::GetNext.md)|Ruft das folgende Element zum Durchlaufen ab.|  
|[CObList::GetPrev](../Topic/CObList::GetPrev.md)|Ruft das vorherige Element zum Durchlaufen ab.|  
|[CObList::GetSize](../Topic/CObList::GetSize.md)|Gibt die Anzahl von Elementen in dieser Liste zurück.|  
|[CObList::GetTail](../Topic/CObList::GetTail.md)|Gibt das Endeelement der Liste zurück \(kann nicht leer sein\).|  
|[CObList::GetTailPosition](../Topic/CObList::GetTailPosition.md)|Gibt die Position des Endeelements der Liste zurück.|  
|[CObList::InsertAfter](../Topic/CObList::InsertAfter.md)|Fügt ein neues Element nach einer angegebenen Position ein.|  
|[CObList::InsertBefore](../Topic/CObList::InsertBefore.md)|Fügt ein neues Element vor einer angegebenen Position ein.|  
|[CObList::IsEmpty](../Topic/CObList::IsEmpty.md)|Tests für die leere Listenzustand \(keine Elemente\).|  
|[CObList::RemoveAll](../Topic/CObList::RemoveAll.md)|Entfernt alle Elemente aus dieser Liste.|  
|[CObList::RemoveAt](../Topic/CObList::RemoveAt.md)|Entfernt ein Element aus dieser Liste, die durch Position angegeben ist.|  
|[CObList::RemoveHead](../Topic/CObList::RemoveHead.md)|Entfernt das Element aus dem Anfang der Liste.|  
|[CObList::RemoveTail](../Topic/CObList::RemoveTail.md)|Entfernt das Element aus dem Ende der Liste.|  
|[CObList::SetAt](../Topic/CObList::SetAt.md)|Legt das Element in einer angegebenen Position fest.|  
  
## Hinweise  
 `CObList` Listen verhalten sich wie doppelt\-verknüpfte Listen.  
  
 Eine Variable vom Typ **POSITION** ist eine Schlüssel für die Liste.  Sie können eine **POSITION**\-Variable als Iterator, um eine Liste sequenziell zu durchlaufen und als Lesezeichen verwenden, um einen Ort aufzunehmen.  Eine Position ist nicht identisch mit einem Index, jedoch.  
  
 Elementeinfügung ist sehr schnell am Listenkopf, am Ende bei bekannten **POSITION**.  Eine sequenzielle Suche ist erforderlich, um ein Element als Wert oder Index gesucht wird.  Diese Suche kann langsam sein, wenn die Liste lang ist.  
  
 `CObList` enthält das `IMPLEMENT_SERIAL`\-Makro, um die Serialisierung und das Speichern seiner Elemente zu unterstützen.  Wenn eine Liste von `CObject` Zeiger zu einem Archiv, entweder mit einem überladenen Einfügungsoperator oder mit der `Serialize`\-Memberfunktion gespeichert wird, wird jedes Element `CObject` wiederum serialisiert.  
  
 Wenn Sie ein Speicherabbild der einzelnen `CObject`\-Elemente in der Liste benötigen, müssen Sie die Tiefe des Dumpkontexts auf 1 festlegen oder größer ist.  
  
 Wenn ein `CObList`\-Objekt gelöscht oder wenn seine Elemente entfernt werden, nur die `CObject` Zeiger entfernt werden, nicht die Objekte, die darauf verweisen.  
  
 Sie können eigene Klassen von `CObList` berechnen.  Die neue Listenklasse, entwickelt, um Zeiger auf Objekte enthält, die von `CObject` abgeleitet werden, fügt neue Datenmember und neue Memberfunktionen hinzu.  Beachten Sie, dass die resultierende Liste ausschließlich nicht typsicher ist, da sie Einfügen eines beliebigen `CObject` Zeigers zulässig.  
  
> [!NOTE]
>  Sie müssen das [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md)\-Makro in der Implementierung der abgeleiteten Klasse verwenden, wenn Sie beabsichtigen, die Liste zu serialisieren.  
  
 Weitere Informationen zur Verwendung von `CObList`, finden Sie im Artikel [Auflistungen](../../mfc/collections.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CObList`  
  
## Anforderungen  
 **Header:**  afxcoll.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CStringList Class](../../mfc/reference/cstringlist-class.md)   
 [CPtrList Class](../../mfc/reference/cptrlist-class.md)