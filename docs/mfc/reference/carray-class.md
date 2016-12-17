---
title: "CArray Class"
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
  - "CArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Arrays [C++], Klassen"
  - "CArray class"
  - "Auflistungsklassen, template-based"
  - "Vorlagen, Auflistungsklassen"
ms.assetid: fead8b00-4cfd-4625-ad0e-251df62ba92f
caps.latest.revision: 33
caps.handback.revision: "23"
ms.author: "mblome"
manager: "ghogen"
---
# CArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unterstützt, Arrays, die wie C\-Arrays sind, kann jedoch dynamisch reduzieren und bei Bedarf wachsen.  
  
## Syntax  
  
```  
template < class TYPE, class ARG_TYPE = const TYPE& >   
class CArray :   
   public CObject  
```  
  
#### Parameter  
 `TYPE`  
 Vorlagenparameter, der den Typ von Objekten angibt, gespeicherten im Array.  `TYPE` ist ein Parameter, der von `CArray` zurückgegeben wird.  
  
 `ARG` *\_* `TYPE`  
 Vorlagenparameter, der den Argumenttyp angibt, der verwendet wird, um auf Objekte zuzugreifen, gespeicherten im Array.  Häufig ein Verweis auf `TYPE`.  `ARG_TYPE` ist ein Parameter, der auf `CArray` übergeben wird.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CArray::CArray](../Topic/CArray::CArray.md)|Erstellt ein leeres Array.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CArray::Add](../Topic/CArray::Add.md)|Fügt ein Element am Ende des Arrays hinzu; vergrößert das Array.|  
|[CArray::Append](../Topic/CArray::Append.md)|Fügt ein anderes Array dem Array an; vergrößert das Array ggf.|  
|[CArray::Copy](../Topic/CArray::Copy.md)|Kopiert ein anderes Array dem Array; vergrößert das Array.|  
|[CArray::ElementAt](../Topic/CArray::ElementAt.md)|Gibt einen temporären Verweis auf das Element innerhalb des Arrays zurück.|  
|[CArray::FreeExtra](../Topic/CArray::FreeExtra.md)|Gibt alle nicht verwendeten Arbeitsspeicher über der aktuellen Obergrenze frei.|  
|[CArray::GetAt](../Topic/CArray::GetAt.md)|Gibt den Wert an einem angegebenen Index zurück.|  
|[CArray::GetCount](../Topic/CArray::GetCount.md)|Ruft die Anzahl der Elemente in diesem Array ab.|  
|[CArray::GetData](../Topic/CArray::GetData.md)|Ermöglicht den Zugriff auf Elemente im Array.  Kann **NULL**.|  
|[CArray::GetSize](../Topic/CArray::GetSize.md)|Ruft die Anzahl der Elemente in diesem Array ab.|  
|[CArray::GetUpperBound](../Topic/CArray::GetUpperBound.md)|Gibt den größten gültigen Index zurück.|  
|[CArray::InsertAt](../Topic/CArray::InsertAt.md)|Fügt ein Element \(oder alle Elemente in anderen Array\) zu einem angegebenen Index ein.|  
|[CArray::IsEmpty](../Topic/CArray::IsEmpty.md)|Bestimmt, ob das Array leer ist.|  
|[CArray::RemoveAll](../Topic/CArray::RemoveAll.md)|Entfernt alle Elemente aus diesem Array.|  
|[CArray::RemoveAt](../Topic/CArray::RemoveAt.md)|Entfernt ein Element an einem bestimmten Index.|  
|[CArray::SetAt](../Topic/CArray::SetAt.md)|Legt den Wert für einen angegebenen Index fest; Array nicht zulässig, um vergrößert.|  
|[CArray::SetAtGrow](../Topic/CArray::SetAtGrow.md)|Legt den Wert für einen angegebenen Index fest; vergrößert das Array.|  
|[CArray::SetSize](../Topic/CArray::SetSize.md)|Legt die Anzahl der fest in diesem Array enthalten von Elementen.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CArray::operator](../Topic/CArray::operator.md)|Legt fest oder ruft das Element am angegebenen Index ab.|  
  
## Hinweise  
 Anfang der Arrayindizes immer an Position 0.  Sie können entscheiden, ob die Obergrenze korrigiert oder das Array ermöglicht, zu erweitern, wenn Sie Elemente hinter der Stromgrenze hinzufügen.  Arbeitsspeicher wird nacheinander zur Obergrenze zugeordnet, selbst wenn einige Elemente NULL sind.  
  
> [!NOTE]
>  Die meisten Methoden, die ein Objekt `CArray` Größe oder Elemente ihm Verwendung [memcpy\_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md) Verschiebungselementen hinzufügen.  Dieses Problem ist, da `memcpy_s` nicht mit allen Objekten kompatibel ist, die den Konstruktor benötigen aufgerufen werden.  Wenn die Elemente in `CArray` nicht mit `memcpy_s` kompatibel sind, müssen Sie neue `CArray` der entsprechenden Größe erstellen.  Sie müssen [CArray::Copy](../Topic/CArray::Copy.md) und [CArray::SetAt](../Topic/CArray::SetAt.md) dann verwenden, um das neue Array aufgefüllt, da diese Methoden einen Zuweisungsoperator anstelle `memcpy_s` verwenden.  
  
 Wie bei Wechselstrom\-Array, ist die Zugriffsgeschwindigkeit für ein `CArray` indiziertes Element konstant und ist unabhängig von der Arraygröße.  
  
> [!TIP]
>  Vor der Verwendung eines Arrays, verwenden Sie [SetSize](../Topic/CArray::SetSize.md), um die Größe und für sie Speicher reserviert.  Wenn Sie nicht `SetSize` verwenden, wird das Hinzufügen von Elementen zu dem Array es, mehrfach neu zugeordnet werden und kopiert werden.  Allgemeine Neuzuordnung und das Kopieren sind ineffizient und können Arbeitsspeicher fragmentieren.  
  
 Wenn Sie eine Dumpdatei einzelner Elemente in einem Array benötigen, müssen Sie die Tiefe des [CDumpContext](../../mfc/reference/cdumpcontext-class.md)\-Objekts auf 1 festlegen oder größer ist.  
  
 Bestimmte Memberfunktionen dieser Klasse rufen globale Hilfsfunktionen auf, die für die meisten Verwendungsmöglichkeiten der Klasse `CArray` angepasst werden müssen.  Weitere Informationen finden Sie im Thema [Auflistungsklassen\-Hilfen](../../mfc/reference/collection-class-helpers.md) im MFC\-Makro\- und \-Werteabschnitt.  
  
 Arrayklassenableitung ist wie Listenableitung.  
  
 Weitere Informationen dazu, wie `CArray`, finden Sie im Artikel [Auflistungen](../../mfc/collections.md) verwendet.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CArray`  
  
## Anforderungen  
 `Header:` afxtempl.h  
  
## Siehe auch  
 [MFC\-Beispiel COLLECT](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CObArray Class](../../mfc/reference/cobarray-class.md)   
 [Hilfsfunktionen für die Auflistungsklasse](../../mfc/reference/collection-class-helpers.md)