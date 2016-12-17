---
title: "CMapWordToOb Class"
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
  - "CMapWordToOb"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "16-bit word mapping"
  - "CMapWordToOb class"
ms.assetid: 9c9bcd76-456f-4cf9-b03c-dd28b49d5e4f
caps.latest.revision: 23
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CMapWordToOb Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stützzuordnungen von `CObject` Zeigern verschlüsselt durch 16\-Bit\-Wörter.  
  
## Syntax  
  
```  
class CMapWordToOb : public CObject  
```  
  
## Mitglieder  
 Die Memberfunktionen von `CMapWordToOb` sind \- Memberfunktion der Klasse [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md) ähnlich.  Aufgrund dieser Ähnlichkeit, können Sie die `CMapStringToOb` Referenzdokumentation für Memberfunktionsbesonderen verwenden.  Wenn Sie `CString` oder einen **const** Zeiger auf `char` als Funktionsparameter oder Rückgabewert finden, ersetzen Sie **WORD**.  
  
 `BOOL CMapStringToOb::Lookup( const char* <key>,`  
  
 `CObject*& <rValue> ) const;`  
  
 beispielsweise übersetzt zu  
  
 `BOOL CMapWordToOb::Lookup( WORD <key>, CObject*& <rValue> ) const;`  
  
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
 `CMapWordToOb` enthält das `IMPLEMENT_SERIAL`\-Makro, um die Serialisierung und das Speichern seiner Elemente zu unterstützen.  Jedes Element wird wiederum serialisiert, wenn eine Zuordnung zu einem Archiv, entweder mit dem überladenen Operator Einfüge\-**\<\<**\(\) oder mit der `Serialize`\-Memberfunktion gespeichert wird.  
  
 Wenn Sie einen Dump der einzelnen **WORD**\- der `CObject`\-Elemente benötigen, müssen Sie die Tiefe des Dumpkontexts auf 1 festlegen oder größer ist.  
  
 Wenn ein `CMapWordToOb`\-Objekt gelöscht oder wenn seine Elemente entfernt werden, werden die `CObject` Zeiger entfernt.  Die Objekte, die von den `CObject` Zeigern verwiesen wird, werden nicht zerstört.  
  
 Weitere Informationen zu `CMapWordToOb`, finden Sie im Artikel [Auflistungen](../../mfc/collections.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapWordToOb`  
  
## Anforderungen  
 **Header:**  afxcoll.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)