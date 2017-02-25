---
title: "CMapWordToPtr Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMapWordToPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "16-bit word mapping"
  - "CMapWordToPtr class"
ms.assetid: b204d87f-6427-43e1-93e3-a4b1bb41099f
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMapWordToPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stützzuordnungen von den void\-Zeigern verschlüsselt durch 16\-Bit\-Wörter.  
  
## Syntax  
  
```  
class CMapWordToPtr : public CObject  
```  
  
## Mitglieder  
 Die Memberfunktionen von `CMapWordToPtr` sind \- Memberfunktion der Klasse [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md) ähnlich.  Aufgrund dieser Ähnlichkeit, können Sie die `CMapStringToOb` Referenzdokumentation für Memberfunktionsbesonderen verwenden.  Wenn Sie einen `CObject` Zeiger als Funktionsparameter oder Rückgabewert finden, ersetzen Sie einen Zeiger auf `void`.  Wenn Sie `CString` oder einen **const** Zeiger auf `char` als Funktionsparameter oder Rückgabewert finden, ersetzen Sie **WORD**.  
  
 `BOOL CMapStringToOb::Lookup( const char* <key>,`  
  
 `CObject*& <rValue> ) const;`  
  
 beispielsweise übersetzt zu  
  
 `BOOL CMapWordToPtr::Lookup( WORD <key>, void*& <rValue> ) const;`  
  
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
  
 Word\-zu\-Zeiger Zuordnungen nicht serialisiert werden kann.  
  
 Wenn ein `CMapWordToPtr`\-Objekt gelöscht oder wenn seine Elemente entfernt werden, werden die Wörter und die Zeiger entfernt.  Die Entitäten, die von Zeigern verwiesen werden, werden nicht entfernt.  
  
 Weitere Informationen zu `CMapWordToPtr`, finden Sie im Artikel [Auflistungen](../../mfc/collections.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapWordToPtr`  
  
## Anforderungen  
 **Header:**  afxcoll.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)