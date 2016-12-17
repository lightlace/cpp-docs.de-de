---
title: "CObArray Class"
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
  - "CObArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Arrays [C++], Objekttyp"
  - "Arrays [C++], Zeiger"
  - "CObArray class"
  - "Objektarrays, CObArray class"
ms.assetid: 27894efd-2370-4776-9ed9-24a98492af17
caps.latest.revision: 20
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CObArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unterstützt Arrays `CObject` Zeiger.  
  
## Syntax  
  
```  
class CObArray : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CObArray::CObArray](../Topic/CObArray::CObArray.md)|Erstellt ein leeres Array für `CObject` Zeiger.|  
  
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
 Diese Objektarrays sind zu C\-Arrays ähnlich, allerdings können dynamisch verkleinern und bei Bedarf wachsen.  
  
 Anfang der Arrayindizes immer an Position 0.  Sie können entscheiden, ob die Obergrenze korrigiert oder dem Array ermöglicht, zu erweitern, wenn Sie Elemente hinter der Stromgrenze hinzufügen.  Arbeitsspeicher wird nacheinander zur Obergrenze zugeordnet, selbst wenn einige Elemente NULL sind.  
  
 Die Win32 wird die Größe eines Objekts `CObArray` nur an den verfügbaren Arbeitsspeicher begrenzt.  
  
 Wie bei Wechselstrom\-Array, ist die Zugriffsgeschwindigkeit für ein `CObArray` indiziertes Element konstant und ist unabhängig von der Arraygröße.  
  
 `CObArray` enthält das `IMPLEMENT_SERIAL`\-Makro, um die Serialisierung und das Speichern seiner Elemente zu unterstützen.  Wenn ein Array `CObject` Zeiger zu einem Archiv, entweder mit dem überladenen Einfügungsoperator oder mit der `Serialize`\-Memberfunktion gespeichert wird, wird jedes Element `CObject` wiederum zusammen mit dem Arrayindex serialisiert.  
  
 Wenn Sie ein Speicherabbild der einzelnen  `CObject`\-Elemente in einem Array benötigen, müssen Sie die Tiefe des `CDumpContext`\-Objekts auf 1 festlegen oder größer ist.  
  
 Wenn ein `CObArray`\-Objekt gelöscht oder wenn seine Elemente entfernt werden, nur die `CObject` Zeiger entfernt werden, nicht die Objekte, die darauf verweisen.  
  
> [!NOTE]
>  Vor der Verwendung eines Arrays, verwenden Sie `SetSize`, um die Größe und für sie Speicher reserviert.  Wenn Sie nicht `SetSize` verwenden, wird das Hinzufügen von Elementen zu dem Array es, mehrfach neu zugeordnet werden und kopiert werden.  Allgemeine Neuzuordnung und das Kopieren sind ineffizient und können Arbeitsspeicher fragmentieren.  
  
 Arrayklassenableitung ist zur Listenableitung ähnlich.  Ausführliche Informationen über die Ableitung einer Listenklasse für spezielle Zwecke, finden Sie im Artikel [Auflistungen](../../mfc/collections.md).  
  
> [!NOTE]
>  Sie müssen das `IMPLEMENT_SERIAL`\-Makro in der Implementierung der abgeleiteten Klasse verwenden, wenn Sie beabsichtigen, das Array zu serialisieren.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CObArray`  
  
## Anforderungen  
 **Header:**  afxcoll.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CStringArray Class](../../mfc/reference/cstringarray-class.md)   
 [CPtrArray Class](../../mfc/reference/cptrarray-class.md)   
 [CByteArray Class](../../mfc/reference/cbytearray-class.md)   
 [CWordArray Class](../../mfc/reference/cwordarray-class.md)   
 [CDWordArray Class](../../mfc/reference/cdwordarray-class.md)