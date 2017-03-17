---
title: CArray-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- C++
helpviewer_keywords:
- CArray class
- arrays [C++], classes
- templates, collection classes
- collection classes, template-based
ms.assetid: fead8b00-4cfd-4625-ad0e-251df62ba92f
caps.latest.revision: 33
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
ms.openlocfilehash: bac8e08540ffead565d1097c6ef1efcae5e606c2
ms.lasthandoff: 02/24/2017

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
 Ein Vorlagenparameter, der den Typ der im Array gespeicherten Objekte angibt. `TYPE`ist ein Parameter, der von zurückgegebene `CArray`.  
  
 `ARG` *_* `TYPE`  
 Ein Vorlagenparameter, der den Typ des Arguments, der verwendet wird angibt, um den Zugriff auf Objekte im Array gespeichert. Häufig einen Verweis auf `TYPE`. `ARG_TYPE`ist ein Parameter, der an `CArray`.  
  
## <a name="members"></a>Mitglieder  
  
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
 Arrayindizes beginnen immer an Position 0. Sie können entscheiden, ob beheben die obere Grenze oder aktivieren das Array, erweitern beim Hinzufügen von Elementen nach der aktuellen gebunden werden soll. Arbeitsspeicher ist die Obergrenze zusammenhängend zugewiesen, auch wenn einige Elemente null sind.  
  
> [!NOTE]
>  Die meisten Methoden, die die Größe einer `CArray` Objekt oder Elemente zu verwenden, fügen [Memcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md) Elemente verschoben. Dies ist ein Problem, da `memcpy_s` ist nicht kompatibel mit der alle Objekte, die den Konstruktor aufgerufen werden müssen. Wenn die Elemente in der `CArray` sind nicht kompatibel mit `memcpy_s`, müssen Sie ein neues erstellen `CArray` von geeigneter Größe. Sie müssen dann verwenden [CArray::Copy](#copy) und [CArray::SetAt](#setat) an das neue Array zu füllen, da die Verwendung dieser Methoden Zuweisungsoperator anstelle von `memcpy_s`.  
  
 Wie bei einer C#-Array, die Zugriffszeit für eine `CArray` indizierte Element ist konstant und wird unabhängig von der Größe des Arrays.  
  
> [!TIP]
>  Verwenden Sie vor dem Verwenden eines Arrays, [SetSize](#setsize) seiner Größe und weisen dafür Arbeitsspeicher. Wenn Sie `SetSize` nicht verwenden, kann das Hinzufügen von Elementen zu Ihrem Array dazu führen, dass es häufig neu zugeordnet und kopiert wird. Häufige Neuzuordnungen und Kopiervorgänge sind ineffizient und können zu einer Fragmentierung des Arbeitsspeichers führen.  
  
 Wenn Sie ein Abbild der einzelnen Elemente in einem Array benötigen, müssen Sie festlegen, dass die Tiefe der [CDumpContext](../../mfc/reference/cdumpcontext-class.md) Objekt auf 1 oder größer.  
  
 Bestimmte Memberfunktionen dieser Klasse rufen globale Hilfsfunktionen, die angepasst werden müssen, für die meisten Verwendungen von der `CArray` Klasse. Finden Sie unter [Auflistungsklasse](../../mfc/reference/collection-class-helpers.md) im Abschnitt MFC-Makros und Globals.  
  
 Array-Klasse-Ableitung ist wie Liste Ableitung.  
  
 Weitere Informationen zur Verwendung von `CArray`, finden Sie im Artikel [Sammlungen](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CArray`  
  
## <a name="requirements"></a>Anforderungen  
 `Header:`afxtempl.h  
  
##  <a name="add"></a>CArray::Add  
 Fügt ein neues Element am Ende ein Array, das Array um 1 vergrößert.  
  
```  
INT_PTR Add(ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parameter  
 `ARG_TYPE`  
 Der Vorlagenparameter, die den Typ der Argumente Verweise auf Elemente in diesem Array.  
  
 `newElement`  
 Das Element, das in diesem Array hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des hinzugefügten Elements.  
  
### <a name="remarks"></a>Hinweise  
 Wenn [SetSize](#setsize) wurde verwendet, mit einer `nGrowBy` Wert größer als 1 ist, wird zusätzlicher Speicher zugeordnet werden. Allerdings wird die Obergrenze von nur 1 erhöht.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#22;](../../mfc/codesnippet/cpp/carray-class_1.cpp)]  
  
##  <a name="append"></a>CArray::Append  
 Rufen Sie diese Memberfunktion, um den Inhalt eines Arrays an das Ende eines anderen hinzufügen.  
  
```  
INT_PTR Append(const CArray& src);
```  
  
### <a name="parameters"></a>Parameter  
 *src*  
 Die Quelle der Elemente, die einem Array hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des ersten Elements angefügt.  
  
### <a name="remarks"></a>Hinweise  
 Die Arrays müssen vom gleichen Typ sein.  
  
 Falls erforderlich, **Append** können zusätzlichen Speicher, um die Elemente des Arrays angefügt aufnehmen zuweisen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&23;](../../mfc/codesnippet/cpp/carray-class_2.cpp)]  
  
##  <a name="carray"></a>CArray::CArray  
 Erstellt ein leeres Array.  
  
```  
CArray();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Array nimmt ein Element zu einem Zeitpunkt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#24;](../../mfc/codesnippet/cpp/carray-class_3.cpp)]  
  
##  <a name="copy"></a>CArray::Copy  
 Verwenden Sie diese Memberfunktion, die Elemente eines Arrays in ein anderes kopiert.  
  
```  
void Copy(const CArray& src);
```  
  
### <a name="parameters"></a>Parameter  
 *src*  
 Die Quelle der Elemente, die in ein Array kopiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion, um die Elemente eines Arrays mit den Elementen eines anderen Arrays zu überschreiben.  
  
 **Kopie** keinen Speicherplatz frei, jedoch bei Bedarf **Kopie** kann Speicher zusätzliche Aufnahme der Elemente in das Array kopiert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#25;](../../mfc/codesnippet/cpp/carray-class_4.cpp)]  
  
##  <a name="elementat"></a>CArray::ElementAt  
 Gibt einen temporären Verweis auf das angegebene Element innerhalb des Arrays zurück.  
  
```  
TYPE& ElementAt(INT_PTR nIndex);  
const TYPE& ElementAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner oder gleich der von zurückgegebene Wert [GetUpperBound](#getupperbound).  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf ein Arrayelement.  
  
### <a name="remarks"></a>Hinweise  
 Sie wird verwendet, um den linken Zuweisungsoperator für Arrays zu implementieren.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetSize](#getsize).  
  
##  <a name="freeextra"></a>CArray::FreeExtra  
 Zusätzlichen Speicher, der belegt wurde, während das Array angebaut wurde frei.  
  
```  
void FreeExtra();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion hat keine Auswirkung auf die Größe oder die obere Grenze des Arrays.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetData](#getdata).  
  
##  <a name="getat"></a>CArray::GetAt  
 Gibt das Arrayelement am angegebenen Index zurück.  
  
```  
TYPE& GetAt(INT_PTR nIndex);  
const TYPE& GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Der Vorlagenparameter, die den Typ der Arrayelemente.  
  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner oder gleich der von zurückgegebene Wert [GetUpperBound](#getupperbound).  
  
### <a name="return-value"></a>Rückgabewert  
 Das Arrayelement derzeit an diesem Index.  
  
### <a name="remarks"></a>Hinweise  
 Übergeben einen negativen Wert oder einen Wert größer als der von zurückgegebene Wert `GetUpperBound` führt dazu, dass eine fehlgeschlagene Assertion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#26;](../../mfc/codesnippet/cpp/carray-class_5.cpp)]  
  
##  <a name="getcount"></a>CArray::GetCount  
 Gibt die Anzahl der Arrayelemente.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Array.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Anzahl der Elemente im Array ab. Da Indizes nullbasiert sind, ist die Größe 1 größer als der größte Index. Das Aufrufen dieser Methode generiert das gleiche Ergebnis wie die [CArray::GetSize](#getsize) Methode.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#27;](../../mfc/codesnippet/cpp/carray-class_6.cpp)]  
  
##  <a name="getdata"></a>CArray::GetData  
 Verwenden Sie diese Memberfunktion auf die Elemente in einem Array direkt zugreifen.  
  
```  
const TYPE* GetData() const; 
TYPE* GetData();
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Der Vorlagenparameter, die den Typ der Arrayelemente.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Arrayelement.  
  
### <a name="remarks"></a>Hinweise  
 Wenn keine Elemente verfügbar sind, `GetData` gibt null zurück.  
  
 Direkter Zugriff auf die Elemente eines Arrays können Sie schneller arbeiten helfen, seien Sie vorsichtig beim Aufrufen von `GetData`; alle Fehler, die Sie direkt vornehmen beeinflussen die Elemente des Arrays.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#28;](../../mfc/codesnippet/cpp/carray-class_7.cpp)]  
  
##  <a name="getsize"></a>CArray::GetSize  
 Gibt die Größe des Arrays zurück.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Da Indizes nullbasiert sind, ist die Größe 1 größer als der größte Index. Das Aufrufen dieser Methode generiert das gleiche Ergebnis wie die [CArray::GetCount](#getcount) Methode.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#29;](../../mfc/codesnippet/cpp/carray-class_8.cpp)]  
  
##  <a name="getupperbound"></a>CArray::GetUpperBound  
 Gibt die aktuellen Obergrenze für dieses Array zurück.  
  
```  
INT_PTR GetUpperBound() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Da Arrayindizes nullbasiert sind, gibt diese Funktion einen Wert 1 kleiner als `GetSize`.  
  
 Die Bedingung **GetUpperBound ()** = -1 gibt an, dass das Array keine Elemente enthält.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CArray::GetAt](#getat).  
  
##  <a name="insertat"></a>CArray::InsertAt  
 Die erste Version der `InsertAt` Fügt ein Element (oder mehrere Kopien eines Elements) an einem angegebenen Index in einem Array.  
  
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
 Eine ganzzahlige Index, der größer als der zurückgegebene Wert möglicherweise `GetUpperBound`.  
  
 `ARG_TYPE`  
 Der Vorlagenparameter, die den Typ der Elemente im Array.  
  
 `newElement`  
 Das Element in diesem Array platziert werden.  
  
 `nCount`  
 Wie oft dieses Element liegen eingefügt (Standardwert: 1).  
  
 `nStartIndex`  
 Eine ganzzahlige Index, der größer als der zurückgegebene Wert möglicherweise [GetUpperBound](#getupperbound).  
  
 `pNewArray`  
 Ein anderes Array mit Elementen in diesem Array hinzugefügt werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Bei diesem Vorgang werden Sie verschoben (durch erhöhen den Index) Verschiebt das vorhandene Element am Index, und es werden alle Elemente davor.  
  
 Die zweite Version fügt alle Elemente aus einem anderen `CArray` -Auflistung, beginnend ab dem `nStartIndex` Position.  
  
 Die `SetAt` -Funktion hingegen ersetzt eine angegebene Arrayelement und alle Elemente werden nicht verschoben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#30;](../../mfc/codesnippet/cpp/carray-class_9.cpp)]  
  
##  <a name="isempty"></a>CArray::IsEmpty  
 Bestimmt, ob das Array leer ist.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Array keine Elemente enthält; andernfalls 0.  
  
##  <a name="operator_at"></a>CArray::operator\[\]  
 Diese Indexoperatoren sind praktisch Ersatz für die [SetAt](#setat) und [GetAt](#getat) Funktionen.  
  
```  
TYPE& operator[](int_ptr nindex);  
const TYPE& operator[](int_ptr nindex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Der Vorlagenparameter, die den Typ der Elemente im Array.  
  
 `nIndex`  
 Der Index des Elements zugegriffen werden.  
  
### <a name="remarks"></a>Hinweise  
 Der first-Operator für Arrays, bei denen aufgerufen **const**, darf für (r) nach rechts oder links (l-Wert) einer zuweisungsanweisung verwendet werden. Die zweite Bezeichnung für **const** Arrays dürfen nur auf der rechten Seite verwendet werden.  
  
 Die Debugversion der Bibliothek bestätigt, wenn der Index (entweder auf der linken oder rechten Seite einer zuweisungsanweisung) außerhalb des gültigen Bereichs ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#34;](../../mfc/codesnippet/cpp/carray-class_10.cpp)]  
  
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
 Das alte Array der Elemente.  
  
 `nCount`  
 Anzahl der Elemente im alten Array.  
  
### <a name="remarks"></a>Hinweise  
 `pNewData`ist immer groß genug für alle die `pData` Elemente.  
  
 Die [CArray](../../mfc/reference/carray-class.md) Implementierung verwendet diese Methode, um die alten Daten in einen neuen Puffer zu kopieren, wenn das Array vergrößert oder verkleinert werden soll (Wenn [SetSize](#setsize) oder [FreeExtra](#freeextra) bezeichnet werden). Die standardmäßige Implementierung werden nur die Daten kopiert.  
  
 Für Arrays, das ein Element enthält einen Zeiger auf einen Member oder eine andere Struktur enthält einen Zeiger auf eine der Elemente des Arrays werden die Zeiger in einfachen Kopieren nicht aktualisiert. In diesem Fall können Sie Zeiger korrigieren, indem Sie implementieren eine Spezialisierung der `RelocateElements` mit den entsprechenden Typen. Sie können auch für das Kopieren von Daten zuständig.  
  
##  <a name="removeall"></a>CArray::RemoveAll  
 Entfernt alle Elemente aus diesem Array.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie bereits das Array leer ist, funktioniert die Funktion weiterhin.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#31;](../../mfc/codesnippet/cpp/carray-class_11.cpp)]  
  
##  <a name="removeat"></a>CArray::RemoveAt  
 Entfernt eine oder mehrere Elemente, beginnend am angegebenen Index in ein Array.  
  
```  
void RemoveAt(
    INT_PTR nIndex,  
    INT_PTR nCount = 1);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner oder gleich der von zurückgegebene Wert [GetUpperBound](#getupperbound).  
  
 `nCount`  
 Die Anzahl der zu entfernenden Elemente.  
  
### <a name="remarks"></a>Hinweise  
 In der werden verschoben Sie alle Elemente über die entfernten Elemente. Es verringert die obere Grenze des Arrays, aber keinen Speicherplatz frei.  
  
 Wenn Sie versuchen, mehr Elemente als in das Array über die Entfernung Punkt enthaltenen entfernen, überprüft dann die Debugversion der Bibliothek.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#32;](../../mfc/codesnippet/cpp/carray-class_12.cpp)]  
  
##  <a name="setat"></a>CArray::SetAt  
 Legt das Arrayelement am angegebenen Index fest.  
  
```  
void SetAt(INT_PTR nIndex, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner oder gleich der von zurückgegebene Wert [GetUpperBound](#getupperbound).  
  
 `ARG_TYPE`  
 Der Vorlagenparameter, die den Typ der Argumente, die zum Verweisen auf Arrayelemente verwendet.  
  
 `newElement`  
 Der neue Elementwert an der angegebenen Position gespeichert werden.  
  
### <a name="remarks"></a>Hinweise  
 `SetAt`das Array vergrößert wird nicht verursacht werden. Verwendung [SetAtGrow](#setatgrow) , wenn das Array, das automatisch vergrößert werden soll.  
  
 Sie müssen sicherstellen, dass der Indexwert gültige Position im Array darstellt. Ist außerhalb des gültigen Bereichs, überprüft dann die Debugversion der Bibliothek.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetAt](#getat).  
  
##  <a name="setatgrow"></a>CArray::SetAtGrow  
 Legt das Arrayelement am angegebenen Index fest.  
  
```  
void SetAtGrow(INT_PTR nIndex, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 ist.  
  
 `ARG_TYPE`  
 Der Vorlagenparameter, die den Typ der Elemente im Array.  
  
 `newElement`  
 Das Element, das in diesem Array hinzugefügt werden. Ein **NULL** Wert zulässig ist.  
  
### <a name="remarks"></a>Hinweise  
 Das Array vergrößert automatisch bei Bedarf (d. h. die obere Grenze wird angepasst, um das neue Element aufzunehmen).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&33;](../../mfc/codesnippet/cpp/carray-class_13.cpp)]  
  
##  <a name="setsize"></a>SetSize  
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
 Wenn die neue Größe kleiner als die alte Größe ist, wird das Array abgeschnitten, und alle nicht verwendeten Speicher freigegeben wird.  
  
 Verwenden Sie diese Funktion, um die Größe des Arrays festgelegt, bevor Sie beginnen mit dem Array. Wenn Sie `SetSize` nicht verwenden, kann das Hinzufügen von Elementen zu Ihrem Array dazu führen, dass es häufig neu zugeordnet und kopiert wird. Häufige Neuzuordnungen und Kopiervorgänge sind ineffizient und können zu einer Fragmentierung des Arbeitsspeichers führen.  
  
 Die `nGrowBy` Parameter wirkt sich auf internen Speicher reservieren, während das Array wächst. Seine Verwendung nie wirkt sich auf die Größe des Arrays von gemeldeten [GetSize](#getsize) und [GetUpperBound](#getupperbound). Wenn der Standardwert verwendet wird, reserviert MFC so vermeiden Sie Speicherfragmentierung und erhöht die Effizienz in den meisten Fällen berechnet.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetData](#getdata).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel COLLECT](../../visual-cpp-samples.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CObArray-Klasse](../../mfc/reference/cobarray-class.md)   
 [Die Auflistungsklasse](../../mfc/reference/collection-class-helpers.md)

