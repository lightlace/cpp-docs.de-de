---
title: "CMap Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMap class"
  - "Auflistungsklassen, dictionary mapping"
  - "dictionary mapping class"
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Wörterbuchauflistungsklasse, die eindeutige Schlüssel auf Werte zuordnet.  
  
## Syntax  
  
```  
template< class KEY, class ARG_KEY, class VALUE, class ARG_VALUE >class CMap : public CObject  
```  
  
#### Parameter  
 `KEY`  
 Klasse des Objekts verwendet als Schlüssel zur Zuordnung.  
  
 `ARG` *\_* `KEY`  
 Datentyp verwendet für `KEY`\-Argumente; normalerweise ein Verweis auf `KEY`.  
  
 `VALUE`  
 Klasse des Objekts gespeichert in der Zuordnung.  
  
 `ARG` *\_* `VALUE`  
 Datentyp verwendet für `VALUE`\-Argumente; normalerweise ein Verweis auf `VALUE`.  
  
## Mitglieder  
  
### Öffentliche Strukturen  
  
|Name|Description|  
|----------|-----------------|  
|[CMap::CPair](../Topic/CMap::CPair.md)|Eine geschachtelte Struktur, die einen Schlüsselwert und den Wert des zugeordneten Objekts enthält.|  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMap::CMap](../Topic/CMap::CMap.md)|Erstellt eine Auflistung, die Schlüssel zu den Werten zuordnet.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMap::GetCount](../Topic/CMap::GetCount.md)|Gibt die Anzahl von Elementen in dieser Zuordnung zurück.|  
|[CMap::GetHashTableSize](../Topic/CMap::GetHashTableSize.md)|Gibt die Anzahl der Elemente in der Hashtabelle zurück.|  
|[CMap::GetNextAssoc](../Topic/CMap::GetNextAssoc.md)|Ruft das folgende Element zum Durchlaufen ab.|  
|[CMap::GetSize](../Topic/CMap::GetSize.md)|Gibt die Anzahl von Elementen in dieser Zuordnung zurück.|  
|[CMap::GetStartPosition](../Topic/CMap::GetStartPosition.md)|Gibt die Position des ersten Elements zurück.|  
|[CMap::InitHashTable](../Topic/CMap::InitHashTable.md)|Initialisiert die Hashtabelle und gibt seine Größe an.|  
|[CMap::IsEmpty](../Topic/CMap::IsEmpty.md)|Tests für die EMPTYZuordnung Zustand \(keine Elemente\).|  
|[CMap::Lookup](../Topic/CMap::Lookup.md)|Dynamic Data sucht nach den Wert, der einer angegebenen Schlüssel zugeordnet ist.|  
|[CMap::PGetFirstAssoc](../Topic/CMap::PGetFirstAssoc.md)|Gibt einen Zeiger auf das erste Element zurück.|  
|[CMap::PGetNextAssoc](../Topic/CMap::PGetNextAssoc.md)|Ruft einen Zeiger auf das folgende Element zum Durchlaufen.|  
|[CMap::PLookup](../Topic/CMap::PLookup.md)|Gibt einen Zeiger auf eine Schlüssel zurück, deren Wert den angegebenen Wert entspricht.|  
|[CMap::RemoveAll](../Topic/CMap::RemoveAll.md)|Entfernt alle Elemente aus dieser Zuordnung.|  
|[CMap::RemoveKey](../Topic/CMap::RemoveKey.md)|Entfernt ein Element, das über einen Schlüssel angegeben wird.|  
|[CMap::SetAt](../Topic/CMap::SetAt.md)|Fügt ein Element in die Zuordnung ein; ersetzt ein vorhandenes Element, wenn ein übereinstimmender Schlüssel gefunden wird.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMap::operator](../Topic/CMap::operator.md)|Fügt ein Element in die Zuordnung Operatorersatz für `SetAt` ein.|  
  
## Hinweise  
 Nachdem Sie ein Schlüssel\-Wert\-Paar \(\- Element\) in die Zuordnung eingefügt haben, können Sie die beiden mithilfe der Schlüssel effizient abrufen oder löschen, um darauf zuzugreifen.  Sie können über alle Elemente in der Zuordnung aber auch.  
  
 Eine Variable vom Typ **POSITION** wird für alternativen Zugriff zu Einträgen verwendet.  Sie können **POSITION** verwenden "der Anmeldedaten an einen Eintrag und durch die Zuordnung durchlaufen.  Möglicherweise gehen Sie davon aus, dass diese Iteration durch Schlüsselwert sequenziell ist; nicht berücksichtigt.  Die Sequenz der abgerufenen Elemente ist unbestimmt.  
  
 Bestimmte Memberfunktionen dieser Klasse rufen globale Hilfsfunktionen auf, die für die meisten Verwendungsmöglichkeiten der Klasse `CMap` angepasst werden müssen.  Siehe [Auflistungsklassen\-Hilfen](../../mfc/reference/collection-class-helpers.md) im Makro\- und Werteabschnitt `MFC``Reference`.  
  
 `CMap` überschreibt [CObject::Serialize](../Topic/CObject::Serialize.md), um die Serialisierung und das Speichern seiner Elemente zu unterstützen.  Wenn eine Zuordnung zu einem Archiv mithilfe `Serialize` gespeichert wird, wird jedes Kartenelement wiederum serialisiert.  Die Standardimplementierung der `SerializeElements` Hilfsfunktion führt eine bitweise schreiben.  Weitere Informationen zur Serialisierung von den Zeigerauflistungselementen, die von `CObject` oder anderen benutzerdefinierten Typen abgeleitet werden, finden Sie unter [Gewusst wie: Erstellen einer typsicheren Auflistung](../../mfc/how-to-make-a-type-safe-collection.md).  
  
 Wenn Sie einen Diagnosen Dump der einzelnen Elemente in der Zuordnung \(die Schlüssel und Werte\) benötigen, müssen Sie die Tiefe des Dumpkontexts auf 1 festlegen oder größer ist.  
  
 Wenn ein `CMap`\-Objekt gelöscht oder wenn seine Elemente entfernt werden, werden die Schlüssel und Werte beide entfernt.  
  
 Zuordnungsklassenableitung ist zur Listenableitung ähnlich.  Weitere Informationen finden Sie im Artikel [Auflistungen](../../mfc/collections.md) für eine Abbildung der Ableitung einer Listenklasse für spezielle Zwecke.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMap`  
  
## Anforderungen  
 **Header:**  afxtempl.h  
  
## Siehe auch  
 [MFC\-Beispiel COLLECT](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)