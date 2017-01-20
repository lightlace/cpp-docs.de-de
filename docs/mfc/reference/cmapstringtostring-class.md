---
title: "CMapStringToString Class"
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
  - "CMapStringToString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMapStringToString class"
  - "Auflistungsklassen, string mapping"
  - "Zeichenfolgen [C++], class for mapping"
  - "Zeichenfolgen [C++], Zuordnen"
ms.assetid: b45794c2-fe6b-4edb-a8ca-faa03b57b4a8
caps.latest.revision: 23
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CMapStringToString Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stützzuordnungen `CString` von Objekten, die von `CString` verschlüsselt werden, Objekte ein.  
  
## Syntax  
  
```  
class CMapStringToString : public CObject  
```  
  
## Mitglieder  
 Die Memberfunktionen von `CMapStringToString` sind \- Memberfunktion der Klasse [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md) ähnlich.  Aufgrund dieser Ähnlichkeit, können Sie die `CMapStringToOb` Referenzdokumentation für Memberfunktionsbesonderen verwenden.  Wenn Sie einen `CObject` Zeiger als Rückgabewert\- oder "Ausgabe" Funktionsparameter finden, ersetzen Sie einen Zeiger auf `char`.  Wenn Sie einen `CObject` Zeiger als "Eingabe" Funktionsparameter finden, ersetzen Sie einen Zeiger auf `char`.  
  
 `BOOL CMapStringToOb::Lookup(const char*<key>, CObject*&<rValue>) const;`  
  
 beispielsweise übersetzt zu  
  
 `BOOL CMapStringToString::Lookup(LPCTSTR<key>, CString&<rValue>) const;`  
  
### Öffentliche Strukturen  
  
|Name|Description|  
|----------|-----------------|  
|[CMapStringToString::CPair](../Topic/CMapStringToString::CPair.md)|Eine geschachtelte Struktur, die einen Schlüsselwert und den Wert des zugeordneten Zeichenfolgenobjekts enthält.|  
  
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
|[CMapStringToString::PGetFirstAssoc](../Topic/CMapStringToString::PGetFirstAssoc.md)|Ruft einen Zeiger auf `CString` erste in der Zuordnung.|  
|[CMapStringToString::PGetNextAssoc](../Topic/CMapStringToString::PGetNextAssoc.md)|Ruft einen Zeiger auf folgende `CString` zum Durchlaufen.|  
|[CMapStringToString::PLookup](../Topic/CMapStringToString::PLookup.md)|Gibt einen Zeiger auf `CString` zurück, dessen Wert den angegebenen Wert entspricht.|  
|[CMapStringToOb::RemoveAll](../Topic/CMapStringToOb::RemoveAll.md)|Entfernt alle Elemente aus dieser Zuordnung.|  
|[CMapStringToOb::RemoveKey](../Topic/CMapStringToOb::RemoveKey.md)|Entfernt ein Element, das über einen Schlüssel angegeben wird.|  
|[CMapStringToOb::SetAt](../Topic/CMapStringToOb::SetAt.md)|Fügt ein Element in die Zuordnung ein; ersetzt ein vorhandenes Element, wenn ein übereinstimmender Schlüssel gefunden wird.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMapStringToOb::operator](../Topic/CMapStringToOb::operator.md)|Fügt ein Element in die Zuordnung Operatorersatz für `SetAt` ein.|  
  
## Hinweise  
 `CMapStringToString` enthält das `IMPLEMENT_SERIAL`\-Makro, um die Serialisierung und das Speichern seiner Elemente zu unterstützen.  Jedes Element wird wiederum serialisiert, wenn eine Zuordnung zu einem Archiv, entweder mit dem überladenen Operator Einfüge\-**\<\<**\(\) oder mit der `Serialize`\-Memberfunktion gespeichert wird.  
  
 Wenn Sie einen Dump der einzelnen `CString`\- der `CString`\-Elemente benötigen, müssen Sie die Tiefe des Dumpkontexts auf 1 festlegen oder größer ist.  
  
 Wenn ein `CMapStringToString`\-Objekt gelöscht oder wenn seine Elemente entfernt werden, werden die `CString`\-Objekte ggf. entfernt.  
  
 Weitere Informationen zu `CMapStringToString`, finden Sie im Artikel [Auflistungen](../../mfc/collections.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapStringToString`  
  
## Anforderungen  
 **Header:**  afxcoll.h  
  
## Siehe auch  
 [MFC\-Beispiel COLLECT](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)