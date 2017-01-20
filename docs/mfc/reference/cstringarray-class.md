---
title: "CStringArray Class"
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
  - "CStringArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Arrays [C++], Zeichenfolgen"
  - "CStringArray class"
  - "string arrays"
  - "Zeichenfolgen [C++], Auflistungen"
ms.assetid: 6c637e06-bba8-4c08-b0fc-cf8cb067ce34
caps.latest.revision: 24
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CStringArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unterstützt Arrays mit [CString](../../atl-mfc-shared/using-cstring.md)\-Objekten.  
  
## Syntax  
  
```  
class CStringArray : public CObject  
```  
  
## Mitglieder  
 Die Memberfunktionen von `CStringArray` entsprechen den Memberfunktionen der Klasse [CObArray](../../mfc/reference/cobarray-class.md).  Aufgrund dieser Ähnlichkeit können Sie die `CObArray`\-Referenzdokumentation für Memberfunktionsbesonderheiten verwenden.  Immer dort, wo ein `CObject`\-Zeiger als Rückgabewert angezeigt wird, ersetzen Sie ein [CString](../../atl-mfc-shared/using-cstring.md)\-Objekt \(nicht einen [CString](../../atl-mfc-shared/using-cstring.md)\-Zeiger\).  Immer dort, wo ein `CObject`\-Zeiger als Funktionsparameter angezeigt wird, ersetzen Sie einen `LPCTSTR`.  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 Beispielsweise übersetzt zu  
  
 `CString CStringArray::GetAt( int <nIndex> ) const;`  
  
 und  
  
 `void SetAt( int <nIndex>, CObject* <newElement> )`  
  
 wird übersetzt in  
  
 `void SetAt( int <nIndex>, LPCTSTR <newElement> )`  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CObArray::CObArray](../Topic/CObArray::CObArray.md)|Erstellt ein leeres Array.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CObArray::Add](../Topic/CObArray::Add.md)|Fügt am Ende des Arrays ein Element hinzu; vergrößert das Array bei Bedarf.|  
|[CObArray::Append](../Topic/CObArray::Append.md)|Hängt ein anderes Array an das Array an; vergrößert das Array bei Bedarf.|  
|[CObArray::Copy](../Topic/CObArray::Copy.md)|Kopiert ein anderes Array in das Array; vergrößert das Array bei Bedarf.|  
|[CObArray::ElementAt](../Topic/CObArray::ElementAt.md)|Gibt einen temporären Verweis auf den Elementzeiger innerhalb des Arrays zurück.|  
|[CObArray::FreeExtra](../Topic/CObArray::FreeExtra.md)|Gibt den gesamten nicht verwendeten Arbeitsspeicher über der aktuellen Obergrenze frei.|  
|[CObArray::GetAt](../Topic/CObArray::GetAt.md)|Gibt den Wert an einem bestimmten Index zurück.|  
|[CObArray::GetCount](../Topic/CObArray::GetCount.md)|Ruft die Anzahl der Elemente im Array ab.|  
|[CObArray::GetData](../Topic/CObArray::GetData.md)|Ermöglicht den Zugriff auf Elemente im Array.  Kann **NULL** sein.|  
|[CObArray::GetSize](../Topic/CObArray::GetSize.md)|Ruft die Anzahl der Elemente im Array ab.|  
|[CObArray::GetUpperBound](../Topic/CObArray::GetUpperBound.md)|Gibt den größten gültigen Index zurück.|  
|[CObArray::InsertAt](../Topic/CObArray::InsertAt.md)|Fügt ein Element \(oder alle Elemente in einem anderen Array\) am angegebenen Index ein.|  
|[CObArray::IsEmpty](../Topic/CObArray::IsEmpty.md)|Bestimmt, ob das Array leer ist.|  
|[CObArray::RemoveAll](../Topic/CObArray::RemoveAll.md)|Entfernt alle Elemente aus diesem Array.|  
|[CObArray::RemoveAt](../Topic/CObArray::RemoveAt.md)|Entfernt ein Element an einem spezifischen Index.|  
|[CObArray::SetAt](../Topic/CObArray::SetAt.md)|Legt den Wert für einen bestimmten Index fest; Array darf nicht vergrößert werden.|  
|[CObArray::SetAtGrow](../Topic/CObArray::SetAtGrow.md)|Legt den Wert für einen bestimmten Index fest; vergrößert das Array bei Bedarf.|  
|[CObArray::SetSize](../Topic/CObArray::SetSize.md)|Legt die Anzahl der Elemente im Array fest.|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CObArray::operator](../Topic/CObArray::operator.md)|Legt das Element am angegebenen Index fest oder ruft es ab.|  
  
## Hinweise  
 `CStringArray` integriert das `IMPLEMENT_SERIAL`\-Makro, um die Serialisierung sowie die Sicherung der Elemente zu unterstützen.  Wenn ein Array mit `CString`\-Objekten in einem Archiv gespeichert wird, entweder mit einem überladenen Operator zum Einfügen oder mit der `Serialize`\-Member\-Funktion, wird jedes Element der Reihe nach serialisiert.  
  
> [!NOTE]
>  Vor dem Verwenden eines Arrays, verwenden Sie `SetSize`, um dessen Größe festzustellen, und weisen dafür Arbeitsspeicher zu.  Wenn Sie `SetSize` nicht verwenden, kann das Hinzufügen von Elementen zu Ihrem Array dazu führen, dass es häufig neu zugeordnet und kopiert wird.  Häufige Neuzuordnungen und Kopiervorgänge sind ineffizient und können zu einer Fragmentierung des Arbeitsspeichers führen.  
  
 Wenn Sie eine Sicherung einzelner Zeichenfolgenelemente im Array benötigen, müssen Sie die Tiefe des Sicherungskontexts auf 1 oder größer festlegen.  
  
 Wenn ein `CString`\-Array gelöscht wird oder wenn dessen Elemente entfernt werden, wird je nach Bedarf Zeichenfolgenspeicher freigegeben.  
  
 Weitere Informationen zum Verwenden von `CStringArray` finden Sie im Artikel [Auflistungen](../../mfc/collections.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CStringArray`  
  
## Anforderungen  
 **Header:** afxcoll.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)