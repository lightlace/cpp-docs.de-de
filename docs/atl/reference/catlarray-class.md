---
title: CAtlArray-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAtlArray
- ATLCOLL/ATL::CAtlArray
- ATLCOLL/ATL::Add
- ATLCOLL/ATL::Append
- ATLCOLL/ATL::AssertValid
- ATLCOLL/ATL::Copy
- ATLCOLL/ATL::FreeExtra
- ATLCOLL/ATL::GetAt
- ATLCOLL/ATL::GetCount
- ATLCOLL/ATL::GetData
- ATLCOLL/ATL::InsertArrayAt
- ATLCOLL/ATL::InsertAt
- ATLCOLL/ATL::IsEmpty
- ATLCOLL/ATL::RemoveAll
- ATLCOLL/ATL::RemoveAt
- ATLCOLL/ATL::SetAt
- ATLCOLL/ATL::SetAtGrow
- ATLCOLL/ATL::SetCount
- ATLCOLL/ATL::INARGTYPE
- ATLCOLL/ATL::OUTARGTYPE
helpviewer_keywords:
- CAtlArray class
ms.assetid: 0b503aa8-2357-40af-a326-6654bf1da098
ms.openlocfilehash: 6a0b83f722d1b616e9c10713646d337f9cb090a4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260843"
---
# <a name="catlarray-class"></a>CAtlArray-Klasse

Diese Klasse implementiert eine Array-Objekt.

## <a name="syntax"></a>Syntax

```
template<typename E, class ETraits = CElementTraits<E>>
class CAtlArray
```

#### <a name="parameters"></a>Parameter

*E*<br/>
Der Typ der im Array gespeicherten Daten.

*ETraits*<br/>
Der Code verwendet, um die Elemente kopiert oder verschoben wird.

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[Add](#add)|Rufen Sie diese Methode, um das Array-Objekt ein Element hinzufügen.|
|[Anfügen](#append)|Rufen Sie diese Methode, um den Inhalt eines Arrays am Ende eines anderen hinzufügen.|
|[AssertValid](#assertvalid)|Rufen Sie diese Methode, um sicherzustellen, dass das Arrayobjekt gültig ist.|
|[CAtlArray](#catlarray)|Der Konstruktor.|
|[~CAtlArray](#dtor)|Der Destruktor.|
|[Kopieren](#copy)|Rufen Sie diese Methode, um die Elemente eines Arrays in ein anderes kopieren.|
|[FreeExtra](#freeextra)|Rufen Sie diese Methode, um leere Elemente aus dem Array entfernt.|
|[GetAt](#getat)|Rufen Sie diese Methode, um ein einzelnes Element aus dem Arrayobjekt abzurufen.|
|[GetCount](#getcount)|Rufen Sie diese Methode, um die Anzahl der Elemente im Array gespeicherten zurück.|
|[GetData](#getdata)|Rufen Sie diese Methode, um einen Zeiger auf das erste Element im Array zurückzugeben.|
|[InsertArrayAt](#insertarrayat)|Rufen Sie diese Methode, um ein Array in eine andere einzufügen.|
|[InsertAt](#insertat)|Rufen Sie diese Methode zum Einfügen eines neuen Elements (oder mehrere Kopien eines Elements), in das Array-Objekt.|
|[IsEmpty](#isempty)|Rufen Sie diese Methode zu testen, ob das Array leer ist.|
|[RemoveAll](#removeall)|Rufen Sie diese Methode, um alle Elemente aus dem Arrayobjekt zu entfernen.|
|[RemoveAt](#removeat)|Rufen Sie diese Methode, um ein oder mehrere Elemente aus dem Array entfernt.|
|[SetAt](#setat)|Rufen Sie diese Methode, um den Wert eines Elements in das Array-Objekt festlegen.|
|[SetAtGrow](#setatgrow)|Rufen Sie diese Methode, um den Wert eines Elements in das Array-Objekt, und erweitern das Array als erforderlich festgelegt.|
|[SetCount](#setcount)|Rufen Sie diese Methode, um die Größe des Array-Objekts festgelegt.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator &#91;&#93;](#operator_at)|Rufen Sie diesen Operator, um einen Verweis auf ein Element im Array zurückzugeben.|

### <a name="typedefs"></a>Typedefs

|||
|-|-|
|[INARGTYPE](#inargtype)|Der Datentyp, verwenden Sie zum Hinzufügen von Elementen in das Array.|
|[OUTARGTYPE](#outargtype)|Der Datentyp für das Abrufen von Elementen aus dem Array.|

## <a name="remarks"></a>Hinweise

`CAtlArray` Stellt Methoden zum Erstellen und verwalten ein Array von Elementen eines benutzerdefinierten Typs. Obwohl der standard-C-Arrays, ähnlich wie die `CAtlArray` Objekt dynamisch verkleinern und nach Bedarf wachsen kann. Der Arrayindex beginnt immer an Position 0, und die obere Grenze kann korrigiert oder erweitert werden, wenn neue Elemente hinzugefügt werden können.

Für Arrays mit einer kleinen Anzahl von Elementen, die ATL-Klasse [CSimpleArray](../../atl/reference/csimplearray-class.md) kann verwendet werden.

`CAtlArray` ist eng verwandt mit MFC `CArray` Klasse und funktioniert in einem MFC-Projekt, allerdings ohne Unterstützung der Serialisierung.

Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlcoll.h

##  <a name="add"></a>  CAtlArray::Add

Rufen Sie diese Methode, um das Array-Objekt ein Element hinzufügen.

```
size_t Add(INARGTYPE element);
size_t Add();
```

### <a name="parameters"></a>Parameter

*element*<br/>
Das Element, das dem Array hinzugefügt werden.

### <a name="return-value"></a>Rückgabewert

Gibt den Index des hinzugefügten Elements.

### <a name="remarks"></a>Hinweise

Das neue Element wird am Ende des Arrays hinzugefügt werden. Wenn kein Element angegeben wird, ein leeres Element hinzugefügt wird; das Array wird, also Größe erhöht, als ob eine echte-Element hinzugefügt wurde. Wenn der Vorgang fehlschlägt, ["atlthrow"](debugging-and-error-reporting-global-functions.md#atlthrow) mit dem Argument E_OUTOFMEMORY aufgerufen wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#1](../../atl/codesnippet/cpp/catlarray-class_1.cpp)]

##  <a name="append"></a>  CAtlArray::Append

Rufen Sie diese Methode, um den Inhalt eines Arrays am Ende eines anderen hinzufügen.

```
size_t Append(const CAtlArray<E, ETraits>& aSrc);
```

### <a name="parameters"></a>Parameter

*aSrc*<br/>
Das Array angefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt den Index des ersten Elements angefügt.

### <a name="remarks"></a>Hinweise

Das Ende des vorhandenen Arrays werden die Elemente im angegebenen Array hinzugefügt. Bei Bedarf wird Arbeitsspeicher zugeordnet werden, um die neuen Elemente aufnehmen zu können.

Die Arrays müssen vom gleichen Typ sein, und es ist nicht möglich, ein Array mit sich selbst angefügt werden soll.

In Debugbuilds einer ATLASSERT wird ausgelöst, wenn die `CAtlArray` Argument ist kein gültiges Array oder, wenn *aSrc* bezieht sich auf das gleiche Objekt. In Releasebuilds möglicherweise ungültige Argumente zu unvorhersehbarem Verhalten führen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#2](../../atl/codesnippet/cpp/catlarray-class_2.cpp)]

##  <a name="assertvalid"></a>  CAtlArray::AssertValid

Rufen Sie diese Methode, um sicherzustellen, dass das Arrayobjekt gültig ist.

```
void AssertValid() const;
```

### <a name="remarks"></a>Hinweise

Wenn das Arrayobjekt nicht gültig ist, wird die ATLASSERT eine Assertion ausgelöst. Diese Methode ist nur verfügbar, wenn _DEBUG definiert ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#3](../../atl/codesnippet/cpp/catlarray-class_3.cpp)]

##  <a name="catlarray"></a>  CAtlArray::CAtlArray

Der Konstruktor.

```
CAtlArray() throw();
```

### <a name="remarks"></a>Hinweise

Initialisiert das Arrayobjekt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#4](../../atl/codesnippet/cpp/catlarray-class_4.cpp)]

##  <a name="dtor"></a>  CAtlArray:: ~ CAtlArray

Der Destruktor.

```
~CAtlArray() throw();
```

### <a name="remarks"></a>Hinweise

Alle vom Array-Objekt verwendeten Ressourcen freigegeben.

##  <a name="copy"></a>  CAtlArray::Copy

Rufen Sie diese Methode, um die Elemente eines Arrays in ein anderes kopieren.

```
void Copy(const CAtlArray<E, ETraits>& aSrc);
```

### <a name="parameters"></a>Parameter

*aSrc*<br/>
Die Quelle der Elemente, die in einem Array zu kopieren.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode, um die Elemente eines Arrays mit den Elementen eines anderen Arrays zu überschreiben. Bei Bedarf wird Arbeitsspeicher zugeordnet werden, um die neuen Elemente aufnehmen zu können. Es ist nicht möglich, Elemente eines Arrays mit sich selbst zu kopieren.

Wenn Sie den vorhandenen Inhalt des Arrays sind beibehalten werden sollen, verwenden [CAtlArray::Append](#append) stattdessen.

In Debugbuilds einer ATLASSERT wird ausgelöst, wenn die vorhandene `CAtlArray` -Objekt ist ungültig, oder wenn *aSrc* bezieht sich auf das gleiche Objekt. In Releasebuilds möglicherweise ungültige Argumente zu unvorhersehbarem Verhalten führen.

> [!NOTE]
> `CAtlArray::Copy` unterstützt keine Arrays aus Elementen, die mit erstellt besteht die [CAutoPtr](../../atl/reference/cautoptr-class.md) Klasse.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#5](../../atl/codesnippet/cpp/catlarray-class_5.cpp)]

##  <a name="freeextra"></a>  CAtlArray::FreeExtra

Rufen Sie diese Methode, um leere Elemente aus dem Array entfernt.

```
void FreeExtra() throw();
```

### <a name="remarks"></a>Hinweise

Leere Elemente werden entfernt, aber die Größe und die obere Grenze des Arrays unverändert bleiben.

Debug-Builds wird ein ATLASSERT ausgelöst, wenn CAtlArray-Objekt ungültig ist oder wenn das Array die maximale Größe überschreiten würde.

##  <a name="getat"></a>  CAtlArray::GetAt

Aufruf, dass diese Methode, um ein einzelnes Element aus dem Arrayobjekt abgerufen.

```
const E& GetAt(size_t iElement) const throw();
E& GetAt(size_t iElement) throw();
```

### <a name="parameters"></a>Parameter

*iElement*<br/>
Der Indexwert des Arrayelements zurückgegeben.

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf das erforderliche Arrayelement.

### <a name="remarks"></a>Hinweise

In Debugbuilds einer ATLASSERT wird ausgelöst, wenn *"IElement"* überschreitet die Anzahl der Elemente im Array. In Releasebuilds kann ein ungültiges Argument zu einem unvorhersehbaren Verhalten führen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#6](../../atl/codesnippet/cpp/catlarray-class_6.cpp)]

##  <a name="getcount"></a>  CAtlArray::GetCount

Rufen Sie diese Methode, um die Anzahl der Elemente im Array gespeicherten zurück.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Elemente im Array gespeichert.

### <a name="remarks"></a>Hinweise

Da das erste Element im Array an Position 0 ist, wird der Wert von zurückgegeben `GetCount` ist immer 1 größer als der größte Index.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlArray::GetAt](#getat).

##  <a name="getdata"></a>  CAtlArray::GetData

Rufen Sie diese Methode, um einen Zeiger auf das erste Element im Array zurückzugeben.

```
E* GetData() throw();
const E* GetData() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die Speicheradresse, speichern das erste Element im Array zurück. Wenn keine Elemente verfügbar sind, wird NULL zurückgegeben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#7](../../atl/codesnippet/cpp/catlarray-class_7.cpp)]

##  <a name="inargtype"></a>  CAtlArray::INARGTYPE

Der Datentyp, verwenden Sie zum Hinzufügen von Elementen in das Array.

```
typedef ETraits::INARGTYPE INARGTYPE;
```

##  <a name="insertarrayat"></a>  CAtlArray::InsertArrayAt

Rufen Sie diese Methode, um ein Array in eine andere einzufügen.

```
void InsertArrayAt(size_t iStart, const CAtlArray<E, ETraits>* paNew);
```

### <a name="parameters"></a>Parameter

*iStart*<br/>
Der Index, an dem das Array ist, eingefügt werden soll.

*paNew*<br/>
Das Array eingefügt werden soll.

### <a name="remarks"></a>Hinweise

Elemente aus dem Array *PaNew* werden in das Array-Objekt, beginnend bei Element kopiert *iStart*. Die Elemente des vorhandenen Arrays werden verschoben, um zu vermeiden, überschrieben werden.

In Debugbuilds einer ATLASSERT wird ausgelöst, wenn die `CAtlArray` -Objekt ist ungültig, oder wenn die *PaNew* -Zeiger ist, NULL oder ungültig.

> [!NOTE]
> `CAtlArray::InsertArrayAt` unterstützt keine Arrays aus Elementen, die mit erstellt besteht die [CAutoPtr](../../atl/reference/cautoptr-class.md) Klasse.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#8](../../atl/codesnippet/cpp/catlarray-class_8.cpp)]

##  <a name="insertat"></a>  CAtlArray::InsertAt

Rufen Sie diese Methode zum Einfügen eines neuen Elements (oder mehrere Kopien eines Elements), in das Array-Objekt.

```
void InsertAt(size_t iElement, INARGTYPE element, size_t nCount = 1);
```

### <a name="parameters"></a>Parameter

*iElement*<br/>
Der Index, in dem das Element oder Elemente sind, eingefügt werden soll.

*element*<br/>
Der Wert des Elements oder Elemente eingefügt werden soll.

*nCount*<br/>
Die Anzahl der hinzuzufügenden Elemente.

### <a name="remarks"></a>Hinweise

Fügt einen oder mehrere Elemente in das Array, beginnend am Index *"IElement"*. Vorhandene Elemente werden verschoben, um zu vermeiden, überschrieben werden.

In Debugbuilds einer ATLASSERT wird ausgelöst, wenn die `CAtlArray` Objekt ist ungültig, die Anzahl von Elementen, die hinzugefügt werden, ist 0 (null) oder die kombinierte Anzahl von Elementen ist zu groß für das Array enthält. In Verkaufsversionen kann die Übergabe ungültiger Parameter zu unvorhersehbaren Ergebnissen führen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#9](../../atl/codesnippet/cpp/catlarray-class_9.cpp)]

##  <a name="isempty"></a>  CAtlArray::IsEmpty

Rufen Sie diese Methode zu testen, ob das Array leer ist.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das Array leer ist, andernfalls false.

### <a name="remarks"></a>Hinweise

Das Array wird als leer sein, wenn es keine Elemente enthält. Auch wenn das Array leere Elemente enthält, ist es daher nicht leer.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#10](../../atl/codesnippet/cpp/catlarray-class_10.cpp)]

##  <a name="operator_at"></a>  CAtlArray::operator]

Rufen Sie diesen Operator, um einen Verweis auf ein Element im Array zurückzugeben.

```
E& operator[](size_t ielement) throw();
const E& operator[](size_t ielement) const throw();
```

### <a name="parameters"></a>Parameter

*iElement*<br/>
Der Indexwert des Arrayelements zurückgegeben.

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf das erforderliche Arrayelement.

### <a name="remarks"></a>Hinweise

Führt eine ähnliche Funktion [CAtlArray::GetAt](#getat). Im Gegensatz zu der MFC-Klasse [CArray](../../mfc/reference/carray-class.md), dieser Operator kann nicht verwendet werden, als Ersatz für [CAtlArray::SetAt](#setat).

In Debugbuilds einer ATLASSERT wird ausgelöst, wenn *"IElement"* überschreitet die Gesamtzahl der Elemente im Array. In Verkaufsversionen kann ein ungültiger Parameter zu unvorhersehbaren Ergebnissen führen.

##  <a name="outargtype"></a>  CAtlArray::OUTARGTYPE

Der Datentyp für das Abrufen von Elementen aus dem Array.

```
typedef ETraits::OUTARGTYPE OUTARGTYPE;
```

##  <a name="removeall"></a>  CAtlArray::RemoveAll

Rufen Sie diese Methode, um alle Elemente aus dem Arrayobjekt zu entfernen.

```
void RemoveAll() throw();
```

### <a name="remarks"></a>Hinweise

Entfernt alle Elemente aus dem Arrayobjekt.

Diese Methode ruft [CAtlArray::SetCount](#setcount) zum Ändern der Größe des Arrays und gibt anschließend alle zugeordneten Arbeitsspeicher frei.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlArray::IsEmpty](#isempty).

##  <a name="removeat"></a>  CAtlArray::RemoveAt

Rufen Sie diese Methode, um ein oder mehrere Elemente aus dem Array entfernt.

```
void RemoveAt(size_t iElement, size_t nCount = 1);
```

### <a name="parameters"></a>Parameter

*iElement*<br/>
Der Index des ersten Elements, das entfernt werden soll.

*nCount*<br/>
Die Anzahl der zu entfernenden Elemente.

### <a name="remarks"></a>Hinweise

Entfernt eine oder mehrere Elemente aus dem Array. Alle übrigen Elemente werden nach unten verschoben. Die obere Grenze wird verringert, aber Speicher wird nicht freigegeben, bis ein Aufruf von [CAtlArray::FreeExtra](#freeextra) erfolgt.

In Debugversionen einer ATLASSERT wird ausgelöst, wenn die `CAtlArray` -Objekt ist ungültig, oder wenn die kombinierte Summe *"IElement"* und *nCount* überschreitet die Gesamtzahl der Elemente im Array. Ungültige Parameter können zu unvorhersehbaren Ergebnissen führen, in Retail-Builds.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#11](../../atl/codesnippet/cpp/catlarray-class_11.cpp)]

##  <a name="setat"></a>  CAtlArray::SetAt

Rufen Sie diese Methode, um den Wert eines Elements in das Array-Objekt festlegen.

```
void SetAt(size_t iElement, INARGTYPE element);
```

### <a name="parameters"></a>Parameter

*iElement*<br/>
Der Index verweist auf das Arrayelement festgelegt.

*element*<br/>
Der neue Wert des angegebenen Elements.

### <a name="remarks"></a>Hinweise

In Debugbuilds einer ATLASSERT wird ausgelöst, wenn *"IElement"* überschreitet die Anzahl der Elemente im Array. Ein ungültiger Parameter kann in Verkaufsversionen zu unvorhersehbaren Ergebnissen führen.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlArray::GetAt](#getat).

##  <a name="setcount"></a>  CAtlArray::SetCount

Rufen Sie diese Methode, um die Größe des Array-Objekts festgelegt.

```
bool SetCount(size_t nNewSize, int nGrowBy = - 1);
```

### <a name="parameters"></a>Parameter

*nNewSize*<br/>
Die erforderliche Größe des Arrays.

*nGrowBy*<br/>
Ein Wert, der verwendet wird, um zu bestimmen, wie groß ist, um den Puffer zu machen. Der Wert-1 wird einen intern berechneten Wert verwendet werden.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn das Array wurde erfolgreich geändert, andernfalls false ist.

### <a name="remarks"></a>Hinweise

Das Array kann erhöht oder verringert die Größe sein. Wenn erhöht, werden dem Array zusätzliche leere Elemente hinzugefügt. Verringert, die Elemente mit den größten Indizes gelöscht werden, und der Speicher freigegeben.

Verwenden Sie diese Methode, um die Größe des Arrays festgelegt wird, bevor Sie ihn verwenden. Wenn `SetCount` nicht verwendet wird, den Prozess des Hinzufügens von Elementen, und die nachfolgenden speicherbelegung ausgeführt, wird die Leistung beeinträchtigt und Arbeitsspeicher fragmentieren.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlArray::GetData](#getdata).

##  <a name="setatgrow"></a>  CAtlArray::SetAtGrow

Rufen Sie diese Methode, um den Wert eines Elements in das Array-Objekt, und erweitern das Array als erforderlich festgelegt.

```
void SetAtGrow(size_t iElement, INARGTYPE element);
```

### <a name="parameters"></a>Parameter

*iElement*<br/>
Der Index verweist auf das Arrayelement festgelegt.

*element*<br/>
Der neue Wert des angegebenen Elements.

### <a name="remarks"></a>Hinweise

Ersetzt den Wert des Elements vom Index verweist. Wenn *"IElement"* ist größer als die aktuelle Größe des Arrays, das Array wird automatisch erhöht, über einen Aufruf an [CAtlArray::SetCount](#setcount). In Debugbuilds einer ATLASSERT wird ausgelöst, wenn die `CAtlArray` -Objekt ist ungültig. Ungültige Parameter können zu unvorhersehbaren Ergebnissen führen, in Retail-Builds.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#12](../../atl/codesnippet/cpp/catlarray-class_12.cpp)]

## <a name="see-also"></a>Siehe auch

[MMXSwarm-Beispiel](../../overview/visual-cpp-samples.md)<br/>
[-Beispiel-Beispiel](../../overview/visual-cpp-samples.md)<br/>
[UpdatePV-Beispiel](../../overview/visual-cpp-samples.md)<br/>
[Marquee-Beispiel](../../overview/visual-cpp-samples.md)<br/>
[CArray-Klasse](../../mfc/reference/carray-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
