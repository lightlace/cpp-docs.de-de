---
title: "CMapStringToOb Class"
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
  - "CMapStringToOb"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMapStringToOb class"
  - "Auflistungsklassen, string mapping"
  - "Zeichenfolgen [C++], class for mapping"
ms.assetid: 09653980-b885-4f3a-8594-0aeb7f94c601
caps.latest.revision: 20
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CMapStringToOb Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Wörterbuchauflistungsklasse, die eindeutige `CString` zuordnet, von Objekten zu `CObject` Zeiger ein.  
  
## Syntax  
  
```  
class CMapStringToOb : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMapStringToOb::CMapStringToOb](../Topic/CMapStringToOb::CMapStringToOb.md)|Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMapStringToOb::GetCount](../Topic/CMapStringToOb::GetCount.md)|Gibt die Anzahl von Elementen in dieser Zuordnung zurück.|  
|[CMapStringToOb::GetHashTableSize](../Topic/CMapStringToOb::GetHashTableSize.md)|Bestimmt die aktuelle Anzahl von Elementen in der Hashtabelle.|  
|[CMapStringToOb::GetNextAssoc](../Topic/CMapStringToOb::GetNextAssoc.md)|Ruft das folgende Element zum Durchlaufen ab.|  
|[CMapStringToOb::GetSize](../Topic/CMapStringToOb::GetSize.md)|Gibt die Anzahl von Elementen in dieser Zuordnung zurück.|  
|[CMapStringToOb::GetStartPosition](../Topic/CMapStringToOb::GetStartPosition.md)|Gibt die Position des ersten Elements zurück.|  
|[CMapStringToOb::HashKey](../Topic/CMapStringToOb::HashKey.md)|Berechnet den Hashwert des angegebenen Schlüssels.|  
|[CMapStringToOb::InitHashTable](../Topic/CMapStringToOb::InitHashTable.md)|Initialisiert die Hashtabelle.|  
|[CMapStringToOb::IsEmpty](../Topic/CMapStringToOb::IsEmpty.md)|Tests für die EMPTYZuordnung Zustand \(keine Elemente\).|  
|[CMapStringToOb::Lookup](../Topic/CMapStringToOb::Lookup.md)|Dynamic Data sucht nach einen void\-Zeiger auf Grundlage der void\-Zeiger\-Taste.  Der Zeigerwert, nicht die Entität zeigt diese, wird für den Schlüsselvergleich.|  
|[CMapStringToOb::LookupKey](../Topic/CMapStringToOb::LookupKey.md)|Gibt einen Verweis auf die Schlüssel zurück, die dem angegebenen Schlüsselwert zugeordnet ist.|  
|[CMapStringToOb::RemoveAll](../Topic/CMapStringToOb::RemoveAll.md)|Entfernt alle Elemente aus dieser Zuordnung.|  
|[CMapStringToOb::RemoveKey](../Topic/CMapStringToOb::RemoveKey.md)|Entfernt ein Element, das über einen Schlüssel angegeben wird.|  
|[CMapStringToOb::SetAt](../Topic/CMapStringToOb::SetAt.md)|Fügt ein Element in die Zuordnung ein; ersetzt ein vorhandenes Element, wenn ein übereinstimmender Schlüssel gefunden wird.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMapStringToOb::operator](../Topic/CMapStringToOb::operator.md)|Fügt ein Element in die Zuordnung Operatorersatz für `SetAt` ein.|  
  
## Hinweise  
 Nachdem Sie ein `CString`\-`CObject*` Paar \(\- Element\) in die Zuordnung eingefügt haben, können Sie die Paare mit einer Zeichenfolge oder einem `CString`\-Wert als Schlüssel effizient abrufen oder löschen.  Sie können über alle Elemente in der Zuordnung aber auch.  
  
 Eine Variable vom Typ **POSITION** wird für alternativen Eintragszugriff in allen Zuordnungsvariationen verwendet.  Sie können **POSITION** verwenden "der Anmeldedaten an einen Eintrag und durch die Zuordnung durchlaufen.  Möglicherweise gehen Sie davon aus, dass diese Iteration durch Schlüsselwert sequenziell ist; nicht berücksichtigt.  Die Sequenz der abgerufenen Elemente ist unbestimmt.  
  
 `CMapStringToOb` enthält das `IMPLEMENT_SERIAL`\-Makro, um die Serialisierung und das Speichern seiner Elemente zu unterstützen.  Jedes Element wird wiederum serialisiert, wenn eine Zuordnung zu einem Archiv, entweder mit dem überladenen Operator Einfüge\-**\<\<**\(\) oder mit der `Serialize`\-Memberfunktion gespeichert wird.  
  
 Wenn Sie einen Diagnosen Dump der einzelnen Elemente in der Zuordnung \(der `CString`\-Wert und der `CObject` Inhalt\) benötigen, müssen Sie die Tiefe des Dumpkontexts auf 1 festlegen oder größer ist.  
  
 Wenn ein `CMapStringToOb`\-Objekt gelöscht oder wenn seine Elemente entfernt werden, werden die `CString`\-Objekte und die `CObject` Zeiger entfernt.  Die Objekte, die von den `CObject` Zeigern verwiesen wird, werden nicht zerstört.  
  
 Zuordnungsklassenableitung ist zur Listenableitung ähnlich.  Weitere Informationen finden Sie im Artikel [Auflistungen](../../mfc/collections.md) für eine Abbildung der Ableitung einer Listenklasse für spezielle Zwecke.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapStringToOb`  
  
## Anforderungen  
 **Header:**  afxcoll.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr Class](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord Class](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapStringToPtr Class](../../mfc/reference/cmapstringtoptr-class.md)   
 [CMapStringToString Class](../../mfc/reference/cmapstringtostring-class.md)   
 [CMapWordToOb Class](../../mfc/reference/cmapwordtoob-class.md)   
 [CMapWordToPtr Class](../../mfc/reference/cmapwordtoptr-class.md)