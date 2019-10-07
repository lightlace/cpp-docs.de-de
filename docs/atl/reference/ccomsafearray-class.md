---
title: CComSafeArray-Klasse
ms.date: 05/06/2019
f1_keywords:
- CComSafeArray
- ATLSAFE/ATL::CComSafeArray
- ATLSAFE/ATL::CComSafeArray::CComSafeArray
- ATLSAFE/ATL::CComSafeArray::Add
- ATLSAFE/ATL::CComSafeArray::Attach
- ATLSAFE/ATL::CComSafeArray::CopyFrom
- ATLSAFE/ATL::CComSafeArray::CopyTo
- ATLSAFE/ATL::CComSafeArray::Create
- ATLSAFE/ATL::CComSafeArray::Destroy
- ATLSAFE/ATL::CComSafeArray::Detach
- ATLSAFE/ATL::CComSafeArray::GetAt
- ATLSAFE/ATL::CComSafeArray::GetCount
- ATLSAFE/ATL::CComSafeArray::GetDimensions
- ATLSAFE/ATL::CComSafeArray::GetLowerBound
- ATLSAFE/ATL::CComSafeArray::GetSafeArrayPtr
- ATLSAFE/ATL::CComSafeArray::GetType
- ATLSAFE/ATL::CComSafeArray::GetUpperBound
- ATLSAFE/ATL::CComSafeArray::IsSizable
- ATLSAFE/ATL::CComSafeArray::MultiDimGetAt
- ATLSAFE/ATL::CComSafeArray::MultiDimSetAt
- ATLSAFE/ATL::CComSafeArray::Resize
- ATLSAFE/ATL::CComSafeArray::SetAt
- ATLSAFE/ATL::CComSafeArray::m_psa
helpviewer_keywords:
- CComSafeArray class
ms.assetid: ee349aef-33db-4c85-bd08-5d86a3c9d53a
ms.openlocfilehash: 79b1dc844f53f739dc48eb6177e57810ff0c8412
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70739594"
---
# <a name="ccomsafearray-class"></a>CComSafeArray-Klasse

Diese Klasse ist ein Wrapper für die `SAFEARRAY` -Struktur.

## <a name="syntax"></a>Syntax

```
template <typename T, VARTYPE _vartype = _ATL_AutomationType<T>::type>
class CComSafeArray
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ der im Array gespeicherten Daten.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComSafeArray::CComSafeArray](#ccomsafearray)|Der Konstruktor.|
|[CComSafeArray::~CComSafeArray](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComSafeArray::Add](#add)|Fügt einem `SAFEARRAY` `CComSafeArray`oder mehreren-Elementen oder-Strukturen hinzu.|
|[CComSafeArray::Attach](#attach)|Fügt eine `SAFEARRAY` -Struktur an `CComSafeArray` ein-Objekt an.|
|[CComSafeArray::CopyFrom](#copyfrom)|Kopiert den Inhalt einer `SAFEARRAY` -Struktur in das `CComSafeArray` -Objekt.|
|[CComSafeArray::CopyTo](#copyto)|Erstellt eine Kopie des `CComSafeArray`-Objekts.|
|[CComSafeArray::Create](#create)|Erstellt ein `CComSafeArray`-Objekt.|
|[CComSafeArray::Destroy](#destroy)|Zerstört ein `CComSafeArray`-Objekt.|
|[CComSafeArray::Detach](#detach)|Trennt einen `SAFEARRAY` von einem `CComSafeArray` -Objekt.|
|[CComSafeArray::GetAt](#getat)|Ruft ein einzelnes Element aus einem eindimensionalen Array ab.|
|[CComSafeArray::GetCount](#getcount)|Gibt die Anzahl der Elemente des Arrays zurück.|
|[CComSafeArray::GetDimensions](#getdimensions)|Gibt die Anzahl der Dimensionen des Arrays zurück.|
|[CComSafeArray::GetLowerBound](#getlowerbound)|Gibt die untere Grenze für eine bestimmte Dimension des Arrays zurück.|
|[CComSafeArray::GetSafeArrayPtr](#getsafearrayptr)|Gibt die Adresse des `m_psa` -Datenelements zurück.|
|[CComSafeArray::GetType](#gettype)|Gibt den Typ der im Array gespeicherten Daten zurück.|
|[CComSafeArray::GetUpperBound](#getupperbound)|Gibt die obere Grenze für eine bestimmte Dimension des Arrays zurück.|
|[CComSafeArray::IsSizable](#issizable)|Testet, ob die Größe eines `CComSafeArray` -Objekts geändert werden kann.|
|[CComSafeArray::MultiDimGetAt](#multidimgetat)|Ruft ein einzelnes Element aus einem mehrdimensionalen Array ab.|
|[CComSafeArray::MultiDimSetAt](#multidimsetat)|Legt den Wert eines Elements in einem mehrdimensionalen Array fest.|
|[CComSafeArray::Resize](#resize)|Ändert die Größe eines `CComSafeArray` -Objekts.|
|[CComSafeArray::SetAt](#setat)|Legt den Wert eines Elements in einem eindimensionalen Array fest.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CComSafeArray:: Operator lpsafearray](#operator_lpsafearray)|Wandelt einen Wert in einen `SAFEARRAY` -Zeiger um.|
|[CComSafeArray::operator\[\]](ccomsafearray-class.md#operator_at)|Ruft ein Element aus dem Array ab.|
|[CComSafeArray::operator =](#operator_eq)|Zuweisungsoperator.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComSafeArray::m_psa](#m_psa)|Dieser Datenmember enthält die Adresse der `SAFEARRAY` -Struktur.|

## <a name="remarks"></a>Hinweise

`CComSafeArray` stellt einen Wrapper für die [SAFEARRAY Data Type](/windows/win32/api/oaidl/ns-oaidl-safearray) -Klasse bereit, wodurch sich ein- und mehrdimensionale Arrays von nahezu jedem der VARIANT-unterstützten Typen problemlos erstellen und verwalten lassen.

`CComSafeArray` vereinfacht die Übergabe von Arrays zwischen Prozessen und bietet darüber hinaus zusätzliche Sicherheit durch Überprüfen der Arrayindexwerte anhand der oberen und unteren Grenzen.

Die untere Grenze eines `CComSafeArray` kann bei einem beliebigen benutzerdefinierten Wert beginnen, Arrays, auf die über C++ zugegriffen wird, sollte jedoch eine Untergrenze von 0 verwenden. Andere Sprachen wie Visual Basic können andere Begrenzungswerte (z. B. -10 bis 10) verwenden.

Verwenden Sie [CComSafeArray::Create](#create) , um ein `CComSafeArray` -Objekt zu erstellen, und [CComSafeArray::Destroy](#destroy) , um es zu löschen.

Ein `CComSafeArray` kann die folgende Teilmenge von VARIANT-Datentypen enthalten:

|VARTYPE|Beschreibung|
|-------------|-----------------|
|VT_I1|char|
|VT_I2|short|
|VT_I4|int|
|VT_I4|long|
|VT_I8|longlong|
|VT_UI1|byte|
|VT_UI2|ushort|
|VT_UI4|uint|
|VT_UI4|ulong|
|VT_UI8|ulonglong|
|VT_R4|float|
|VT_R8|double|
|VT_DECIMAL|Dezimalzeiger|
|VT_VARIANT|Variant-Zeiger|
|VT_CY|Currency-Datentyp|

## <a name="requirements"></a>Anforderungen

**Header:** atlsafe.h

## <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#75](../../atl/codesnippet/cpp/ccomsafearray-class_1.cpp)]

##  <a name="add"></a>CComSafeArray:: Add

Fügt einem `SAFEARRAY` `CComSafeArray`oder mehreren-Elementen oder-Strukturen hinzu.

```
HRESULT Add(const SAFEARRAY* psaSrc);
HRESULT Add(ULONG ulCount, const T* pT, BOOL bCopy = TRUE);
HRESULT Add(const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>Parameter

*psaSrc*<br/>
Ein Zeiger auf ein `SAFEARRAY` -Objekt.

*ulCount*<br/>
Die Anzahl der-Objekte, die dem Array hinzugefügt werden sollen.

*pT*<br/>
Ein Zeiger auf ein oder mehrere-Objekte, die dem Array hinzugefügt werden sollen.

*t*<br/>
Ein Verweis auf das-Objekt, das dem Array hinzugefügt werden soll.

*bCopy*<br/>
Gibt an, ob eine Kopie der Daten erstellt werden soll. Der Standardwert ist "true".

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Die neuen-Objekte werden an das Ende des vorhandenen `SAFEARRAY` -Objekts angehängt. Das Hinzufügen eines Objekts zu `SAFEARRAY` einem mehrdimensionalen Objekt wird nicht unterstützt. Wenn Sie ein vorhandenes Array von-Objekten hinzufügen, müssen beide Arrays Elemente desselben Typs enthalten.

Das *bcopy* -Flag wird berücksichtigt, wenn einem Array Elemente vom Typ BSTR oder Variant hinzugefügt werden. Der Standardwert true stellt sicher, dass eine neue Kopie der Daten erstellt wird, wenn das Element dem Array hinzugefügt wird.

##  <a name="attach"></a>CComSafeArray:: Attach

Fügt eine `SAFEARRAY` -Struktur an `CComSafeArray` ein-Objekt an.

```
HRESULT Attach(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>Parameter

*psaSrc*<br/>
Ein Zeiger auf die `SAFEARRAY` -Struktur.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Fügt eine `SAFEARRAY` -Struktur an `CComSafeArray` ein-Objekt an und `CComSafeArray` stellt die vorhandenen Methoden zur Verfügung.

##  <a name="ccomsafearray"></a>CComSafeArray:: CComSafeArray

Der Konstruktor.

```
CComSafeArray();
CComSafeArray(const SAFEARRAYBOUND& bound);
CComSafeArray(ULONG  ulCount, LONG lLBound = 0);
CComSafeArray(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
CComSafeArray(const CComSafeArray& saSrc);
CComSafeArray(const SAFEARRAY& saSrc);
CComSafeArray(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>Parameter

*binden*<br/>
Eine `SAFEARRAYBOUND`-Struktur.

*ulCount*<br/>
Die Anzahl der Elemente im Array.

*lLBound*<br/>
Der untere gebundene Wert. Das heißt, der Index des ersten Elements im Array.

*pBound*<br/>
Ein Zeiger auf eine `SAFEARRAYBOUND` -Struktur.

*uDims*<br/>
Die Anzahl der Dimensionen im Array.

*saSrc*<br/>
Ein Verweis auf eine `SAFEARRAY` Struktur oder `CComSafeArray` ein Objekt. In beiden Fällen verwendet der Konstruktor diesen Verweis, um eine Kopie des Arrays zu erstellen, sodass nach der Erstellung nicht auf das Array verwiesen wird.

*psaSrc*<br/>
Ein Zeiger auf eine `SAFEARRAY` -Struktur. Der Konstruktor verwendet diese Adresse, um eine Kopie des Arrays zu erstellen, sodass nach der Erstellung nicht auf das Array verwiesen wird.

### <a name="remarks"></a>Hinweise

Erstellt ein `CComSafeArray`-Objekt.

##  <a name="dtor"></a>CComSafeArray:: ~ CComSafeArray

Der Destruktor.

```
~CComSafeArray() throw()
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordneten Ressourcen frei.

##  <a name="copyfrom"></a>CComSafeArray:: CopyFrom

Kopiert den Inhalt einer `SAFEARRAY` -Struktur in das `CComSafeArray` -Objekt.

```
HRESULT CopyFrom(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>Parameter

*ppArray*<br/>
Zeiger auf das `SAFEARRAY` , das kopiert werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Diese Methode kopiert den Inhalt einer `SAFEARRAY` in das aktuelle `CComSafeArray` -Objekt. Der vorhandene Inhalt des Arrays wird ersetzt.

##  <a name="copyto"></a>CComSafeArray:: CopyTo

Erstellt eine Kopie des `CComSafeArray`-Objekts.

```
HRESULT CopyTo(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>Parameter

*ppArray*<br/>
Ein Zeiger auf einen Speicherort, an dem die neue `SAFEARRAY`erstellt werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Diese Methode kopiert den Inhalt eines `CComSafeArray` -Objekts in eine `SAFEARRAY` -Struktur.

##  <a name="create"></a>  CComSafeArray::Create

Erstellt eine `CComSafeArray`.

```
HRESULT Create(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
HRESULT Create(ULONG ulCount = 0, LONG lLBound = 0);
```

### <a name="parameters"></a>Parameter

*pBound*<br/>
Ein Zeiger auf ein `SAFEARRAYBOUND` -Objekt.

*uDims*<br/>
Die Anzahl der Dimensionen im Array.

*ulCount*<br/>
Die Anzahl der Elemente im Array.

*lLBound*<br/>
Der untere gebundene Wert. Das heißt, der Index des ersten Elements im Array.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Ein `CComSafeArray` -Objekt kann aus einer vorhandenen `SAFEARRAYBOUND` -Struktur und der Anzahl von Dimensionen erstellt werden, oder durch Angeben der Anzahl von Elementen im Array und der unteren Grenze. Wenn von C++auf das Array zugegriffen werden soll, muss die untere Grenze 0 sein. Andere Sprachen können andere Werte für die untere Grenze zulassen (z. b. Visual Basic unterstützt Arrays mit Elementen mit einem Bereich, z. b.-10 bis 10).

##  <a name="destroy"></a>  CComSafeArray::Destroy

Zerstört ein `CComSafeArray`-Objekt.

```
HRESULT Destroy();
```

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Zerstört ein vorhandenes `CComSafeArray` -Objekt und alle darin enthaltenen Daten.

##  <a name="detach"></a>CComSafeArray::D Etach

Trennt einen `SAFEARRAY` von einem `CComSafeArray` -Objekt.

```
LPSAFEARRAY Detach();
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf ein `SAFEARRAY` -Objekt zurück.

### <a name="remarks"></a>Hinweise

Diese Methode trennt das `SAFEARRAY` -Objekt `CComSafeArray` vom-Objekt.

##  <a name="getat"></a>CComSafeArray:: GetAt

Ruft ein einzelnes Element aus einem eindimensionalen Array ab.

```
T& GetAt(LONG lIndex) const;
```

### <a name="parameters"></a>Parameter

*lIndex*<br/>
Die Indexnummer des Werts im Array, der zurückgegeben werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf das erforderliche Array Element zurück.

##  <a name="getcount"></a>CComSafeArray:: GetCount

Gibt die Anzahl der Elemente des Arrays zurück.

```
ULONG GetCount(UINT uDim = 0) const;
```

### <a name="parameters"></a>Parameter

*uDim*<br/>
Die Array Dimension.

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Elemente des Arrays zurück.

### <a name="remarks"></a>Hinweise

Wenn Sie mit einem mehrdimensionalen Array verwendet wird, gibt diese Methode nur die Anzahl von Elementen in einer bestimmten Dimension zurück.

##  <a name="getdimensions"></a>CComSafeArray:: GetDimensions

Gibt die Anzahl der Dimensionen des Arrays zurück.

```
UINT GetDimensions() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Dimensionen des Arrays zurück.

##  <a name="getlowerbound"></a>CComSafeArray:: GetLowerBound

Gibt die untere Grenze für eine bestimmte Dimension des Arrays zurück.

```
LONG GetLowerBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>Parameter

*uDim*<br/>
Die Array Dimension, für die die untere Grenze angezeigt werden soll. Wenn der Wert weggelassen wird, ist der Standardwert 0.

### <a name="return-value"></a>Rückgabewert

Gibt die untere Grenze zurück.

### <a name="remarks"></a>Hinweise

Wenn die untere Grenze 0 ist, gibt dies ein C-ähnliches Array an, dessen erstes Element die Element Nummer 0 ist. Im Fall eines Fehlers, z. b. eines ungültigen Dimensions Arguments, ruft `AtlThrow` diese Methode mit einem HRESULT auf, das den Fehler beschreibt.

##  <a name="getsafearrayptr"></a>CComSafeArray:: gezafearrayptr

Gibt die Adresse des `m_psa` -Datenelements zurück.

```
LPSAFEARRAY* GetSafeArrayPtr() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf den [CComSafeArray:: m_psa](#m_psa) -Datenmember zurück.

##  <a name="gettype"></a>CComSafeArray:: GetType

Gibt den Typ der im Array gespeicherten Daten zurück.

```
VARTYPE GetType() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt den Typ der im Array gespeicherten Daten zurück. dabei kann es sich um einen der folgenden Typen handeln:

|VARTYPE|Beschreibung|
|-------------|-----------------|
|VT_I1|char|
|VT_I2|short|
|VT_I4|int|
|VT_I4|long|
|VT_I8|longlong|
|VT_UI1|byte|
|VT_UI2|ushort|
|VT_UI4|uint|
|VT_UI4|ulong|
|VT_UI8|ulonglong|
|VT_R4|float|
|VT_R8|double|
|VT_DECIMAL|Dezimalzeiger|
|VT_VARIANT|Variant-Zeiger|
|VT_CY|Currency-Datentyp|

##  <a name="getupperbound"></a>CComSafeArray:: GetUpperBound

Gibt die obere Grenze für eine bestimmte Dimension des Arrays zurück.

```
LONG GetUpperBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>Parameter

*uDim*<br/>
Die Array Dimension, für die die obere Grenze angezeigt werden soll. Wenn der Wert weggelassen wird, ist der Standardwert 0.

### <a name="return-value"></a>Rückgabewert

Gibt die obere Grenze zurück. Dieser Wert ist inklusiv, der höchst gültige Index für diese Dimension.

### <a name="remarks"></a>Hinweise

Im Fall eines Fehlers, z. b. eines ungültigen Dimensions Arguments, ruft `AtlThrow` diese Methode mit einem HRESULT auf, das den Fehler beschreibt.

##  <a name="issizable"></a>CComSafeArray:: issisierbar

Testet, ob die Größe eines `CComSafeArray` -Objekts geändert werden kann.

```
bool IsSizable() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, `CComSafeArray` wenn die Größe der geändert werden kann, andernfalls false.

##  <a name="m_psa"></a>CComSafeArray:: m_psa

Enthält die Adresse der- `SAFEARRAY` Struktur, auf die zugegriffen wird.

```
LPSAFEARRAY m_psa;
```

##  <a name="multidimgetat"></a>CComSafeArray:: multidimgetat

Ruft ein einzelnes Element aus einem mehrdimensionalen Array ab.

```
HRESULT MultiDimGetAt(const LONG* alIndex, T& t);
```

### <a name="parameters"></a>Parameter

*alIndex*<br/>
Zeiger auf einen Vektor von Indizes für jede Dimension im Array. Die am weitesten links stehende (wichtigste) Dimension ist `alIndex[0]`.

*t*<br/>
Ein Verweis auf die zurückgegebenen Daten.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="multidimsetat"></a>CComSafeArray:: multidim-Tat

Legt den Wert eines Elements in einem mehrdimensionalen Array fest.

```
HRESULT MultiDimSetAt(const LONG* alIndex, const T& t);
```

### <a name="parameters"></a>Parameter

*alIndex*<br/>
Zeiger auf einen Vektor von Indizes für jede Dimension im Array. Die am weitesten rechts (am wenigsten bedeutende) `alIndex`Dimension ist [0].

*T*<br/>
Gibt den Wert des neuen Elements an.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Dies ist eine mehrdimensionale Version von [CComSafeArray::](#setat).

##  <a name="operator_at"></a>CComSafeArray::-Operator\[\]

Ruft ein Element aus dem Array ab.

```
T& operator[](long lindex) const;
T& operator[]int nindex) const;
```

### <a name="parameters"></a>Parameter

*lIndex, nIndex*<br/>
Die Indexnummer des erforderlichen Elements im Array.

### <a name="return-value"></a>Rückgabewert

Gibt das entsprechende Array Element zurück.

### <a name="remarks"></a>Hinweise

Führt eine ähnliche Funktion wie [CComSafeArray:: GetAt](#getat)aus, aber dieser Operator funktioniert nur mit eindimensionalen Arrays.

##  <a name="operator_eq"></a>CComSafeArray:: Operator =

Zuweisungsoperator.

```
ATL::CComSafeArray<T>& operator=(const ATL::CComSafeArray& saSrc);
ATL::CComSafeArray<T>& operator=(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>Parameter

*saSrc*<br/>
Ein Verweis auf ein `CComSafeArray`-Objekt.

*psaSrc*<br/>
Ein Zeiger auf ein `SAFEARRAY` -Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt den Typ der im Array gespeicherten Daten zurück.

##  <a name="operator_lpsafearray"></a>CComSafeArray:: Operator lpsafearray

Wandelt einen Wert in einen `SAFEARRAY` -Zeiger um.

```
operator LPSAFEARRAY() const;
```

### <a name="return-value"></a>Rückgabewert

Wandelt einen Wert in einen `SAFEARRAY` -Zeiger um.

##  <a name="resize"></a>CComSafeArray:: Resize

Ändert die Größe eines `CComSafeArray` -Objekts.

```
HRESULT Resize(const SAFEARRAYBOUND* pBound);
HRESULT Resize(ULONG ulCount, LONG lLBound = 0);
```

### <a name="parameters"></a>Parameter

*pBound*<br/>
Ein Zeiger auf eine `SAFEARRAYBOUND` -Struktur, die Informationen über die Anzahl der Elemente und die untere Grenze eines Arrays enthält.

*ulCount*<br/>
Die angeforderte Anzahl von Objekten im Array, dessen Größe geändert wurde.

*lLBound*<br/>
Die untere Grenze.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Diese Methode ändert nur die Größe der äußersten rechten Dimension. Die Größe von Arrays, die als false `IsResizable` zurückgegeben werden, wird nicht geändert.

##  <a name="setat"></a>CComSafeArray::

Legt den Wert eines Elements in einem eindimensionalen Array fest.

```
HRESULT SetAt(LONG lIndex, const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>Parameter

*lIndex*<br/>
Die Indexnummer des festzulegenden Array Elements.

*t*<br/>
Der neue Wert des angegebenen Elements.

*bCopy*<br/>
Gibt an, ob eine Kopie der Daten erstellt werden soll. Der Standardwert ist "true".

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Das *bcopy* -Flag wird berücksichtigt, wenn einem Array Elemente vom Typ BSTR oder Variant hinzugefügt werden. Der Standardwert true stellt sicher, dass eine neue Kopie der Daten erstellt wird, wenn das Element dem Array hinzugefügt wird.

## <a name="see-also"></a>Siehe auch

[SAFEARRAY-Datentyp](/windows/win32/api/oaidl/ns-oaidl-safearray)<br/>
[CComSafeArray::Create](#create)<br/>
[CComSafeArray::Destroy](#destroy)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
