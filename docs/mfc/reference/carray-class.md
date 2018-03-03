---
title: CArray-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CArray
- AFXTEMPL/CArray
- AFXTEMPL/CArray::CArray
- AFXTEMPL/CArray::Add
- AFXTEMPL/CArray::Append
- AFXTEMPL/CArray::Copy
- AFXTEMPL/CArray::ElementAt
- AFXTEMPL/CArray::FreeExtra
- AFXTEMPL/CArray::GetAt
- AFXTEMPL/CArray::GetCount
- AFXTEMPL/CArray::GetData
- AFXTEMPL/CArray::GetSize
- AFXTEMPL/CArray::GetUpperBound
- AFXTEMPL/CArray::InsertAt
- AFXTEMPL/CArray::IsEmpty
- AFXTEMPL/CArray::RemoveAll
- AFXTEMPL/CArray::RemoveAt
- AFXTEMPL/CArray::SetAt
- AFXTEMPL/CArray::SetAtGrow
- AFXTEMPL/CArray::SetSize
dev_langs:
- CPP
helpviewer_keywords:
- CArray [MFC], CArray
- CArray [MFC], Add
- CArray [MFC], Append
- CArray [MFC], Copy
- CArray [MFC], ElementAt
- CArray [MFC], FreeExtra
- CArray [MFC], GetAt
- CArray [MFC], GetCount
- CArray [MFC], GetData
- CArray [MFC], GetSize
- CArray [MFC], GetUpperBound
- CArray [MFC], InsertAt
- CArray [MFC], IsEmpty
- CArray [MFC], RemoveAll
- CArray [MFC], RemoveAt
- CArray [MFC], SetAt
- CArray [MFC], SetAtGrow
- CArray [MFC], SetSize
ms.assetid: fead8b00-4cfd-4625-ad0e-251df62ba92f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 85e7bf9518ad96e5a67f2d19d3729e5813d3f84d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="carray-class"></a>CArray-Klasse
Unterstützt Arrays, die C-Arrays ähneln, jedoch können dynamisch verkleinern oder Vergrößern nach Bedarf.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class TYPE, class ARG_TYPE = const TYPE&>  
class CArray : public CObject  
```  
  
#### <a name="parameters"></a>Parameter  
 `TYPE`  
 Ein Vorlagenparameter, der den Typ der im Array gespeicherten Objekte angibt. `TYPE`ist ein Parameter, die zurückgegebene `CArray`.  
  
 `ARG` *_* `TYPE`  
 Ein Vorlagenparameter, der den Argumenttyp, der verwendet wird angibt, um den Zugriff auf Objekte im Array gespeichert. Häufig einen Verweis auf `TYPE`. `ARG_TYPE`ist ein Parameter, der an übergebene `CArray`.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CArray::CArray](#carray)|Erstellt ein leeres Array.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CArray::Add](#add)|Fügt am Ende des Arrays ein Element hinzu; vergrößert das Array bei Bedarf.|  
|[CArray::Append](#append)|Fügt ein anderes Array in das Array; Vergrößert das Array bei Bedarf|  
|[CArray::Copy](#copy)|Kopiert ein anderes Array in das Array; vergrößert das Array bei Bedarf.|  
|[CArray::ElementAt](#elementat)|Gibt einen temporären Verweis auf den Elementzeiger innerhalb des Arrays zurück.|  
|[CArray::FreeExtra](#freeextra)|Gibt den gesamten nicht verwendeten Arbeitsspeicher über der aktuellen Obergrenze frei.|  
|[CArray::GetAt](#getat)|Gibt den Wert an einem bestimmten Index zurück.|  
|[CArray::GetCount](#getcount)|Ruft die Anzahl der Elemente im Array ab.|  
|[CArray::GetData](#getdata)|Ermöglicht den Zugriff auf Elemente im Array. Kann **NULL**.|  
|[CArray::GetSize](#getsize)|Ruft die Anzahl der Elemente im Array ab.|  
|[CArray::GetUpperBound](#getupperbound)|Gibt den größten gültigen Index zurück.|  
|[CArray::InsertAt](#insertat)|Fügt ein Element (oder alle Elemente in einem anderen Array) am angegebenen Index ein.|  
|[CArray::IsEmpty](#isempty)|Bestimmt, ob das Array leer ist.|  
|[CArray::RemoveAll](#removeall)|Entfernt alle Elemente aus diesem Array.|  
|[CArray::RemoveAt](#removeat)|Entfernt ein Element an einem spezifischen Index.|  
|[CArray::SetAt](#setat)|Legt den Wert für einen bestimmten Index fest; Array darf nicht vergrößert werden.|  
|[CArray::SetAtGrow](#setatgrow)|Legt den Wert für einen bestimmten Index fest; vergrößert das Array bei Bedarf.|  
|[SetSize](#setsize)|Legt die Anzahl der Elemente im Array fest.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[operator&#91;&#93;](#operator_at)|Legt das Element am angegebenen Index fest oder ruft es ab.|  
  
## <a name="remarks"></a>Hinweise  
 Arrayindizes starten immer an Position 0. Sie können entscheiden, ob die obere Grenze beheben oder aktivieren das Array zu erweitern, wenn Sie Elemente nach der aktuellen gebunden hinzufügen. Speicher ist zusammenhängend die Obergrenze belegt, auch wenn einige Elemente null sind.  
  
> [!NOTE]
>  Die meisten Methoden, die die Größe einer `CArray` Objekt oder Elemente zu verwenden, fügen [Memcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md) Elemente verschoben. Dies ist ein Problem aufgetreten, da `memcpy_s` ist nicht kompatibel mit der alle Objekte, die den Konstruktor aufgerufen werden müssen. Wenn die Elemente in der `CArray` sind nicht kompatibel mit `memcpy_s`, müssen Sie ein neues erstellen `CArray` der entsprechenden Größe. Sie müssen dann verwenden, [CArray::Copy](#copy) und [CArray::SetAt](#setat) zum Füllen des neuen Arrays, da diese Methoden anstelle der Zuweisungsoperator verwendet `memcpy_s`.  
  
 Wie bei einem C-Array, die Uhrzeit des Zugriffs für einen `CArray` indizierte Element ist konstant und ist unabhängig von der Größe des Arrays.  
  
> [!TIP]
>  Vor dem Verwenden eines Arrays, verwenden [SetSize](#setsize) , dessen Größe festzustellen, und weisen dafür Arbeitsspeicher. Wenn Sie `SetSize` nicht verwenden, kann das Hinzufügen von Elementen zu Ihrem Array dazu führen, dass es häufig neu zugeordnet und kopiert wird. Häufige Neuzuordnungen und Kopiervorgänge sind ineffizient und können zu einer Fragmentierung des Arbeitsspeichers führen.  
  
 Wenn Sie eine Sicherung einzelner Elemente in einem Array benötigen, müssen Sie die Tiefe der Festlegen der [CDumpContext](../../mfc/reference/cdumpcontext-class.md) Objekt auf 1 oder größer.  
  
 Bestimmte Memberfunktionen der Klasse Aufruf globale Hilfsfunktionen, die angepasst werden müssen, für die meisten Verwendungen von der `CArray` Klasse. Finden Sie im Thema [Auflistungsklasse](../../mfc/reference/collection-class-helpers.md) im Abschnitt MFC-Makros und Globals.  
  
 Array-klassenableitung gleicht Liste Ableitung ab.  
  
 Weitere Informationen zur Verwendung von `CArray`, finden Sie im Artikel [Sammlungen](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CArray`  
  
## <a name="requirements"></a>Anforderungen  
 `Header:`afxtempl.h  
  
##  <a name="add"></a>CArray::Add  
 Fügt ein neues Element am Ende eines Arrays, Arrays um 1 vergrößert.  
  
```  
INT_PTR Add(ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parameter  
 `ARG_TYPE`  
 Template-Parameter, die den Typ der Argumente verweisen auf Elemente in diesem Array angeben.  
  
 `newElement`  
 Das Element mit diesem Array hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des hinzugefügten Elements.  
  
### <a name="remarks"></a>Hinweise  
 Wenn [SetSize](#setsize) wurde mit verwendet ein `nGrowBy` Wert größer als 1, und klicken Sie dann auf zusätzlichen Arbeitsspeicher zugeordnet werden kann. Allerdings wird die obere Grenze nur 1 erhöhen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#22](../../mfc/codesnippet/cpp/carray-class_1.cpp)]  
  
##  <a name="append"></a>CArray::Append  
 Rufen Sie diese Memberfunktion um den Inhalt eines Arrays an das Ende einer anderen hinzuzufügen.  
  
```  
INT_PTR Append(const CArray& src);
```  
  
### <a name="parameters"></a>Parameter  
 *src*  
 Die Quelle der Elemente, die ein Array angefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des ersten Elements angefügt.  
  
### <a name="remarks"></a>Hinweise  
 Die Arrays sein des gleichen Typs.  
  
 Bei Bedarf **Append** möglicherweise belegen zusätzlichen Speicherplatz, um die Elemente, die angefügt werden, auf das Array aufnehmen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#23](../../mfc/codesnippet/cpp/carray-class_2.cpp)]  
  
##  <a name="carray"></a>CArray::CArray  
 Erstellt ein leeres Array.  
  
```  
CArray();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Array wird ein Element zu einem Zeitpunkt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#24](../../mfc/codesnippet/cpp/carray-class_3.cpp)]  
  
##  <a name="copy"></a>CArray::Copy  
 Verwenden Sie diese Memberfunktion auf, die Elemente eines Arrays in ein anderes kopiert.  
  
```  
void Copy(const CArray& src);
```  
  
### <a name="parameters"></a>Parameter  
 *src*  
 Die Quelle der Elemente in ein Array kopiert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion, um die Elemente eines Arrays mit den Elementen von einem anderen Array zu überschreiben.  
  
 **Kopie** keinen Speicherplatz frei, aber bei Bedarf **Kopie** möglicherweise belegen zusätzlichen Speicherplatz, um die in das Array kopierten Elemente aufzunehmen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#25](../../mfc/codesnippet/cpp/carray-class_4.cpp)]  
  
##  <a name="elementat"></a>CArray::ElementAt  
 Gibt einen temporären Verweis auf das angegebene Element innerhalb des Arrays zurück.  
  
```  
TYPE& ElementAt(INT_PTR nIndex);  
const TYPE& ElementAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 ist und kleiner oder gleich den Rückgabewert von [GetUpperBound](#getupperbound).  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf ein Arrayelement.  
  
### <a name="remarks"></a>Hinweise  
 Sie wird verwendet, um den linken Zuweisungsoperator für Arrays zu implementieren.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetSize](#getsize).  
  
##  <a name="freeextra"></a>CArray::FreeExtra  
 Gibt alle zusätzlichen Speicherplatz, der belegt wurde, während das Array vergrößert wurde.  
  
```  
void FreeExtra();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion hat keine Auswirkungen auf die Größe oder die obere Grenze des Arrays.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetData](#getdata).  
  
##  <a name="getat"></a>CArray::GetAt  
 Gibt das Arrayelement am angegebenen Index zurück.  
  
```  
TYPE& GetAt(INT_PTR nIndex);  
const TYPE& GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *DATENTYP*  
 Der Vorlagenparameter, der den Typ der Elemente des Arrays angibt.  
  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 ist und kleiner oder gleich den Rückgabewert von [GetUpperBound](#getupperbound).  
  
### <a name="return-value"></a>Rückgabewert  
 Das Arrayelement zurzeit für diesen Index.  
  
### <a name="remarks"></a>Hinweise  
 Übergeben einen negativen Wert oder einen Wert größer als der Rückgabewert von `GetUpperBound` führt zu einem fehlgeschlagenen Assertion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#26](../../mfc/codesnippet/cpp/carray-class_5.cpp)]  
  
##  <a name="getcount"></a>CArray::GetCount  
 Gibt die Anzahl der Elemente des Arrays zurück.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Array.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Abrufen der Anzahl der Elemente im Array. Da die Indizes nullbasiert sind, ist die Größe größer als der größte Index 1. Beim Aufrufen dieser Methode werden dieselben Ergebnisse wie beim Generieren der [CArray::GetSize](#getsize) Methode.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#27](../../mfc/codesnippet/cpp/carray-class_6.cpp)]  
  
##  <a name="getdata"></a>CArray::GetData  
 Verwenden Sie diese Memberfunktion auf, um direkten Zugriff auf die Elemente in einem Array zu erhalten.  
  
```  
const TYPE* GetData() const; 
TYPE* GetData();
```  
  
### <a name="parameters"></a>Parameter  
 *DATENTYP*  
 Der Vorlagenparameter, der den Typ der Elemente des Arrays angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Arrayelement.  
  
### <a name="remarks"></a>Hinweise  
 Wenn keine Elemente verfügbar ist, enthält `GetData` gibt einen null-Wert zurück.  
  
 Beim direkter Zugriff auf die Elemente eines Arrays mit schneller Arbeit helfen, seien Sie vorsichtig beim Aufrufen von `GetData`; alle Fehler, die Sie direkt vornehmen Auswirkungen auf die Elemente des Arrays.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#28](../../mfc/codesnippet/cpp/carray-class_7.cpp)]  
  
##  <a name="getsize"></a>CArray::GetSize  
 Gibt die Größe des Arrays zurück.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Da die Indizes nullbasiert sind, ist die Größe größer als der größte Index 1. Beim Aufrufen dieser Methode werden dieselben Ergebnisse wie beim Generieren der [CArray::GetCount](#getcount) Methode.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#29](../../mfc/codesnippet/cpp/carray-class_8.cpp)]  
  
##  <a name="getupperbound"></a>CArray::GetUpperBound  
 Gibt die aktuellen Obergrenze für dieses Array zurück.  
  
```  
INT_PTR GetUpperBound() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Da Arrayindizes nullbasiert sind, gibt diese Funktion einen Wert von 1 kleiner als `GetSize`.  
  
 Die Bedingung **GetUpperBound ()** =-1 bedeutet, dass das Array keine Elemente enthält.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CArray::GetAt](#getat).  
  
##  <a name="insertat"></a>CArray::InsertAt  
 Die erste Version des `InsertAt` Fügt ein Element (oder mehrere Kopien eines Elements) an einem angegebenen Index in einem Array.  
  
```  
void InsertAt(
    INT_PTR nIndex,
    ARG_TYPE newElement,  
    INT_PTR nCount = 1);
 
void InsertAt(
    INT_PTR nStartIndex,  
    CArray* pNewArray);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Eine ganzzahlige Index, die größer als der zurückgegebene Wert möglicherweise `GetUpperBound`.  
  
 `ARG_TYPE`  
 Der Vorlagenparameter, den Typ der Elemente im Array angibt.  
  
 `newElement`  
 Das Element im Array abgelegt werden soll.  
  
 `nCount`  
 Die Anzahl der Häufigkeit, mit die dieses Element liegen eingefügt (Standardwert: 1).  
  
 `nStartIndex`  
 Eine ganzzahlige Index, die größer als der zurückgegebene Wert möglicherweise [GetUpperBound](#getupperbound).  
  
 `pNewArray`  
 Ein anderes Array mit Elementen mit diesem Array hinzugefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Im Prozess, werden Sie verschoben (durch erhöhen den Index) Verschiebt das vorhandene Element in dieser Index, und es werden alle Elemente davor.  
  
 Die zweite Version fügt alle Elemente aus einer anderen `CArray` -Auflistung, beginnend ab dem `nStartIndex` Position.  
  
 Die `SetAt` -Funktion im Gegensatz dazu ersetzt ein angegebenes Array-Element und alle Elemente werden nicht verschoben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#30](../../mfc/codesnippet/cpp/carray-class_9.cpp)]  
  
##  <a name="isempty"></a>CArray::IsEmpty  
 Bestimmt, ob das Array leer ist.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Array keine Elemente enthält; andernfalls 0.  
  
##  <a name="operator_at"></a>CArray::operator\[\]  
 Diese-Indexoperatoren werden praktische Ersatz für die [SetAt](#setat) und [GetAt](#getat) Funktionen.  
  
```  
TYPE& operator[](int_ptr nindex);  
const TYPE& operator[](int_ptr nindex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *DATENTYP*  
 Der Vorlagenparameter, den Typ der Elemente im Array angibt.  
  
 `nIndex`  
 Der Index des Elements zugegriffen werden.  
  
### <a name="remarks"></a>Hinweise  
 Der erste Operator aufgerufen für Arrays, die nicht **const**, auf der rechten Seite (r) oder linken (l-Wert) einer zuweisungsanweisung verwendet werden kann. Die zweite für aufgerufen **const** Arrays dürfen nur auf der rechten Seite verwendet werden.  
  
 Die Debugversion der Bibliothek wird bestätigt, wenn der Index (entweder auf der linken oder rechten Seite einer zuweisungsanweisung) außerhalb des gültigen Bereichs ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#34](../../mfc/codesnippet/cpp/carray-class_10.cpp)]  
  
##  <a name="relocateelements"></a>CArray::RelocateElements  
 Verschiebt Daten in einen neuen Puffer an, wenn das Array vergrößert oder verkleinert werden soll.  
  
```  
template<class TYPE, class ARG_TYPE>  
AFX_INLINE void CArray<TYPE, ARG_TYPE>::RelocateElements(
    TYPE* pNewData,  
    const TYPE* pData,  
    INT_PTR nCount);
```  
  
### <a name="parameters"></a>Parameter  
 `pNewData`  
 Ein neuer Puffer für das Array von Elementen.  
  
 `pData`  
 Das alte Array von Elementen.  
  
 `nCount`  
 Anzahl der Elemente im alten Array.  
  
### <a name="remarks"></a>Hinweise  
 `pNewData`ist immer groß genug für alle der `pData` Elemente.  
  
 Die [CArray](../../mfc/reference/carray-class.md) Implementierung verwendet diese Methode, um die alten Daten in einen neuen Puffer kopieren, wenn das Array vergrößert oder verkleinert werden soll (Wenn [SetSize](#setsize) oder [FreeExtra](#freeextra) heißen). Die standardmäßige Implementierung kopiert nur die Daten.  
  
 Für Arrays, in dem ein Element enthält einen Zeiger auf einen Member oder eine andere Struktur enthält einen Zeiger auf eine der Elemente des Arrays werden die Zeiger in plain Kopie nicht aktualisiert. In diesem Fall können Sie Zeiger korrigieren, indem Sie implementieren eine Spezialisierung der `RelocateElements` mit den relevanten Typen. Sie sind auch für das Kopieren von Daten verantwortlich.  
  
##  <a name="removeall"></a>CArray::RemoveAll  
 Entfernt alle Elemente aus diesem Array.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie bereits das Array leer ist, funktioniert die Funktion weiterhin.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#31](../../mfc/codesnippet/cpp/carray-class_11.cpp)]  
  
##  <a name="removeat"></a>CArray::RemoveAt  
 Entfernt eine oder mehrere Elemente, beginnend am angegebenen Index in ein Array.  
  
```  
void RemoveAt(
    INT_PTR nIndex,  
    INT_PTR nCount = 1);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 ist und kleiner oder gleich den Rückgabewert von [GetUpperBound](#getupperbound).  
  
 `nCount`  
 Die Anzahl der zu entfernenden Elemente.  
  
### <a name="remarks"></a>Hinweise  
 Im Prozess verschoben unten alle Elemente, die sich über die entfernten Elemente. Es verringert die obere Grenze des Arrays, aber keinen Speicherplatz frei.  
  
 Wenn Sie versuchen, entfernen Sie weitere Elemente im Array oberhalb der Entfernung Punkt enthalten sind, überprüft dann die Debugversion der Bibliothek.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#32](../../mfc/codesnippet/cpp/carray-class_12.cpp)]  
  
##  <a name="setat"></a>CArray::SetAt  
 Legt das Arrayelement am angegebenen Index fest.  
  
```  
void SetAt(INT_PTR nIndex, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 ist und kleiner oder gleich den Rückgabewert von [GetUpperBound](#getupperbound).  
  
 `ARG_TYPE`  
 Der Vorlagenparameter Angabe des Typs der Argumente, die für Verweise auf Elemente des Arrays verwendet.  
  
 `newElement`  
 Der neue Elementwert an der angegebenen Position gespeichert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 `SetAt`Vergrößert das Array wird nicht verursacht werden. Verwendung [SetAtGrow](#setatgrow) , wenn das Array die automatische Vergrößerung aktiviert werden soll.  
  
 Sie müssen sicherstellen, dass Ihre Indexwert eine gültige Position im Array darstellt. Wenn es außerhalb des gültigen Bereichs handelt, bestätigt klicken Sie dann die Debugversion der Bibliothek.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetAt](#getat).  
  
##  <a name="setatgrow"></a>CArray::SetAtGrow  
 Legt das Arrayelement am angegebenen Index fest.  
  
```  
void SetAtGrow(INT_PTR nIndex, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Ein Integer-Index, der größer als oder gleich 0 ist.  
  
 `ARG_TYPE`  
 Der Vorlagenparameter, den Typ der Elemente im Array angibt.  
  
 `newElement`  
 Das Element mit diesem Array hinzugefügt werden. Ein **NULL** Wert ist zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Das Array vergrößert automatisch bei Bedarf (d. h. die obere Grenze wird angepasst, dass das neue Element).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#33](../../mfc/codesnippet/cpp/carray-class_13.cpp)]  
  
##  <a name="setsize"></a>SetSize  
 Legt die Größe eines Arrays leer oder vorhandene; belegt Speicher aus, falls erforderlich.  
  
```  
void SetSize(
    INT_PTR nNewSize,  
    INT_PTR nGrowBy = -1);
```  
  
### <a name="parameters"></a>Parameter  
 `nNewSize`  
 Das neue Arraygröße (Anzahl der Elemente). Muss größer als oder gleich 0 sein.  
  
 `nGrowBy`  
 Die minimale Anzahl der Element-Slots zugewiesen werden, wenn eine Größenzuwachs erforderlich ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die neue Größe kleiner als die alte Größe ist, wird das Array abgeschnitten, und alle nicht verwendeter Arbeitsspeicher freigegeben wird.  
  
 Verwenden Sie diese Funktion, um die Größe des Arrays festgelegt, bevor Sie beginnen mit dem Array. Wenn Sie `SetSize` nicht verwenden, kann das Hinzufügen von Elementen zu Ihrem Array dazu führen, dass es häufig neu zugeordnet und kopiert wird. Häufige Neuzuordnungen und Kopiervorgänge sind ineffizient und können zu einer Fragmentierung des Arbeitsspeichers führen.  
  
 Die `nGrowBy` Parameter wirkt sich auf interne speicherbelegung, während das Array zunimmt. Verwendungsmöglichkeiten nie wirkt sich auf die Arraygröße von gemeldeten [GetSize](#getsize) und [GetUpperBound](#getupperbound). Wenn der Standardwert verwendet wird, reserviert MFC in eine Möglichkeit zur Vermeidung von Fragmentierung des Arbeitsspeichers und erhöht die Effizienz in den meisten Fällen berechnet.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetData](#getdata).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel erfassen](../../visual-cpp-samples.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CObArray-Klasse](../../mfc/reference/cobarray-class.md)   
 [Hilfsfunktionen für die Auflistungsklasse](../../mfc/reference/collection-class-helpers.md)
