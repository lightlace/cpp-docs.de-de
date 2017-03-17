---
title: CObArray Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CObArray
- AFXCOLL/CObArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
dev_langs:
- C++
helpviewer_keywords:
- arrays [C++], pointers
- CObArray class
- arrays [C++], Object type
- object arrays, CObArray class
ms.assetid: 27894efd-2370-4776-9ed9-24a98492af17
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ed822c7e23510144d09ee268c1430aea354144cb
ms.lasthandoff: 02/24/2017

---
# <a name="cobarray-class"></a>CObArray-Klasse
Unterstützt Arrays mit `CObject` -Zeigern.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CObArray : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObArray::CObArray](#cobarray)|Erstellt ein leeres Array für `CObject` Zeiger.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObArray::Add](#add)|Fügt am Ende des Arrays ein Element hinzu; vergrößert das Array bei Bedarf.|  
|[CObArray::Append](#append)|Hängt ein anderes Array an das Array an; vergrößert das Array bei Bedarf.|  
|[CObArray::Copy](#copy)|Kopiert ein anderes Array in das Array; vergrößert das Array bei Bedarf.|  
|[CObArray::ElementAt](#elementat)|Gibt einen temporären Verweis auf den Elementzeiger innerhalb des Arrays zurück.|  
|[CObArray::FreeExtra](#freeextra)|Gibt den gesamten nicht verwendeten Arbeitsspeicher über der aktuellen Obergrenze frei.|  
|[CObArray::GetAt](#getat)|Gibt den Wert an einem bestimmten Index zurück.|  
|[CObArray::GetCount](#getcount)|Ruft die Anzahl der Elemente im Array ab.|  
|[CObArray::GetData](#getdata)|Ermöglicht den Zugriff auf Elemente im Array. Kann **NULL**.|  
|[CObArray::GetSize](#getsize)|Ruft die Anzahl der Elemente im Array ab.|  
|[CObArray::GetUpperBound](#getupperbound)|Gibt den größten gültigen Index zurück.|  
|[CObArray::InsertAt](#insertat)|Fügt ein Element (oder alle Elemente in einem anderen Array) am angegebenen Index ein.|  
|[CObArray::IsEmpty](#isempty)|Bestimmt, ob das Array leer ist.|  
|[CObArray::RemoveAll](#removeall)|Entfernt alle Elemente aus diesem Array.|  
|[CObArray::RemoveAt](#removeat)|Entfernt ein Element an einem spezifischen Index.|  
|[CObArray::SetAt](#setat)|Legt den Wert für einen bestimmten Index fest; Array darf nicht vergrößert werden.|  
|[CObArray::SetAtGrow](#setatgrow)|Legt den Wert für einen bestimmten Index fest; vergrößert das Array bei Bedarf.|  
|[CObArray::SetSize](#setsize)|Legt die Anzahl der Elemente im Array fest.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObArray::operator]](#operator_at)|Legt das Element am angegebenen Index fest oder ruft es ab.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Objektarrays C-Arrays ähneln, aber sie dynamisch verkleinern und nach Bedarf wachsen können.  
  
 Arrayindizes beginnen immer an Position 0. Sie können entscheiden, ob die obere Grenze beheben oder ermöglichen das Array zu erweitern, wenn Sie Elemente nach der aktuellen Grenze hinzufügen. Arbeitsspeicher ist die Obergrenze zusammenhängend zugewiesen, auch wenn einige Elemente null sind.  
  
 Unter Win32, die Größe einer `CObArray` Objekt ist nur auf den verfügbaren Arbeitsspeicher beschränkt.  
  
 Wie bei einer C#-Array, die Zugriffszeit für eine `CObArray` indizierte Element ist konstant und wird unabhängig von der Größe des Arrays.  
  
 `CObArray`enthält die `IMPLEMENT_SERIAL` Makro zur Unterstützung der Serialisierung und Sicherung der Elemente. Wenn ein Array von `CObject` Zeiger gespeichert ist, in ein Archiv, das mit den überladenen Operator zum Einfügen oder mit der `Serialize` Member-Funktion, `CObject` Element ist, zusammen mit dem Arrayindex wiederum serialisiert.  
  
 Wenn Sie eine Sicherung der einzelnen benötigen `CObject` Elemente in einem Array, müssen Sie die Tiefe der Festlegen der `CDumpContext` Objekt auf 1 oder größer.  
  
 Wenn ein `CObArray` Objekt gelöscht wird oder wenn dessen Elemente entfernt werden, nur die `CObject` Zeiger entfernt wurden, nicht die Objekte, die sie verweisen.  
  
> [!NOTE]
>  Vor dem Verwenden eines Arrays, verwenden Sie `SetSize`, um dessen Größe festzustellen, und weisen dafür Arbeitsspeicher zu. Wenn Sie `SetSize` nicht verwenden, kann das Hinzufügen von Elementen zu Ihrem Array dazu führen, dass es häufig neu zugeordnet und kopiert wird. Häufige Neuzuordnungen und Kopiervorgänge sind ineffizient und können zu einer Fragmentierung des Arbeitsspeichers führen.  
  
 Array-klassenableitung ist ähnlich wie die Liste Ableitung. Ausführliche Informationen über die Ableitung einer Klasse spezielle Liste, finden Sie im Artikel [Sammlungen](../../mfc/collections.md).  
  
> [!NOTE]
>  Verwenden Sie die `IMPLEMENT_SERIAL` Makro in der Implementierung der abgeleiteten Klasse, wenn das Array serialisiert werden soll.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CObArray`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcoll.h  
  
##  <a name="add"></a>CObArray::Add  
 Fügt ein neues Element am Ende ein Array, das Array um 1 vergrößert.  
  
```  
INT_PTR Add(CObject* newElement);
```  
  
### <a name="parameters"></a>Parameter  
 `newElement`  
 Die `CObject` Zeiger auf dieses Array hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des hinzugefügten Elements.  
  
### <a name="remarks"></a>Hinweise  
 Wenn [SetSize](#setsize) wurde verwendet, mit einer `nGrowBy` Wert größer als 1 ist, wird zusätzlicher Speicher zugeordnet werden. Allerdings wird die Obergrenze von nur 1 erhöht.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObArray::Add`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**Hinzufügen von INT_PTR (BYTE** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**Hinzufügen von INT_PTR (DWORD** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR Add( void\*** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**Hinzufügen von INT_PTR (LPCTSTR** `newElement` **); auslösen (CMemoryException\* );**<br /><br /> **INT_PTR Add(const CString&** `newElement` **);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**Hinzufügen von INT_PTR (UINT** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**Hinzufügen von INT_PTR (WORD** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections&#75;](../../mfc/codesnippet/cpp/cobarray-class_1.cpp)]  
  
 Die Ergebnisse dieses Programms sind wie folgt:  
  
 `Add example: A CObArray with 2 elements`  
  
 `[0] = a CAge at $442A 21`  
  
 `[1] = a CAge at $4468 40`  
  
##  <a name="append"></a>CObArray::Append  
 Rufen Sie diese Memberfunktion, um den Inhalt eines anderen Arrays an das Ende des angegebenen Arrays hinzuzufügen.  
  
```  
INT_PTR Append(const CObArray& src);
```  
  
### <a name="parameters"></a>Parameter  
 *src*  
 Die Quelle für die Elemente des Arrays hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des ersten Elements angefügt.  
  
### <a name="remarks"></a>Hinweise  
 Die Arrays müssen vom gleichen Typ sein.  
  
 Falls erforderlich, **Append** können zusätzlichen Speicher, um die Elemente des Arrays angefügt aufnehmen zuweisen.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObArray::Append`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**Fügen Sie INT_PTR (const CByteArray &** *Src* **);**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**Fügen Sie INT_PTR (const CDWordArray &** *Src* **);**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**Fügen Sie INT_PTR (const CPtrArray &** *Src* **);**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**Fügen Sie INT_PTR (const CStringArray &** *Src* **);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**Fügen Sie INT_PTR (const CUIntArray &** *Src* **);**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**Fügen Sie INT_PTR (const CWordArray &** *Src* **);**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections&#76;](../../mfc/codesnippet/cpp/cobarray-class_2.cpp)]  
  
##  <a name="copy"></a>CObArray::Copy  
 Rufen Sie diese Memberfunktion, um die Elemente im angegebenen Array mit den Elementen eines anderen Arrays des gleichen Typs zu überschreiben.  
  
```  
void Copy(const CObArray& src);
```  
  
### <a name="parameters"></a>Parameter  
 *src*  
 Die Quelle der Elemente, die in das Array kopiert werden.  
  
### <a name="remarks"></a>Hinweise  
 **Kopie** keinen Speicherplatz frei, jedoch bei Bedarf **Kopie** kann Speicher zusätzliche Aufnahme der Elemente in das Array kopiert.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObArray::Copy`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void-Kopie (const CByteArray &** *Src* **);**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void-Kopie (const CDWordArray &** *Src* **);**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void-Kopie (const CPtrArray &** *Src* **);**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void-Kopie (const CStringArray &** *Src* **);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void-Kopie (const CUIntArray &** *Src* **);**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void-Kopie (const CWordArray &** *Src* **);**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections&#77;](../../mfc/codesnippet/cpp/cobarray-class_3.cpp)]  
  
##  <a name="cobarray"></a>CObArray::CObArray  
 Erstellt ein leeres `CObject` Arrays.  
  
```  
CObArray();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Array nimmt ein Element zu einem Zeitpunkt.  
  
 Die folgende Tabelle zeigt die anderen Konstruktoren, die ähnlich sind `CObArray::CObArray`.  
  
|Klasse|Konstruktor|  
|-----------|-----------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**CByteArray ();**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**CDWordArray ();**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**CPtrArray ();**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CStringArray ();**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**CUIntArray ();**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**CWordArray ();**|  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#78;](../../mfc/codesnippet/cpp/cobarray-class_4.cpp)]  
  
##  <a name="elementat"></a>CObArray::ElementAt  
 Gibt einen temporären Verweis auf den Elementzeiger innerhalb des Arrays zurück.  
  
```  
CObject*& ElementAt(INT_PTR nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner oder gleich der von zurückgegebene Wert `GetUpperBound`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf eine `CObject` Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 Sie wird verwendet, um den linken Zuweisungsoperator für Arrays zu implementieren. Beachten Sie, dass dies eine erweiterte Funktion, die nur für spezielle Array Operatoren implementieren verwendet werden soll.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObArray::ElementAt`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**BYTE & ElementAt (INT_PTR** `nIndex` **);**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD & ElementAt (INT_PTR** `nIndex` **);**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void\*& ElementAt (INT_PTR** `nIndex` **);**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString & ElementAt (INT_PTR** `nIndex` **);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT & ElementAt (INT_PTR** `nIndex` **);**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD & ElementAt (INT_PTR** `nIndex` **);**|  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CObArray::GetSize](#getsize).  
  
##  <a name="freeextra"></a>CObArray::FreeExtra  
 Zusätzlichen Speicher, der belegt wurde, während das Array angebaut wurde frei.  
  
```  
void FreeExtra();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion hat keine Auswirkung auf die Größe oder die obere Grenze des Arrays.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObArray::FreeExtra`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void FreeExtra ();**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void FreeExtra ();**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void FreeExtra ();**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void FreeExtra ();**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void FreeExtra ();**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void FreeExtra ();**|  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CObArray::GetData](#getdata).  
  
##  <a name="getat"></a>CObArray::GetAt  
 Gibt das Arrayelement am angegebenen Index zurück.  
  
```  
CObject* GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner oder gleich der von zurückgegebene Wert `GetUpperBound`.  
  
### <a name="return-value"></a>Rückgabewert  
 Die `CObject` Zeiger Element derzeit an diesem Index.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Übergeben einen negativen Wert oder einen Wert größer als der von zurückgegebene Wert `GetUpperBound` führt dazu, dass eine fehlgeschlagene Assertion.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObArray::GetAt`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**BYTE GetAt (INT_PTR** `nIndex` **) const;**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD GetAt (INT_PTR** `nIndex` **) const;**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void\* GetAt (INT_PTR** `nIndex` **) const;**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString GetAt (INT_PTR** `nIndex` **) const;**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT GetAt (INT_PTR** `nIndex` **) const;**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD GetAt (INT_PTR** `nIndex` **) const;**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections&#79;](../../mfc/codesnippet/cpp/cobarray-class_5.cpp)]  
  
##  <a name="getcount"></a>CObArray::GetCount  
 Gibt die Anzahl der Arrayelemente.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Array.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Anzahl der Elemente im Array ab. Da Indizes nullbasiert sind, ist die Größe 1 größer als der größte Index.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObArray::GetCount`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR GetCount () const;**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR GetCount () const;**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR GetCount () const;**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR GetCount () const;**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR GetCount () const;**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR GetCount () const;**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections&#80;](../../mfc/codesnippet/cpp/cobarray-class_6.cpp)]  
  
##  <a name="getdata"></a>CObArray::GetData  
 Verwenden Sie diese Member-Funktion, um direkten Zugriff auf die Elemente im Array zu erhalten.  
  
```  
const CObject** GetData() const;  
  
CObject** GetData();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Array von `CObject` Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 Wenn keine Elemente verfügbar sind, `GetData` gibt null zurück.  
  
 Direkter Zugriff auf die Elemente eines Arrays können Sie schneller arbeiten helfen, seien Sie vorsichtig beim Aufrufen von `GetData`; alle Fehler, die Sie direkt vornehmen beeinflussen die Elemente des Arrays.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObArray::GetData`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**const BYTE\* GetData (const;) BYTE\* GetData ();**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**const DWORD\* GetData (const); DWORD\* GetData ();**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**const Void\* \* GetData () const; void\* \* GetData ();**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**const CString\* GetData (const;) CString\* GetData ();**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**const UINT\* GetData (const;) UINT\* GetData ();**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**const WORD\* GetData (const;) WORD\* GetData ();**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections&#81;](../../mfc/codesnippet/cpp/cobarray-class_7.cpp)]  
  
##  <a name="getsize"></a>CObArray::GetSize  
 Gibt die Größe des Arrays zurück.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Da Indizes nullbasiert sind, ist die Größe 1 größer als der größte Index.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObArray::GetSize`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR GetSize () const;**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR GetSize () const;**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR GetSize () const;**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR GetSize () const;**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR GetSize () const;**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR GetSize () const;**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections&#82;](../../mfc/codesnippet/cpp/cobarray-class_8.cpp)]  
  
##  <a name="getupperbound"></a>CObArray::GetUpperBound  
 Gibt die aktuellen Obergrenze für dieses Array zurück.  
  
```  
INT_PTR GetUpperBound() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index, der die obere Grenze (nullbasiert).  
  
### <a name="remarks"></a>Hinweise  
 Da Arrayindizes nullbasiert sind, gibt diese Funktion einen Wert 1 kleiner als `GetSize`.  
  
 Die Bedingung **GetUpperBound ()** = -1 gibt an, dass das Array keine Elemente enthält.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObArray::GetUpperBound`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR GetUpperBound () const;**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR GetUpperBound () const;**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR GetUpperBound () const;**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR GetUpperBound () const;**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR GetUpperBound () const;**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR GetUpperBound () const;**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections&83;](../../mfc/codesnippet/cpp/cobarray-class_9.cpp)]  
  
##  <a name="insertat"></a>CObArray::InsertAt  
 Fügt ein Element (oder alle Elemente in einem anderen Array) am angegebenen Index ein.  
  
```  
void InsertAt(
    INT_PTR nIndex,  
    CObject* newElement,  
    INT_PTR nCount = 1);

 
void InsertAt(
    INT_PTR nStartIndex,  
    CObArray* pNewArray);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Eine ganzzahlige Index, der größer als der zurückgegebene Wert möglicherweise `GetUpperBound`.  
  
 `newElement`  
 Die `CObject` Zeiger in diesem Array platziert werden. Ein `newElement` des Werts **NULL** ist zulässig.  
  
 `nCount`  
 Wie oft dieses Element liegen eingefügt (Standardwert: 1).  
  
 `nStartIndex`  
 Eine ganzzahlige Index, der größer als der zurückgegebene Wert möglicherweise `GetUpperBound`.  
  
 `pNewArray`  
 Ein anderes Array mit Elementen in diesem Array hinzugefügt werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Version der `InsertAt` Fügt ein Element (oder mehrere Kopien eines Elements) an einem angegebenen Index in einem Array. Bei diesem Vorgang werden Sie verschoben (durch erhöhen den Index) Verschiebt das vorhandene Element am Index, und es werden alle Elemente davor.  
  
 Die zweite Version fügt alle Elemente aus einem anderen `CObArray` -Auflistung, beginnend ab dem `nStartIndex` Position.  
  
 Die `SetAt` -Funktion hingegen ersetzt eine angegebene Arrayelement und alle Elemente werden nicht verschoben.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObArray::InsertAt`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void InsertAt( INT_PTR** `nIndex` **, BYTE** `newElement` **, int** `nCount` **= 1 );**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **void InsertAt( INT_PTR** `nStartIndex` **, CByteArray\*** `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void InsertAt( INT_PTR** `nIndex` **, DWORD** `newElement` **, int** `nCount` **= 1 );**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **void InsertAt( INT_PTR** `nStartIndex` **, CDWordArray\*** `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void InsertAt( INT_PTR** `nIndex` **, void\*** `newElement` **, int** `nCount` **= 1 );**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **void InsertAt( INT_PTR** `nStartIndex` **, CPtrArray\*** `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void InsertAt( INT_PTR** `nIndex` **, LPCTSTR** `newElement` **, int** `nCount` **= 1 );**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **void InsertAt (INT_PTR** `nStartIndex` **, CStringArray\* ** `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void InsertAt( INT_PTR** `nIndex` **, UINT** `newElement` **, int** `nCount` **= 1 );**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **void InsertAt( INT_PTR** `nStartIndex` **, CUIntArray\*** `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void InsertAt( INT_PTR** `nIndex` **, WORD** `newElement` **, int** `nCount` **= 1 );**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **void InsertAt( INT_PTR** `nStartIndex` **, CWordArray\*** `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections&#84;](../../mfc/codesnippet/cpp/cobarray-class_10.cpp)]  
  
 Die Ergebnisse dieses Programms sind wie folgt:  
  
 `InsertAt example: A CObArray with 3 elements`  
  
 `[0] = a CAge at $45C8 21`  
  
 `[1] = a CAge at $4646 30`  
  
 `[2] = a CAge at $4606 40`  
  
##  <a name="isempty"></a>CObArray::IsEmpty  
 Bestimmt, ob das Array leer ist.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Array leer ist; andernfalls 0.  
  
##  <a name="operator_at"></a>CObArray::operator]  
 Diese Indexoperatoren sind praktisch Ersatz für die `SetAt` und `GetAt` Funktionen.  
  
```  
CObject*& operator[](int_ptr nindex);  
CObject* operator[](int_ptr nindex) const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der first-Operator für Arrays, bei denen aufgerufen **const**, darf für (r) nach rechts oder links (l-Wert) einer zuweisungsanweisung verwendet werden. Die zweite Bezeichnung für **const** Arrays dürfen nur auf der rechten Seite verwendet werden.  
  
 Die Debugversion der Bibliothek bestätigt, wenn der Index (entweder auf der linken oder rechten Seite einer zuweisungsanweisung) außerhalb des gültigen Bereichs ist.  
  
 Die folgende Tabelle zeigt andere Operatoren, die ähnlich sind **CObArray::operator []**.  
  
|Klasse|Operator|  
|-----------|--------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**BYTE & -Operator [] (Int_ptr** `nindex` ** \);**<br /><br /> **BYTE-Operator [] (Int_ptr** `nindex` ** \) const;**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD & -Operator [] (Int_ptr** `nindex` ** \);**<br /><br /> **DWORD-Operator [] (Int_ptr** `nindex` ** \) const;**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void\*& operator [](int_ptr** `nindex` **\);**<br /><br /> **void\* -Operator [] (Int_ptr** `nindex` ** \) const;**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString- & -Operator [] (Int_ptr** `nindex` ** \);**<br /><br /> **CString-Operator [] (Int_ptr** `nindex` ** \) const;**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT & -Operator [] (Int_ptr** `nindex` ** \);**<br /><br /> **UINT-Operator [] (Int_ptr** `nindex` ** \) const;**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD & -Operator [] (Int_ptr** `nindex` ** \);**<br /><br /> **WORD-Operator [] (Int_ptr** `nindex` ** \) const;**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections&#88;](../../mfc/codesnippet/cpp/cobarray-class_11.cpp)]  
  
##  <a name="removeall"></a>CObArray::RemoveAll  
 Entfernt alle Zeiger aus diesem Array jedoch nicht tatsächlich die `CObject` Objekte.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie bereits das Array leer ist, funktioniert die Funktion weiterhin.  
  
 Die `RemoveAll` Funktion freigegeben, alle Speicher zum Speichern der Zeiger verwendet.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObArray::RemoveAll`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void RemoveAll ();**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void RemoveAll ();**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void RemoveAll ();**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void RemoveAll ();**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void RemoveAll ();**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void RemoveAll ();**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections&#85;](../../mfc/codesnippet/cpp/cobarray-class_12.cpp)]  
  
##  <a name="removeat"></a>CObArray::RemoveAt  
 Entfernt eine oder mehrere Elemente, beginnend am angegebenen Index in ein Array.  
  
```  
void RemoveAt(
    INT_PTR nIndex,  
    INT_PTR nCount = 1);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner oder gleich der von zurückgegebene Wert `GetUpperBound`.  
  
 `nCount`  
 Die Anzahl der zu entfernenden Elemente.  
  
### <a name="remarks"></a>Hinweise  
 In der werden verschoben Sie alle Elemente über die entfernten Elemente. Es verringert die obere Grenze des Arrays, aber keinen Speicherplatz frei.  
  
 Wenn Sie versuchen, mehr Elemente als in das Array über die Entfernung Punkt enthaltenen entfernen, überprüft dann die Debugversion der Bibliothek.  
  
 Die `RemoveAt` Funktion entfernt die `CObject` Zeiger aus dem Array jedoch nicht das Objekt selbst gelöscht.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObArray::RemoveAt`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void RemoveAt( INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1 );**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void RemoveAt( INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1 );**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void RemoveAt( INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1 );**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void RemoveAt( INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1 );**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void RemoveAt( INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1 );**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **, INT_PTR** *nCount* **= 1);**|  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections&#112;](../../mfc/codesnippet/cpp/cobarray-class_13.cpp)]  
  
 Die Ergebnisse dieses Programms sind wie folgt:  
  
 `RemoveAt example: A CObArray with 1 elements`  
  
 `[0] = a CAge at $4606 40`  
  
##  <a name="setat"></a>CObArray::SetAt  
 Legt das Arrayelement am angegebenen Index fest.  
  
```  
void SetAt(
    INT_PTR nIndex,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner oder gleich der von zurückgegebene Wert `GetUpperBound`.  
  
 `newElement`  
 Der Zeiger in dieses Array eingefügt werden sollen. Ein **NULL** Wert zulässig ist.  
  
### <a name="remarks"></a>Hinweise  
 `SetAt`das Array vergrößert wird nicht verursacht werden. Verwendung `SetAtGrow` , wenn das Array, das automatisch vergrößert werden soll.  
  
 Sie müssen sicherstellen, dass der Indexwert gültige Position im Array darstellt. Ist außerhalb des gültigen Bereichs, überprüft dann die Debugversion der Bibliothek.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObArray::SetAt`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void SetAt( INT_PTR** `nIndex` **, BYTE** `newElement` **);**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetAt( INT_PTR** `nIndex` **, DWORD** `newElement` **);**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void SetAt( INT_PTR** `nIndex` **, void\*** `newElement` **);**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetAt( INT_PTR** `nIndex` **, LPCTSTR** `newElement` **);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void SetAt( INT_PTR** `nIndex` **, UINT** `newElement` **);**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetAt( INT_PTR** `nIndex` **, WORD** `newElement` **);**|  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections&#86;](../../mfc/codesnippet/cpp/cobarray-class_14.cpp)]  
  
 Die Ergebnisse dieses Programms sind wie folgt:  
  
 `SetAt example: A CObArray with 2 elements`  
  
 `[0] = a CAge at $47E0 30`  
  
 `[1] = a CAge at $47A0 40`  
  
##  <a name="setatgrow"></a>CObArray::SetAtGrow  
 Legt das Arrayelement am angegebenen Index fest.  
  
```  
void SetAtGrow(
    INT_PTR nIndex,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 ist.  
  
 `newElement`  
 Der Zeiger dieses Array hinzugefügt werden. Ein **NULL** Wert zulässig ist.  
  
### <a name="remarks"></a>Hinweise  
 Das Array vergrößert automatisch bei Bedarf (d. h. die obere Grenze wird angepasst, um das neue Element aufzunehmen).  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObArray::SetAtGrow`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void SetAtGrow( INT_PTR** `nIndex` **, BYTE** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetAtGrow( INT_PTR** `nIndex` **, DWORD** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void SetAtGrow( INT_PTR** `nIndex` **, void\*** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` **, LPCTSTR** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void SetAtGrow( INT_PTR** `nIndex` **, UINT** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetAtGrow( INT_PTR** `nIndex` **, WORD** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections&#87;](../../mfc/codesnippet/cpp/cobarray-class_15.cpp)]  
  
 Die Ergebnisse dieses Programms sind wie folgt:  
  
 `SetAtGrow example: A CObArray with 4 elements`  
  
 `[0] = a CAge at $47C0 21`  
  
 `[1] = a CAge at $4800 40`  
  
 `[2] = NULL`  
  
 `[3] = a CAge at $4840 65`  
  
##  <a name="setsize"></a>CObArray::SetSize  
 Legt die Größe des ein leeres oder vorhandenes Array fest. belegt Speicher aus, falls erforderlich.  
  
```  
void SetSize(
    INT_PTR nNewSize,  
    INT_PTR nGrowBy = -1);
```  
  
### <a name="parameters"></a>Parameter  
 `nNewSize`  
 Die neue Arraygröße (Anzahl der Elemente). Muss größer als oder gleich 0 sein.  
  
 `nGrowBy`  
 Die minimale Anzahl der Element-Steckplätze zuordnen, wenn eine Erhöhung erforderlich ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die neue Größe kleiner als die alte Größe ist, wird das Array abgeschnitten, und alle nicht verwendeten Speicher freigegeben wird. Rufen Sie aus Leistungsgründen `SetSize` die Größe des Arrays festgelegt wird, bevor Sie sie verwenden. Dadurch müssen neu zuteilen und kopieren das Array jedes Mal, wenn ein Element hinzugefügt wird.  
  
 Die `nGrowBy` Parameter wirkt sich auf internen Speicher reservieren, während das Array wächst. Seine Verwendung nie wirkt sich auf die Größe des Arrays von gemeldeten `GetSize` und `GetUpperBound`.  
  
 Wenn die Größe des Arrays angewachsen ist, alle neu zugeordneten **CObject \* ** Zeiger auf NULL festgelegt werden.  
  
 Die folgende Tabelle zeigt die anderen Funktionen, die ähnlich sind `CObArray::SetSize`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void SetSize( INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1 );**<br /><br /> **throw (CMemoryException\* );**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetSize( INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1 );**<br /><br /> **throw (CMemoryException\* );**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void SetSize( INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1 );**<br /><br /> **throw (CMemoryException\* );**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetSize( INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1 );**<br /><br /> **throw (CMemoryException\* );**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void SetSize( INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1 );**<br /><br /> **throw (CMemoryException\* );**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetSize( INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1 );**<br /><br /> **throw (CMemoryException\* );**|  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CObArray::GetData](#getdata).  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CStringArray-Klasse](../../mfc/reference/cstringarray-class.md)   
 [CPtrArray-Klasse](../../mfc/reference/cptrarray-class.md)   
 [Leistungsfähiger](../../mfc/reference/cbytearray-class.md)   
 [CWordArray-Klasse](../../mfc/reference/cwordarray-class.md)   
 [CDWordArray-Klasse](../../mfc/reference/cdwordarray-class.md)

