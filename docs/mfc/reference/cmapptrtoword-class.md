---
title: "CMapPtrToWord Class"
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
  - "CMapPtrToWord"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "16-bit word mapping"
  - "CMapPtrToWord class"
ms.assetid: 4631c6b6-d49f-49d9-adc0-1e0491e32d7b
caps.latest.revision: 22
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CMapPtrToWord Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stützzuordnungen von den 16\-Bit\-Wörtern verschlüsselt durch void\-Zeiger.  
  
## Syntax  
  
```  
class CMapPtrToWord : public CObject  
```  
  
## Mitglieder  
 Die Memberfunktionen von `CMapPtrToWord` sind \- Memberfunktion der Klasse [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md) ähnlich.  Aufgrund dieser Ähnlichkeit, können Sie die `CMapStringToOb` Referenzdokumentation für Memberfunktionsbesonderen verwenden.  Wenn Sie einen `CObject`\-Zeiger als Funktionsparameter oder Rückgabewert finden, ersetzen Sie **WORD**.  Wenn Sie `CString` oder einen **const** Zeiger auf `char` als Funktionsparameter oder Rückgabewert finden, ersetzen Sie einen Zeiger auf `void`.  
  
 `BOOL CMapStringToOb::Lookup( const char* <key>,`  
  
 `CObject*& <rValue> ) const;`  
  
 beispielsweise übersetzt zu  
  
 `BOOL CMapPtrToWord::Lookup( const void* <key>, WORD& <rValue> ) const;`  
  
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
 `CMapWordToPtr` enthält das `IMPLEMENT_DYNAMIC`\-Makro, um Ablauftypzugriff und das Speichern zu `CDumpContext` eines Objekts zu unterstützen.  Wenn Sie eine Dumpdatei einzelner Kartenelementen benötigen, müssen Sie die Tiefe des Dumpkontexts auf 1 festlegen oder größer ist.  
  
 Zeiger\-zu\-Word\-Zuordnungen nicht serialisiert werden kann.  
  
 Wenn ein `CMapPtrToWord`\-Objekt gelöscht oder wenn seine Elemente entfernt werden, werden die Zeiger und die Wörter entfernt.  Die Entitäten, die von den Schlüsselzeigern verwiesen werden, werden nicht entfernt.  
  
 Weitere Informationen zu `CMapPtrToWord`, finden Sie im Artikel [Auflistungen](../../mfc/collections.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapPtrToWord`  
  
## Anforderungen  
 **Header:**  afxcoll.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)