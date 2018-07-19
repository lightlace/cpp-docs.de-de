---
title: CArray-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53089439c3857dd947a263a80f3330aad3f03f7b
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37339435"
---
# <a name="carray-class"></a>CArray-Klasse
Unterstützt Arrays, die C-Arrays ähneln, jedoch können dynamisch verkleinern oder Vergrößern nach Bedarf.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class TYPE, class ARG_TYPE = const TYPE&>  
class CArray : public CObject  
```  
  
#### <a name="parameters"></a>Parameter  
 *TYPE*  
 Ein Vorlagenparameter, der den Typ der im Array gespeicherten Objekte angibt. *Typ* ist ein Parameter, der von zurückgegebene `CArray`.  
  
 *ARG* *_* *TYP*  
 Ein Vorlagenparameter, der der Argumenttyp angegeben wird, der Zugriff auf Objekte im Array gespeicherten verwendet wird. Häufig einen Verweis auf *Typ*. *ARG_TYPE* ist ein Parameter, die übergeben werden `CArray`.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CArray::CArray](#carray)|Erstellt ein leeres Array.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CArray::Add](#add)|Fügt am Ende des Arrays ein Element hinzu; vergrößert das Array bei Bedarf.|  
|[CArray::Append](#append)|Ein anderes Array an das Array angefügt. Vergrößert das Array bei Bedarf|  
|[CArray::Copy](#copy)|Kopiert ein anderes Array in das Array; vergrößert das Array bei Bedarf.|  
|[CArray::ElementAt](#elementat)|Gibt einen temporären Verweis auf den Elementzeiger innerhalb des Arrays zurück.|  
|[CArray::FreeExtra](#freeextra)|Gibt den gesamten nicht verwendeten Arbeitsspeicher über der aktuellen Obergrenze frei.|  
|[CArray::GetAt](#getat)|Gibt den Wert an einem bestimmten Index zurück.|  
|[CArray::GetCount](#getcount)|Ruft die Anzahl der Elemente im Array ab.|  
|[CArray::GetData](#getdata)|Ermöglicht den Zugriff auf Elemente im Array. NULL kann sein.|  
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
 Arrayindizes starten immer an Position 0. Sie können entscheiden, ob die obere Grenze beheben oder aktivieren das Array, das erweitert, wenn Sie Elemente nach der aktuellen gebunden hinzufügen. Arbeitsspeicher wird mit dem oberen Grenzwert, zusammenhängend zugeordnet, selbst wenn einige Elemente null sind.  
  
> [!NOTE]
>  Die meisten Methoden, die die Größe einer `CArray` Objekt oder zum Hinzufügen von Elementen, die sie verwenden [Memcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md) Elemente zu verschieben. Dies ist ein Problem, da `memcpy_s` ist nicht kompatibel mit der alle Objekte, die den Konstruktor aufgerufen werden müssen. Wenn die Elemente in der `CArray` sind nicht kompatibel mit `memcpy_s`, müssen Sie ein neues erstellen `CArray` von geeigneter Größe. Sie müssen dann verwenden, [CArray::Copy](#copy) und [CArray::SetAt](#setat) das neue Array aufgefüllt, da diese Methoden, einen Zuweisungsoperator, anstelle von verwenden `memcpy_s`.  
  
 Wie bei einer C-Array, die Zugriffszeit für eine `CArray` indizierte Element ist konstant und ist unabhängig von der Größe des Arrays.  
  
> [!TIP]
>  Verwenden Sie vor dem Verwenden eines Arrays, [SetSize](#setsize) , dessen Größe festzustellen, und weisen dafür Arbeitsspeicher. Wenn Sie `SetSize` nicht verwenden, kann das Hinzufügen von Elementen zu Ihrem Array dazu führen, dass es häufig neu zugeordnet und kopiert wird. Häufige Neuzuordnungen und Kopiervorgänge sind ineffizient und können zu einer Fragmentierung des Arbeitsspeichers führen.  
  
 Wenn Sie eine Sicherung der einzelnen Elemente in einem Array benötigen, müssen Sie die Tiefe der Festlegen der [CDumpContext](../../mfc/reference/cdumpcontext-class.md) -Objekts, 1 oder größer.  
  
 Bestimmte Memberfunktionen dieser Klasse rufen globale Hilfsfunktionen, die angepasst werden müssen, für die meisten Verwendungen von der `CArray` Klasse. Finden Sie im Thema [Auflistungsklasse](../../mfc/reference/collection-class-helpers.md) in der MFC-Makros und Globals-Abschnitt.  
  
 Array-klassenableitung ähnelt Ableitung der Liste aus.  
  
 Weitere Informationen zur Verwendung von `CArray`, finden Sie im Artikel [Sammlungen](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CArray`  
  
## <a name="requirements"></a>Anforderungen  
 `Header:` afxtempl.h  
  
##  <a name="add"></a>  CArray::Add  
 Fügt ein neues Element am Ende eines Arrays, wachsenden Arrays um 1.  
  
```  
INT_PTR Add(ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parameter  
 *ARG_TYPE*  
 Der Vorlagenparameter, der den Typ der Argumente, die Verweise auf Elemente im Array angibt.  
  
 *newElement*  
 Das Element, das in diesem Array hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des hinzugefügten Elements.  
  
### <a name="remarks"></a>Hinweise  
 Wenn [SetSize](#setsize) verwendet wurde mit einer `nGrowBy` Wert größer als 1, und klicken Sie dann auf zusätzlichen Arbeitsspeicher zugewiesen werden kann. Allerdings erhöht sich die obere Grenze nur 1.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#22](../../mfc/codesnippet/cpp/carray-class_1.cpp)]  
  
##  <a name="append"></a>  CArray::Append  
 Rufen Sie diese Memberfunktion um den Inhalt eines Arrays am Ende eines anderen hinzufügen.  
  
```  
INT_PTR Append(const CArray& src);
```  
  
### <a name="parameters"></a>Parameter  
 *src*  
 Die Quelle der Elemente, die ein Array angefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des ersten Elements angefügt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Arrays müssen vom gleichen Typ sein.  
  
 Bei Bedarf `Append` auch zusätzlichen Speicher zur Aufnahme der Elemente, die an das Array angefügt reservieren.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#23](../../mfc/codesnippet/cpp/carray-class_2.cpp)]  
  
##  <a name="carray"></a>  CArray::CArray  
 Erstellt ein leeres Array.  
  
```  
CArray();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Array wird ein Element zu einem Zeitpunkt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#24](../../mfc/codesnippet/cpp/carray-class_3.cpp)]  
  
##  <a name="copy"></a>  CArray::Copy  
 Verwenden Sie diese Memberfunktion auf, um die Elemente eines Arrays in ein anderes kopieren.  
  
```  
void Copy(const CArray& src);
```  
  
### <a name="parameters"></a>Parameter  
 *src*  
 Die Quelle der Elemente in ein Array kopiert werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion, um die Elemente eines Arrays mit den Elementen eines anderen Arrays zu überschreiben.  
  
 `Copy` Gibt Arbeitsspeicher frei, jedoch, falls erforderlich, `Copy` auch zusätzlichen Speicher zur Aufnahme der in das Array kopierten Elemente reservieren.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#25](../../mfc/codesnippet/cpp/carray-class_4.cpp)]  
  
##  <a name="elementat"></a>  CArray::ElementAt  
 Gibt einen temporären Verweis auf das angegebene Element im Array zurück.  
  
```  
TYPE& ElementAt(INT_PTR nIndex);  
const TYPE& ElementAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner als oder gleich den Rückgabewert von [GetUpperBound](#getupperbound).  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf ein Arrayelement.  
  
### <a name="remarks"></a>Hinweise  
 Es wird zum Implementieren von des linken Seite Zuweisungsoperators für Arrays verwendet.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetSize](#getsize).  
  
##  <a name="freeextra"></a>  CArray::FreeExtra  
 Zusätzlichen Speicher, der belegt wurde, während das Array geworden war frei.  
  
```  
void FreeExtra();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion hat keine Auswirkungen auf die Größe oder die obere Grenze des Arrays.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetData](#getdata).  
  
##  <a name="getat"></a>  CArray::GetAt  
 Gibt das Arrayelement am angegebenen Index zurück.  
  
```  
TYPE& GetAt(INT_PTR nIndex);  
const TYPE& GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *TYPE*  
 Template-Parameter, die den Typ der Elemente des Arrays angeben.  
  
 *nIndex*  
 Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner als oder gleich den Rückgabewert von [GetUpperBound](#getupperbound).  
  
### <a name="return-value"></a>Rückgabewert  
 Das Arrayelement derzeit an diesem Index.  
  
### <a name="remarks"></a>Hinweise  
 Übergeben einen negativen Wert oder einen Wert größer als der Wert, der vom `GetUpperBound` führt dazu, eine fehlgeschlagene Assertion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#26](../../mfc/codesnippet/cpp/carray-class_5.cpp)]  
  
##  <a name="getcount"></a>  CArray::GetCount  
 Gibt die Anzahl der Elemente des Arrays zurück.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Array.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Anzahl der Elemente im Array abzurufen. Da Indizes nullbasiert sind, ist die Größe 1 größer als der größte Index. Das Aufrufen dieser Methode generiert das gleiche Ergebnis wie die [CArray::GetSize](#getsize) Methode.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#27](../../mfc/codesnippet/cpp/carray-class_6.cpp)]  
  
##  <a name="getdata"></a>  CArray::GetData  
 Verwenden Sie diese Memberfunktion auf, um direkten Zugriff auf die Elemente in einem Array zu erhalten.  
  
```  
const TYPE* GetData() const; 
TYPE* GetData();
```  
  
### <a name="parameters"></a>Parameter  
 *TYPE*  
 Template-Parameter, die den Typ der Elemente des Arrays angeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Arrayelement.  
  
### <a name="remarks"></a>Hinweise  
 Wenn keine Elemente verfügbar sind, `GetData` gibt einen null-Wert zurück.  
  
 Zwar die direkter Zugriff auf die Elemente eines Arrays Sie schneller arbeiten kann, seien Sie vorsichtig, beim Aufrufen von `GetData`; alle Fehler, die Sie, direkt vornehmen Auswirkungen auf die Elemente des Arrays.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#28](../../mfc/codesnippet/cpp/carray-class_7.cpp)]  
  
##  <a name="getsize"></a>  CArray::GetSize  
 Gibt die Größe des Arrays zurück.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Da Indizes nullbasiert sind, ist die Größe 1 größer als der größte Index. Das Aufrufen dieser Methode generiert das gleiche Ergebnis wie die [CArray::GetCount](#getcount) Methode.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#29](../../mfc/codesnippet/cpp/carray-class_8.cpp)]  
  
##  <a name="getupperbound"></a>  CArray::GetUpperBound  
 Gibt die aktuellen Obergrenze dieses Arrays zurück.  
  
```  
INT_PTR GetUpperBound() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Da Arrayindizes nullbasiert sind, gibt diese Funktion einen Wert von 1 kleiner als `GetSize`.  
  
 Die Bedingung `GetUpperBound( )` =-1 bedeutet, dass das Array ohne Elemente enthält.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CArray::GetAt](#getat).  
  
##  <a name="insertat"></a>  CArray::InsertAt  
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
 *nIndex*  
 Eine ganzzahlige Index, die größer als der von zurückgegebene Wert möglicherweise `GetUpperBound`.  
  
 *ARG_TYPE*  
 Der Vorlagenparameter, den Typ der Elemente im Array angibt.  
  
 *newElement*  
 Das Element, das in diesem Array platziert werden.  
  
 *nCount*  
 Die Anzahl der Male, die dieses Element eingefügt (Standardwert: 1).  
  
 *nStartIndex*  
 Eine ganzzahlige Index, die größer als der von zurückgegebene Wert möglicherweise [GetUpperBound](#getupperbound).  
  
 *pNewArray*  
 Ein anderes Array mit Elementen in diesem Array hinzugefügt werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 In den Prozess nach oben verschoben (durch Erhöhen des Indexes) das vorhandene Element an diesem Index und verschiebt, um alle übergeordneten Elemente.  
  
 Die zweite Version fügt alle Elemente aus einer anderen `CArray` -Auflistung, beginnend ab der *nStartIndex* Position.  
  
 Die `SetAt` -Funktion, im Gegensatz dazu ersetzt ein angegebenes Array-Element und alle Elemente werden nicht verschoben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#30](../../mfc/codesnippet/cpp/carray-class_9.cpp)]  
  
##  <a name="isempty"></a>  CArray::IsEmpty  
 Bestimmt, ob das Array leer ist.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, wenn das Array ohne Elemente enthält; andernfalls 0.  
  
##  <a name="operator_at"></a>  CArray::operator \[\]  
 Diese-Indexoperatoren sind eine praktische Ersatz für die ["SetAt"](#setat) und [GetAt](#getat) Funktionen.  
  
```  
TYPE& operator[](int_ptr nindex);  
const TYPE& operator[](int_ptr nindex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *TYPE*  
 Der Vorlagenparameter, den Typ der Elemente im Array angibt.  
  
 *nIndex*  
 Der Index des Elements auf die zugegriffen werden.  
  
### <a name="remarks"></a>Hinweise  
 Der erste Operator aufgerufen wird, für Arrays, die nicht **const**, kann auf der rechten Seite (r) oder der linken Seite (l-Wert) einer zuweisungsanweisung verwendet werden. Das zweite für aufgerufen **const** Arrays kann nur auf der rechten Seite verwendet werden.  
  
 Die Debugversion der Bibliothek wird bestätigt, den der Feldindex (entweder auf der linken oder rechten Seite einer zuweisungsanweisung) liegt außerhalb des gültigen Bereichs.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#34](../../mfc/codesnippet/cpp/carray-class_10.cpp)]  
  
##  <a name="relocateelements"></a>  CArray::RelocateElements  
 Verschiebt Daten in einen neuen Puffer an, wenn das Array vergrößert oder verkleinert werden soll.  
  
```  
template<class TYPE, class ARG_TYPE>  
AFX_INLINE void CArray<TYPE, ARG_TYPE>::RelocateElements(
    TYPE* pNewData,  
    const TYPE* pData,  
    INT_PTR nCount);
```  
  
### <a name="parameters"></a>Parameter  
 *pNewData*  
 Einen neuen Puffer für das Array von Elementen.  
  
 *pData*  
 Das alte Array von Elementen.  
  
 *nCount*  
 Die Anzahl der Elemente in der alten Array.  
  
### <a name="remarks"></a>Hinweise  
 *pNewData* ist immer groß genug für alle der *pData* Elemente.  
  
 Die [CArray](../../mfc/reference/carray-class.md) Implementierung, die diese Methode verwendet, um die alten Daten in einen neuen Puffer zu kopieren, wenn das Array vergrößert oder verkleinert werden soll (Wenn [SetSize](#setsize) oder [FreeExtra](#freeextra) bezeichnet werden). Die standardmäßige Implementierung werden nur die Daten kopiert.  
  
 Für Arrays, in dem ein Element enthält einen Zeiger auf einen Member oder eine andere Struktur enthält einen Zeiger auf eine der Elemente des Arrays werden die Zeiger nicht in einfache Kopie aktualisiert. In diesem Fall können Sie Zeiger beheben, indem Sie implementieren eine Spezialisierung der `RelocateElements` mit den entsprechenden Typen. Sie sind auch zuständig für das Kopieren von Daten.  
  
##  <a name="removeall"></a>  CArray::RemoveAll  
 Entfernt alle Elemente aus diesem Array.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn bereits das Array leer ist, wird die Funktion weiterhin funktioniert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#31](../../mfc/codesnippet/cpp/carray-class_11.cpp)]  
  
##  <a name="removeat"></a>  CArray::RemoveAt  
 Entfernt eine oder mehrere Elemente, die an einem angegebenen Index in einem Array ab.  
  
```  
void RemoveAt(
    INT_PTR nIndex,  
    INT_PTR nCount = 1);
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner als oder gleich den Rückgabewert von [GetUpperBound](#getupperbound).  
  
 *nCount*  
 Die Anzahl der zu entfernenden Elemente.  
  
### <a name="remarks"></a>Hinweise  
 In den Prozess wechselt es alle Elemente über die entfernten Elemente. Es verringert die obere Grenze des Arrays, jedoch keinen Speicherplatz frei.  
  
 Wenn Sie versuchen, entfernen Sie mehr Elemente als im oberhalb der entfernen-Punkt-Array enthalten sind, bestätigt Sie dann die Debugversion der Bibliothek.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#32](../../mfc/codesnippet/cpp/carray-class_12.cpp)]  
  
##  <a name="setat"></a>  CArray::SetAt  
 Legt das Arrayelement am angegebenen Index fest.  
  
```  
void SetAt(INT_PTR nIndex, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner als oder gleich den Rückgabewert von [GetUpperBound](#getupperbound).  
  
 *ARG_TYPE*  
 Der Vorlagenparameter, die den Typ der Argumente, die für Verweise auf Elemente des Arrays verwendet.  
  
 *newElement*  
 Der neue Elementwert an der angegebenen Position gespeichert werden.  
  
### <a name="remarks"></a>Hinweise  
 `SetAt` das Array, wachsen verursacht nicht. Verwendung [SetAtGrow](#setatgrow) , wenn Sie das Array, das automatisch vergrößert werden soll.  
  
 Sie müssen sicherstellen, dass Ihr Indexwert eine gültige Position im Array darstellt. Wenn es außerhalb des gültigen Bereichs ist, bestätigt Sie dann die Debugversion der Bibliothek.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetAt](#getat).  
  
##  <a name="setatgrow"></a>  CArray::SetAtGrow  
 Legt das Arrayelement am angegebenen Index fest.  
  
```  
void SetAtGrow(INT_PTR nIndex, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Eine ganze Zahl-Index, der größer als oder gleich 0 ist.  
  
 *ARG_TYPE*  
 Der Vorlagenparameter, den Typ der Elemente im Array angibt.  
  
 *newElement*  
 Das Element, das in diesem Array hinzugefügt werden. Es ist ein NULL-Wert zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Das Array automatisch vergrößert, bei Bedarf (d. h. die obere Grenze wird angepasst, um das neue Element).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections#33](../../mfc/codesnippet/cpp/carray-class_13.cpp)]  
  
##  <a name="setsize"></a>  SetSize  
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
 Wenn die neue Größe kleiner als die alte Größe ist, klicken Sie dann das Array abgeschnitten, und alle nicht verwendeten Arbeitsspeicher wird freigegeben.  
  
 Verwenden Sie diese Funktion, die Größe eines Arrays festlegen, bevor Sie beginnen mit dem Array. Wenn Sie `SetSize` nicht verwenden, kann das Hinzufügen von Elementen zu Ihrem Array dazu führen, dass es häufig neu zugeordnet und kopiert wird. Häufige Neuzuordnungen und Kopiervorgänge sind ineffizient und können zu einer Fragmentierung des Arbeitsspeichers führen.  
  
 Die *nGrowBy* Parameter wirkt sich auf interne speicherbelegung während das Array vergrößert. Die Verwendung nie wirkt sich auf die Größe des Arrays von gemeldeten [GetSize](#getsize) und [GetUpperBound](#getupperbound). Wenn der Standardwert verwendet wird, weist MFC Speicher auf eine Weise vermeiden die Fragmentierung des Arbeitsspeichers und optimiert die Effizienz in den meisten Fällen berechnet.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetData](#getdata).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel erfassen](../../visual-cpp-samples.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CObArray-Klasse](../../mfc/reference/cobarray-class.md)   
 [Hilfsfunktionen für die Auflistungsklasse](../../mfc/reference/collection-class-helpers.md)
