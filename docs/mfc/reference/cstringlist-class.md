---
title: "CStringList Class"
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
  - "CStringList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringList class"
  - "Listen, Zeichenfolge"
  - "Zeichenfolgen [C++], Auflistungen"
  - "Zeichenfolgen [C++], Listen"
ms.assetid: 310a7edb-263c-4bd2-ac43-0bfbfddc5a33
caps.latest.revision: 25
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# CStringList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stützlisten von `CString`\-Objekten.  
  
## Syntax  
  
```  
class CStringList : public CObject  
```  
  
## Mitglieder  
 Die Memberfunktionen von `CStringList` sind \- Memberfunktion der Klasse [CObList](../../mfc/reference/coblist-class.md) ähnlich.  Aufgrund dieser Ähnlichkeit, können Sie die `CObList` Referenzdokumentation für Memberfunktionsbesonderen verwenden.  Wenn Sie einen `CObject` Zeiger als Rückgabewert finden, ersetzen Sie `CString` \(keinen `CString` Zeiger\).  Wenn Sie einen `CObject` Zeiger als Funktionsparameter finden, ersetzen Sie `LPCTSTR`.  
  
 `CObject*& CObList::GetHead() const;`  
  
 beispielsweise übersetzt zu  
  
 `CString& CStringList::GetHead() const;`  
  
 und  
  
 `POSITION AddHead( CObject* <newElement> );`  
  
 übersetzt zu  
  
 `POSITION AddHead( LPCTSTR <newElement> );`  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CObList::CObList](../Topic/CObList::CObList.md)|Erstellt eine leere Liste.|  
  
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
 Alle Vergleiche werden durch den Wert ausgeführt und bedeuten, dass die Zeichen in der Zeichenfolge anstelle der Adressen der Zeichenfolgen verglichen werden.  
  
 `CStringList` enthält das `IMPLEMENT_SERIAL`\-Makro, um die Serialisierung und das Speichern seiner Elemente zu unterstützen.  Wenn eine Liste von `CString`\-Objekten zu einem Archiv, entweder mit einem überladenen Einfügungsoperator oder mit der `Serialize`\-Memberfunktion gespeichert wird, wird jedes Element `CString` wiederum serialisiert.  
  
 Wenn Sie ein Speicherabbild der einzelnen `CString`\-Elemente benötigen, müssen Sie die Tiefe des Dumpkontexts auf 1 festlegen oder größer ist.  
  
 Weitere Informationen zur Verwendung von `CStringList`, finden Sie im Artikel [Auflistungen](../../mfc/collections.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CStringList`  
  
## Anforderungen  
 **Header:**  afxcoll.h  
  
## Siehe auch  
 [MFC\-Beispiel COLLECT](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)