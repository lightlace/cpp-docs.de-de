---
title: "CUIntArray Class"
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
  - "CUIntArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Arrays [C++], Indiziert"
  - "CUIntArray class"
  - "indexed arrays"
  - "INT"
  - "UINT"
  - "WORD data type"
ms.assetid: d71f3d8f-ef9f-4e48-9b69-7782c0e2ddf7
caps.latest.revision: 23
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CUIntArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unterstützt Arrays der Ganzzahlen ohne Vorzeichen.  
  
## Syntax  
  
```  
class CUIntArray : public CObject  
```  
  
## Mitglieder  
 Die Memberfunktionen von `CUIntArray` sind \- Memberfunktion der Klasse [CObArray](../../mfc/reference/cobarray-class.md) ähnlich.  Aufgrund dieser Ähnlichkeit, können Sie die `CObArray` Referenzdokumentation für Memberfunktionsbesonderen verwenden.  Wenn Sie einen `CObject` Zeiger als Funktionsparameter oder Rückgabewert finden, ersetzen Sie **UINT**.  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 beispielsweise übersetzt zu  
  
 `UINT CUIntArray::GetAt( int <nIndex> ) const;`  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CObArray::CObArray](../Topic/CObArray::CObArray.md)|Erstellt ein leeres Array.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CObArray::Add](../Topic/CObArray::Add.md)|Fügt ein Element am Ende des Arrays hinzu; vergrößert das Array.|  
|[CObArray::Append](../Topic/CObArray::Append.md)|Fügt ein anderes Array dem Array an; vergrößert das Array.|  
|[CObArray::Copy](../Topic/CObArray::Copy.md)|Kopiert ein anderes Array dem Array; vergrößert das Array.|  
|[CObArray::ElementAt](../Topic/CObArray::ElementAt.md)|Gibt einen temporären Verweis auf das Element innerhalb des Arrays zurück.|  
|[CObArray::FreeExtra](../Topic/CObArray::FreeExtra.md)|Gibt alle nicht verwendeten Arbeitsspeicher über der aktuellen Obergrenze frei.|  
|[CObArray::GetAt](../Topic/CObArray::GetAt.md)|Gibt den Wert an einem angegebenen Index zurück.|  
|[CObArray::GetCount](../Topic/CObArray::GetCount.md)|Ruft die Anzahl der Elemente in diesem Array ab.|  
|[CObArray::GetData](../Topic/CObArray::GetData.md)|Ermöglicht den Zugriff auf Elemente im Array.  Kann **NULL**.|  
|[CObArray::GetSize](../Topic/CObArray::GetSize.md)|Ruft die Anzahl der Elemente in diesem Array ab.|  
|[CObArray::GetUpperBound](../Topic/CObArray::GetUpperBound.md)|Gibt den größten gültigen Index zurück.|  
|[CObArray::InsertAt](../Topic/CObArray::InsertAt.md)|Fügt ein Element \(oder alle Elemente in anderen Array\) zu einem angegebenen Index ein.|  
|[CObArray::IsEmpty](../Topic/CObArray::IsEmpty.md)|Bestimmt, ob das Array leer ist.|  
|[CObArray::RemoveAll](../Topic/CObArray::RemoveAll.md)|Entfernt alle Elemente aus diesem Array.|  
|[CObArray::RemoveAt](../Topic/CObArray::RemoveAt.md)|Entfernt ein Element an einem bestimmten Index.|  
|[CObArray::SetAt](../Topic/CObArray::SetAt.md)|Legt den Wert für einen angegebenen Index fest; Array nicht zulässig, um vergrößert.|  
|[CObArray::SetAtGrow](../Topic/CObArray::SetAtGrow.md)|Legt den Wert für einen angegebenen Index fest; vergrößert das Array.|  
|[CObArray::SetSize](../Topic/CObArray::SetSize.md)|Legt die Anzahl der fest in diesem Array enthalten von Elementen.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CObArray::operator](../Topic/CObArray::operator.md)|Legt fest oder ruft das Element am angegebenen Index ab.|  
  
## Hinweise  
 Eine ganze Zahl ohne Vorzeichen oder **UINT**, unterscheidet sich von den Wörtern und von den Doppelworten darin, dass die physische Größe von **UINT** abhängig von der Betriebsumgebung des Ziels ändern kann.  **UINT** ist die gleiche Größe wie Doppelwort.  
  
 `CUIntArray` enthält das [IMPLEMENT\_DYNAMIC](../Topic/IMPLEMENT_DYNAMIC.md)\-Makro, um Ablauftypzugriff und das Speichern zu [CDumpContext](../../mfc/reference/cdumpcontext-class.md) eines Objekts zu unterstützen.  Wenn Sie eine Dumpdatei einzelner vorzeichenlose Elementen ganze Zahl benötigen, müssen Sie die Tiefe des Dumpkontexts auf 1 festlegen oder größer ist.  Ganzzahlige Arrays ohne Vorzeichen können nicht serialisiert werden.  
  
> [!NOTE]
>  Vor der Verwendung eines Arrays, verwenden Sie `SetSize`, um die Größe und für sie Speicher reserviert.  Wenn Sie nicht `SetSize` verwenden, wird das Hinzufügen von Elementen zu dem Array es, mehrfach neu zugeordnet werden und kopiert werden.  Allgemeine Neuzuordnung und das Kopieren sind ineffizient und können Arbeitsspeicher fragmentieren.  
  
 Weitere Informationen zur Verwendung von `CUIntArray`, finden Sie im Artikel [Auflistungen](../../mfc/collections.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CUIntArray`  
  
## Anforderungen  
 **Header:**  afxcoll.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)