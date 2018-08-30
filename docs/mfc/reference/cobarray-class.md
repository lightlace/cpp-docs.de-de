---
title: CObArray-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CObArray [MFC], CObArray
- CObArray [MFC], Add
- CObArray [MFC], Append
- CObArray [MFC], Copy
- CObArray [MFC], ElementAt
- CObArray [MFC], FreeExtra
- CObArray [MFC], GetAt
- CObArray [MFC], GetCount
- CObArray [MFC], GetData
- CObArray [MFC], GetSize
- CObArray [MFC], GetUpperBound
- CObArray [MFC], InsertAt
- CObArray [MFC], IsEmpty
- CObArray [MFC], RemoveAll
- CObArray [MFC], RemoveAt
- CObArray [MFC], SetAt
- CObArray [MFC], SetAtGrow
- CObArray [MFC], SetSize
ms.assetid: 27894efd-2370-4776-9ed9-24a98492af17
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5082490b9dd2e37090bac747e592b62ce51ac26a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43200901"
---
# <a name="cobarray-class"></a>CObArray-Klasse
Unterstützt Arrays mit `CObject` -Zeigern.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CObArray : public CObject  
```  
  
## <a name="members"></a>Member  
  
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
|[CObArray::GetData](#getdata)|Ermöglicht den Zugriff auf Elemente im Array. NULL kann sein.|  
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
  
 Arrayindizes starten immer an Position 0. Sie können entscheiden, ob beheben Sie die obere Grenze oder das Array, das erweitert, wenn Sie Elemente nach der aktuellen Grenze hinzufügen können. Arbeitsspeicher wird mit dem oberen Grenzwert, zusammenhängend zugeordnet, selbst wenn einige Elemente null sind.  
  
 Klicken Sie unter "Win32", "die Größe des eine `CObArray` Objekt ist nur auf den verfügbaren Arbeitsspeicher beschränkt.  
  
 Wie bei einer C-Array, die Zugriffszeit für eine `CObArray` indizierte Element ist konstant und ist unabhängig von der Größe des Arrays.  
  
 `CObArray` enthält das IMPLEMENT_SERIAL-Makro, um Serialisierung und die Sicherung der Elemente zu unterstützen. Wenn ein Array von `CObject` Zeiger befindet sich in ein Archiv, das mit den überladenen Operator zum Einfügen oder mit der `Serialize` Member-Funktion, `CObject` Element ist, zusammen mit dem Arrayindex im Gegenzug serialisiert.  
  
 Wenn Sie eine Sicherung einzelner benötigen `CObject` Elemente in einem Array, müssen Sie die Tiefe der Festlegen der `CDumpContext` Objekt auf 1 oder größer.  
  
 Wenn eine `CObArray` Objekt gelöscht wird oder wenn die Elemente werden entfernt, nur die `CObject` zeigenden Elemente entfernt werden, nicht die Objekte, die sie verweisen.  
  
> [!NOTE]
>  Vor dem Verwenden eines Arrays, verwenden Sie `SetSize`, um dessen Größe festzustellen, und weisen dafür Arbeitsspeicher zu. Wenn Sie `SetSize` nicht verwenden, kann das Hinzufügen von Elementen zu Ihrem Array dazu führen, dass es häufig neu zugeordnet und kopiert wird. Häufige Neuzuordnungen und Kopiervorgänge sind ineffizient und können zu einer Fragmentierung des Arbeitsspeichers führen.  
  
 Array-klassenableitung ist ähnlich wie die Ableitung der Liste. Informationen für die Ableitung einer Klasse spezielle Liste finden Sie im Artikel [Sammlungen](../../mfc/collections.md).  
  
> [!NOTE]
>  Sie müssen das IMPLEMENT_SERIAL-Makro in der Implementierung der abgeleiteten Klasse verwenden, wenn das Array serialisiert werden soll.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CObArray`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcoll.h  
  
##  <a name="add"></a>  CObArray::Add  
 Fügt ein neues Element am Ende eines Arrays, wachsenden Arrays um 1.  
  
```  
INT_PTR Add(CObject* newElement);
```  
  
### <a name="parameters"></a>Parameter  
 *newElement*  
 Die `CObject` Zeiger auf dieses Array hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des hinzugefügten Elements.  
  
### <a name="remarks"></a>Hinweise  
 Wenn [SetSize](#setsize) verwendet wurde mit einer *nGrowBy* Wert größer als 1, und klicken Sie dann auf zusätzlichen Arbeitsspeicher zugewiesen werden kann. Allerdings erhöht sich die obere Grenze nur 1.  
  
 Die folgende Tabelle zeigt die anderen Member-Funktionen, die ähnlich sind `CObArray::Add`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**Hinzufügen von INT_PTR (BYTE** `newElement` **);**<br /><br /> **auslösen (CMemoryException\* );**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**Hinzufügen von INT_PTR (DWORD** `newElement` **);**<br /><br /> **auslösen (CMemoryException\* );**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**Hinzufügen von INT_PTR ("void"** <strong>\*</strong> `newElement` **);**<br /><br /> **auslösen (CMemoryException\* );**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**Hinzufügen von INT_PTR (LPCTSTR** `newElement` **); auslösen (CMemoryException\* );**<br /><br /> **INT_PTR Add(const CString&** `newElement` **);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**Hinzufügen von INT_PTR (UINT** `newElement` **);**<br /><br /> **auslösen (CMemoryException\* );**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**Hinzufügen von INT_PTR (WORD** `newElement` **);**<br /><br /> **auslösen (CMemoryException\* );**|  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections#75](../../mfc/codesnippet/cpp/cobarray-class_1.cpp)]  
  
 Die Ergebnisse dieses Programms sind wie folgt aus:  
  
 `Add example: A CObArray with 2 elements`  
  
 `[0] = a CAge at $442A 21`  
  
 `[1] = a CAge at $4468 40`  
  
##  <a name="append"></a>  CObArray::Append  
 Rufen Sie diese Memberfunktion um den Inhalt eines anderen Arrays am Ende des angegebenen Arrays hinzuzufügen.  
  
```  
INT_PTR Append(const CObArray& src);
```  
  
### <a name="parameters"></a>Parameter  
 *src*  
 Die Quelle der Elemente, die das Array angefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des ersten Elements angefügt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Arrays müssen vom gleichen Typ sein.  
  
 Bei Bedarf `Append` auch zusätzlichen Speicher zur Aufnahme der Elemente, die an das Array angefügt reservieren.  
  
 Die folgende Tabelle zeigt die anderen Member-Funktionen, die ähnlich sind `CObArray::Append`.  
  
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
  
 [!code-cpp[NVC_MFCCollections#76](../../mfc/codesnippet/cpp/cobarray-class_2.cpp)]  
  
##  <a name="copy"></a>  CObArray::Copy  
 Rufen Sie diese Memberfunktion, um die Elemente des angegebenen Arrays mit den Elementen eines anderen Arrays des gleichen Typs zu überschreiben.  
  
```  
void Copy(const CObArray& src);
```  
  
### <a name="parameters"></a>Parameter  
 *src*  
 Die Quelle der Elemente in das Array kopiert werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 `Copy` Gibt Arbeitsspeicher frei, jedoch, falls erforderlich, `Copy` auch zusätzlichen Speicher zur Aufnahme der in das Array kopierten Elemente reservieren.  
  
 Die folgende Tabelle zeigt die anderen Member-Funktionen, die ähnlich sind `CObArray::Copy`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**"void" Kopie (const CByteArray &** *Src* **);**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**"void" Kopie (const CDWordArray &** *Src* **);**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**"void" Kopie (const CPtrArray &** *Src* **);**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**"void" Kopie (const CStringArray &** *Src* **);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**"void" Kopie (const CUIntArray &** *Src* **);**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**"void" Kopie (const CWordArray &** *Src* **);**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections#77](../../mfc/codesnippet/cpp/cobarray-class_3.cpp)]  
  
##  <a name="cobarray"></a>  CObArray::CObArray  
 Erstellt ein leeres `CObject` Zeigerarray.  
  
```  
CObArray();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Array wird ein Element zu einem Zeitpunkt.  
  
 Die folgende Tabelle zeigt die anderen Konstruktoren, die ähnlich wie `CObArray::CObArray`.  
  
|Klasse|Konstruktor|  
|-----------|-----------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**CByteArray ();**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**CDWordArray ();**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**CPtrArray ();**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CStringArray ();**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**CUIntArray ();**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**CWordArray ();**|  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#78](../../mfc/codesnippet/cpp/cobarray-class_4.cpp)]  
  
##  <a name="elementat"></a>  CObArray::ElementAt  
 Gibt einen temporären Verweis auf den Elementzeiger innerhalb des Arrays zurück.  
  
```  
CObject*& ElementAt(INT_PTR nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner als oder gleich den Rückgabewert von `GetUpperBound`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf eine `CObject` Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 Es wird zum Implementieren von des linken Seite Zuweisungsoperators für Arrays verwendet. Beachten Sie, dass es sich um eine erweiterte Funktion handelt, die nur für spezielle Array Operatoren implementieren verwendet werden soll.  
  
 Die folgende Tabelle zeigt die anderen Member-Funktionen, die ähnlich sind `CObArray::ElementAt`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**& ElementAt BYTE (INT_PTR** `nIndex` **);**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD & ElementAt (INT_PTR** `nIndex` **);**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**"void"\*& ElementAt (INT_PTR** `nIndex` **);**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString & ElementAt (INT_PTR** `nIndex` **);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT & ElementAt (INT_PTR** `nIndex` **);**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD & ElementAt (INT_PTR** `nIndex` **);**|  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CObArray::GetSize](#getsize).  
  
##  <a name="freeextra"></a>  CObArray::FreeExtra  
 Zusätzlichen Speicher, der belegt wurde, während das Array geworden war frei.  
  
```  
void FreeExtra();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion hat keine Auswirkungen auf die Größe oder die obere Grenze des Arrays.  
  
 Die folgende Tabelle zeigt die anderen Member-Funktionen, die ähnlich sind `CObArray::FreeExtra`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**"void" FreeExtra ();**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**"void" FreeExtra ();**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**"void" FreeExtra ();**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**"void" FreeExtra ();**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**"void" FreeExtra ();**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**"void" FreeExtra ();**|  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CObArray::GetData](#getdata).  
  
##  <a name="getat"></a>  CObArray::GetAt  
 Gibt das Arrayelement am angegebenen Index zurück.  
  
```  
CObject* GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner als oder gleich den Rückgabewert von `GetUpperBound`.  
  
### <a name="return-value"></a>Rückgabewert  
 Die `CObject` Zeiger-Element derzeit an diesem Index.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Übergeben einen negativen Wert oder einen Wert größer als der Wert, der vom `GetUpperBound` führt dazu, eine fehlgeschlagene Assertion.  
  
 Die folgende Tabelle zeigt die anderen Member-Funktionen, die ähnlich sind `CObArray::GetAt`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**BYTE-GetAt (INT_PTR** `nIndex` **) const;**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD GetAt (INT_PTR** `nIndex` **) const;**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**"void"\* GetAt (INT_PTR** `nIndex` **) const;**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString GetAt (INT_PTR** `nIndex` **) const;**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT GetAt (INT_PTR** `nIndex` **) const;**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD GetAt (INT_PTR** `nIndex` **) const;**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections#79](../../mfc/codesnippet/cpp/cobarray-class_5.cpp)]  
  
##  <a name="getcount"></a>  CObArray::GetCount  
 Gibt die Anzahl der Elemente des Arrays zurück.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Array.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Anzahl der Elemente im Array abzurufen. Da Indizes nullbasiert sind, ist die Größe 1 größer als der größte Index.  
  
 Die folgende Tabelle zeigt die anderen Member-Funktionen, die ähnlich sind `CObArray::GetCount`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR GetCount( ) const;**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR GetCount( ) const;**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR GetCount( ) const;**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR GetCount( ) const;**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR GetCount( ) const;**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR GetCount( ) const;**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections#80](../../mfc/codesnippet/cpp/cobarray-class_6.cpp)]  
  
##  <a name="getdata"></a>  CObArray::GetData  
 Verwenden Sie diese Memberfunktion auf, um direkten Zugriff auf die Elemente im Array zu erhalten.  
  
```  
const CObject** GetData() const;  
  
CObject** GetData();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Array von `CObject` Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 Wenn keine Elemente verfügbar sind, `GetData` gibt einen null-Wert zurück.  
  
 Zwar die direkter Zugriff auf die Elemente eines Arrays Sie schneller arbeiten kann, seien Sie vorsichtig, beim Aufrufen von `GetData`; alle Fehler, die Sie, direkt vornehmen Auswirkungen auf die Elemente des Arrays.  
  
 Die folgende Tabelle zeigt die anderen Member-Funktionen, die ähnlich sind `CObArray::GetData`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**const BYTE\* GetData (const;) BYTE\* GetData ();**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**const DWORD\* GetData (const); DWORD\* GetData ();**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**const Void\* \* GetData () const; "void"\* \* GetData ();**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**const CString\* GetData (const;) CString\* GetData ();**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**const UINT\* GetData (const;) UINT\* GetData ();**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**const WORD\* GetData (const;) WORD\* GetData ();**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections#81](../../mfc/codesnippet/cpp/cobarray-class_7.cpp)]  
  
##  <a name="getsize"></a>  CObArray::GetSize  
 Gibt die Größe des Arrays zurück.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Da die Indizes nullbasiert sind, ist die Größe 1 größer als der größte Index.  
  
 Die folgende Tabelle zeigt die anderen Member-Funktionen, die ähnlich sind `CObArray::GetSize`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR GetSize( ) const;**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR GetSize( ) const;**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR GetSize( ) const;**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR GetSize( ) const;**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR GetSize( ) const;**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR GetSize( ) const;**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections#82](../../mfc/codesnippet/cpp/cobarray-class_8.cpp)]  
  
##  <a name="getupperbound"></a>  CObArray::GetUpperBound  
 Gibt die aktuellen Obergrenze dieses Arrays zurück.  
  
```  
INT_PTR GetUpperBound() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index, der die obere Grenze (nullbasiert).  
  
### <a name="remarks"></a>Hinweise  
 Da Arrayindizes nullbasiert sind, gibt diese Funktion einen Wert von 1 kleiner als `GetSize`.  
  
 Die Bedingung `GetUpperBound( )` =-1 bedeutet, dass das Array ohne Elemente enthält.  
  
 Die folgende Tabelle zeigt die anderen Member-Funktionen, die ähnlich sind `CObArray::GetUpperBound`.  
  
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
  
 [!code-cpp[NVC_MFCCollections#83](../../mfc/codesnippet/cpp/cobarray-class_9.cpp)]  
  
##  <a name="insertat"></a>  CObArray::InsertAt  
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
 *nIndex*  
 Eine ganzzahlige Index, die größer als der von zurückgegebene Wert möglicherweise `GetUpperBound`.  
  
 *newElement*  
 Die `CObject` Zeiger auf die in diesem Array platziert werden. Ein *NewElement* der Wert NULL zulässig ist.  
  
 *nCount*  
 Die Anzahl der Male, die dieses Element eingefügt (Standardwert: 1).  
  
 *nStartIndex*  
 Eine ganzzahlige Index, die größer als der von zurückgegebene Wert möglicherweise `GetUpperBound`.  
  
 *pNewArray*  
 Ein anderes Array mit Elementen in diesem Array hinzugefügt werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Version des `InsertAt` Fügt ein Element (oder mehrere Kopien eines Elements) an einem angegebenen Index in einem Array. In den Prozess nach oben verschoben (durch Erhöhen des Indexes) das vorhandene Element an diesem Index und verschiebt, um alle übergeordneten Elemente.  
  
 Die zweite Version fügt alle Elemente aus einer anderen `CObArray` -Auflistung, beginnend ab der *nStartIndex* Position.  
  
 Die `SetAt` -Funktion, im Gegensatz dazu ersetzt ein angegebenes Array-Element und alle Elemente werden nicht verschoben.  
  
 Die folgende Tabelle zeigt die anderen Member-Funktionen, die ähnlich sind `CObArray::InsertAt`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**"void" InsertAt (INT_PTR** `nIndex` **, BYTE** `newElement` **, Int** `nCount` **= 1);**<br /><br /> **auslösen (CMemoryException\* );**<br /><br /> **"void" InsertAt (INT_PTR** `nStartIndex` **, CByteArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **auslösen (CMemoryException\* );**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**"void" InsertAt (INT_PTR** `nIndex` **, DWORD** `newElement` **, Int** `nCount` **= 1);**<br /><br /> **auslösen (CMemoryException\* );**<br /><br /> **"void" InsertAt (INT_PTR** `nStartIndex` **, CDWordArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **auslösen (CMemoryException\* );**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**"void" InsertAt (INT_PTR** `nIndex` **, "void"** <strong>\*</strong> `newElement` **, Int** `nCount` **= 1);**<br /><br /> **auslösen (CMemoryException\* );**<br /><br /> **"void" InsertAt (INT_PTR** `nStartIndex` **, CPtrArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **auslösen (CMemoryException\* );**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**"void" InsertAt (INT_PTR** `nIndex` **, LPCTSTR** `newElement` **, Int** `nCount` **= 1);**<br /><br /> **auslösen (CMemoryException\* );**<br /><br /> **"void" InsertAt (INT_PTR** `nStartIndex` **, CStringArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **auslösen (CMemoryException\* );**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**"void" InsertAt (INT_PTR** `nIndex` **, "uint"** `newElement` **, Int** `nCount` **= 1);**<br /><br /> **auslösen (CMemoryException\* );**<br /><br /> **"void" InsertAt (INT_PTR** `nStartIndex` **, CUIntArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **auslösen (CMemoryException\* );**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**"void" InsertAt (INT_PTR** `nIndex` **, WORD** `newElement` **, Int** `nCount` **= 1);**<br /><br /> **auslösen (CMemoryException\* );**<br /><br /> **"void" InsertAt (INT_PTR** `nStartIndex` **, CWordArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **auslösen (CMemoryException\* );**|  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections#84](../../mfc/codesnippet/cpp/cobarray-class_10.cpp)]  
  
 Die Ergebnisse dieses Programms sind wie folgt aus:  
  
 `InsertAt example: A CObArray with 3 elements`  
  
 `[0] = a CAge at $45C8 21`  
  
 `[1] = a CAge at $4646 30`  
  
 `[2] = a CAge at $4606 40`  
  
##  <a name="isempty"></a>  CObArray::IsEmpty  
 Bestimmt, ob das Array leer ist.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Array leer ist; andernfalls 0.  
  
##  <a name="operator_at"></a>  CObArray::operator]  
 Diese-Indexoperatoren sind eine praktische Ersatz für die `SetAt` und `GetAt` Funktionen.  
  
```  
CObject*& operator[](int_ptr nindex);  
CObject* operator[](int_ptr nindex) const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der erste Operator aufgerufen wird, für Arrays, die nicht **const**, kann auf der rechten Seite (r) oder der linken Seite (l-Wert) einer zuweisungsanweisung verwendet werden. Das zweite für aufgerufen **const** Arrays kann nur auf der rechten Seite verwendet werden.  
  
 Die Debugversion der Bibliothek wird bestätigt, den der Feldindex (entweder auf der linken oder rechten Seite einer zuweisungsanweisung) liegt außerhalb des gültigen Bereichs.  
  
 Die folgende Tabelle zeigt die anderen Operatoren, die ähnlich wie `CObArray::operator []`.  
  
|Klasse|Operator|  
|-----------|--------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**Operator & BYTE [] (Int_ptr** `nindex`  **\);**<br /><br /> **BYTE []-Operator (Int_ptr** `nindex`  **\) const;**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD & -Operator [] (Int_ptr** `nindex`  **\);**<br /><br /> **DWORD-Operator [] (Int_ptr** `nindex`  **\) const;**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**"void"\*&-Operator [] (Int_ptr** `nindex`  **\);**<br /><br /> **"void"\* []-Operator (Int_ptr** `nindex`  **\) const;**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString & -Operator [] (Int_ptr** `nindex`  **\);**<br /><br /> **CString-Operator [] (Int_ptr** `nindex`  **\) const;**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT & -Operator [] (Int_ptr** `nindex`  **\);**<br /><br /> **UINT-Operator [] (Int_ptr** `nindex`  **\) const;**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD & -Operator [] (Int_ptr** `nindex`  **\);**<br /><br /> **WORD-Operator [] (Int_ptr** `nindex`  **\) const;**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections#88](../../mfc/codesnippet/cpp/cobarray-class_11.cpp)]  
  
##  <a name="removeall"></a>  CObArray::RemoveAll  
 Entfernt alle Zeiger aus diesem Array aber nicht tatsächlich die `CObject` Objekte.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn bereits das Array leer ist, wird die Funktion weiterhin funktioniert.  
  
 Die `RemoveAll` Funktion gibt alle Speicher für Zeiger-Speicherung verwendet, frei.  
  
 Die folgende Tabelle zeigt die anderen Member-Funktionen, die ähnlich sind `CObArray::RemoveAll`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void RemoveAll( );**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void RemoveAll( );**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void RemoveAll( );**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void RemoveAll( );**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void RemoveAll( );**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void RemoveAll( );**|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections#85](../../mfc/codesnippet/cpp/cobarray-class_12.cpp)]  
  
##  <a name="removeat"></a>  CObArray::RemoveAt  
 Entfernt eine oder mehrere Elemente, die an einem angegebenen Index in einem Array ab.  
  
```  
void RemoveAt(
    INT_PTR nIndex,  
    INT_PTR nCount = 1);
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner als oder gleich den Rückgabewert von `GetUpperBound`.  
  
 *nCount*  
 Die Anzahl der zu entfernenden Elemente.  
  
### <a name="remarks"></a>Hinweise  
 In den Prozess wechselt es alle Elemente über die entfernten Elemente. Es verringert die obere Grenze des Arrays, jedoch keinen Speicherplatz frei.  
  
 Wenn Sie versuchen, entfernen Sie mehr Elemente als im oberhalb der entfernen-Punkt-Array enthalten sind, bestätigt Sie dann die Debugversion der Bibliothek.  
  
 Die `RemoveAt` Funktion entfernt die `CObject` Zeiger von Arrays, aber es wird das Objekt selbst nicht gelöscht.  
  
 Die folgende Tabelle zeigt die anderen Member-Funktionen, die ähnlich sind `CObArray::RemoveAt`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**"void" RemoveAt (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**"void" RemoveAt (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**"void" RemoveAt (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**"void" RemoveAt (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**"void" RemoveAt (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**"void" RemoveAt (INT_PTR** `nIndex` **, INT_PTR** *nCount* **= 1);**|  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections#112](../../mfc/codesnippet/cpp/cobarray-class_13.cpp)]  
  
 Die Ergebnisse dieses Programms sind wie folgt aus:  
  
 `RemoveAt example: A CObArray with 1 elements`  
  
 `[0] = a CAge at $4606 40`  
  
##  <a name="setat"></a>  CObArray::SetAt  
 Legt das Arrayelement am angegebenen Index fest.  
  
```  
void SetAt(
    INT_PTR nIndex,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner als oder gleich den Rückgabewert von `GetUpperBound`.  
  
 *newElement*  
 Der Objektzeiger, die in diesem Array eingefügt werden. Es ist ein NULL-Wert zulässig.  
  
### <a name="remarks"></a>Hinweise  
 `SetAt` das Array, wachsen verursacht nicht. Verwendung `SetAtGrow` , wenn Sie das Array, das automatisch vergrößert werden soll.  
  
 Sie müssen sicherstellen, dass Ihr Indexwert eine gültige Position im Array darstellt. Wenn es außerhalb des gültigen Bereichs ist, bestätigt Sie dann die Debugversion der Bibliothek.  
  
 Die folgende Tabelle zeigt die anderen Member-Funktionen, die ähnlich sind `CObArray::SetAt`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**"void" SetAt (INT_PTR** `nIndex` **, BYTE** `newElement` **);**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**"void" SetAt (INT_PTR** `nIndex` **, DWORD** `newElement` **);**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**"void" SetAt (INT_PTR** `nIndex` **, "void"** <strong>\*</strong> `newElement` **);**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**"void" SetAt (INT_PTR** `nIndex` **, LPCTSTR** `newElement` **);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**"void" SetAt (INT_PTR** `nIndex` **, "uint"** `newElement` **);**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**"void" SetAt (INT_PTR** `nIndex` **, WORD** `newElement` **);**|  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections#86](../../mfc/codesnippet/cpp/cobarray-class_14.cpp)]  
  
 Die Ergebnisse dieses Programms sind wie folgt aus:  
  
 `SetAt example: A CObArray with 2 elements`  
  
 `[0] = a CAge at $47E0 30`  
  
 `[1] = a CAge at $47A0 40`  
  
##  <a name="setatgrow"></a>  CObArray::SetAtGrow  
 Legt das Arrayelement am angegebenen Index fest.  
  
```  
void SetAtGrow(
    INT_PTR nIndex,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Eine ganze Zahl-Index, der größer als oder gleich 0 ist.  
  
 *newElement*  
 Der Objektzeiger, die diesem Array hinzugefügt werden. Es ist ein NULL-Wert zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Das Array automatisch vergrößert, bei Bedarf (d. h. die obere Grenze wird angepasst, um das neue Element).  
  
 Die folgende Tabelle zeigt die anderen Member-Funktionen, die ähnlich sind `CObArray::SetAtGrow`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**"void" SetAtGrow (INT_PTR** `nIndex` **, BYTE** `newElement` **);**<br /><br /> **auslösen (CMemoryException\* );**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**"void" SetAtGrow (INT_PTR** `nIndex` **, DWORD** `newElement` **);**<br /><br /> **auslösen (CMemoryException\* );**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**"void" SetAtGrow (INT_PTR** `nIndex` **, "void"** <strong>\*</strong> `newElement` **);**<br /><br /> **auslösen (CMemoryException\* );**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**"void" SetAtGrow (INT_PTR** `nIndex` **, LPCTSTR** `newElement` **);**<br /><br /> **auslösen (CMemoryException\* );**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**"void" SetAtGrow (INT_PTR** `nIndex` **, "uint"** `newElement` **);**<br /><br /> **auslösen (CMemoryException\* );**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**"void" SetAtGrow (INT_PTR** `nIndex` **, WORD** `newElement` **);**<br /><br /> **auslösen (CMemoryException\* );**|  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) eine Liste der `CAge` Klasse, die in allen Beispielen der Auflistung verwendet.  
  
 [!code-cpp[NVC_MFCCollections#87](../../mfc/codesnippet/cpp/cobarray-class_15.cpp)]  
  
 Die Ergebnisse dieses Programms sind wie folgt aus:  
  
 `SetAtGrow example: A CObArray with 4 elements`  
  
 `[0] = a CAge at $47C0 21`  
  
 `[1] = a CAge at $4800 40`  
  
 `[2] = NULL`  
  
 `[3] = a CAge at $4840 65`  
  
##  <a name="setsize"></a>  CObArray::SetSize  
 Legt die Größe eines Arrays von leeren oder vorhandenen; belegt Speicher aus, falls erforderlich.  
  
```  
void SetSize(
    INT_PTR nNewSize,  
    INT_PTR nGrowBy = -1);
```  
  
### <a name="parameters"></a>Parameter  
 *nNewSize*  
 Die neue Arraygröße (Anzahl von Elementen). Muss größer als oder gleich 0 sein.  
  
 *nGrowBy*  
 Die minimale Anzahl der Element-Slots zugewiesen werden, wenn eine Vergrößerung erforderlich ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die neue Größe kleiner als die alte Größe ist, klicken Sie dann das Array abgeschnitten, und alle nicht verwendeten Arbeitsspeicher wird freigegeben. Rufen Sie aus Effizienzgründen `SetSize` die Größe des Arrays festgelegt wird, bevor Sie ihn verwenden. Dies verhindert, dass die Notwendigkeit zum erneuten zuweisen, und kopieren das Array jedes Mal, wenn ein Element hinzugefügt wird.  
  
 Die *nGrowBy* Parameter wirkt sich auf interne speicherbelegung während das Array vergrößert. Die Verwendung nie wirkt sich auf die Größe des Arrays von gemeldeten `GetSize` und `GetUpperBound`.  
  
 Wenn die Größe des Arrays angewachsen ist, alle neu zugeordneten **CObject** <strong>\*</strong> Zeigern auf NULL festgelegt werden.  
  
 Die folgende Tabelle zeigt die anderen Member-Funktionen, die ähnlich sind `CObArray::SetSize`.  
  
|Klasse|Memberfunktion|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**"void" SetSize (INT_PTR** `nNewSize` **, Int** `nGrowBy` **=-1);**<br /><br /> **auslösen (CMemoryException\* );**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**"void" SetSize (INT_PTR** `nNewSize` **, Int** `nGrowBy` **=-1);**<br /><br /> **auslösen (CMemoryException\* );**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**"void" SetSize (INT_PTR** `nNewSize` **, Int** `nGrowBy` **=-1);**<br /><br /> **auslösen (CMemoryException\* );**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**"void" SetSize (INT_PTR** `nNewSize` **, Int** `nGrowBy` **=-1);**<br /><br /> **auslösen (CMemoryException\* );**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**"void" SetSize (INT_PTR** `nNewSize` **, Int** `nGrowBy` **=-1);**<br /><br /> **auslösen (CMemoryException\* );**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**"void" SetSize (INT_PTR** `nNewSize` **, Int** `nGrowBy` **=-1);**<br /><br /> **auslösen (CMemoryException\* );**|  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CObArray::GetData](#getdata).  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CStringArray-Klasse](../../mfc/reference/cstringarray-class.md)   
 [CPtrArray-Klasse](../../mfc/reference/cptrarray-class.md)   
 [CByteArray-Klasse](../../mfc/reference/cbytearray-class.md)   
 [CWordArray-Klasse](../../mfc/reference/cwordarray-class.md)   
 [CDWordArray-Klasse](../../mfc/reference/cdwordarray-class.md)
