---
title: COleSafeArray-Klasse
ms.date: 08/29/2019
f1_keywords:
- COleSafeArray
- AFXDISP/COleSafeArray
- AFXDISP/COleSafeArray::COleSafeArray
- AFXDISP/COleSafeArray::AccessData
- AFXDISP/COleSafeArray::AllocData
- AFXDISP/COleSafeArray::AllocDescriptor
- AFXDISP/COleSafeArray::Attach
- AFXDISP/COleSafeArray::Clear
- AFXDISP/COleSafeArray::Copy
- AFXDISP/COleSafeArray::Create
- AFXDISP/COleSafeArray::CreateOneDim
- AFXDISP/COleSafeArray::Destroy
- AFXDISP/COleSafeArray::DestroyData
- AFXDISP/COleSafeArray::DestroyDescriptor
- AFXDISP/COleSafeArray::Detach
- AFXDISP/COleSafeArray::GetByteArray
- AFXDISP/COleSafeArray::GetDim
- AFXDISP/COleSafeArray::GetElement
- AFXDISP/COleSafeArray::GetElemSize
- AFXDISP/COleSafeArray::GetLBound
- AFXDISP/COleSafeArray::GetOneDimSize
- AFXDISP/COleSafeArray::GetUBound
- AFXDISP/COleSafeArray::Lock
- AFXDISP/COleSafeArray::PtrOfIndex
- AFXDISP/COleSafeArray::PutElement
- AFXDISP/COleSafeArray::Redim
- AFXDISP/COleSafeArray::ResizeOneDim
- AFXDISP/COleSafeArray::UnaccessData
- AFXDISP/COleSafeArray::Unlock
helpviewer_keywords:
- COleSafeArray [MFC], COleSafeArray
- COleSafeArray [MFC], AccessData
- COleSafeArray [MFC], AllocData
- COleSafeArray [MFC], AllocDescriptor
- COleSafeArray [MFC], Attach
- COleSafeArray [MFC], Clear
- COleSafeArray [MFC], Copy
- COleSafeArray [MFC], Create
- COleSafeArray [MFC], CreateOneDim
- COleSafeArray [MFC], Destroy
- COleSafeArray [MFC], DestroyData
- COleSafeArray [MFC], DestroyDescriptor
- COleSafeArray [MFC], Detach
- COleSafeArray [MFC], GetByteArray
- COleSafeArray [MFC], GetDim
- COleSafeArray [MFC], GetElement
- COleSafeArray [MFC], GetElemSize
- COleSafeArray [MFC], GetLBound
- COleSafeArray [MFC], GetOneDimSize
- COleSafeArray [MFC], GetUBound
- COleSafeArray [MFC], Lock
- COleSafeArray [MFC], PtrOfIndex
- COleSafeArray [MFC], PutElement
- COleSafeArray [MFC], Redim
- COleSafeArray [MFC], ResizeOneDim
- COleSafeArray [MFC], UnaccessData
- COleSafeArray [MFC], Unlock
ms.assetid: f45a5224-5f48-40ec-9ddd-287ef9740150
ms.openlocfilehash: a0ce0fc03923806c9e044a7edae3178fd3429b76
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177392"
---
# <a name="colesafearray-class"></a>COleSafeArray-Klasse

Eine Klasse zum Arbeiten mit Arrays beliebiger Dimension und beliebigen Typs.

## <a name="syntax"></a>Syntax

```
class COleSafeArray : public tagVARIANT
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleSafeArray::COleSafeArray](#colesafearray)|Erstellt ein `COleSafeArray`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleSafeArray::AccessData](#accessdata)|Ruft einen Zeiger auf die Array Daten ab.|
|[COleSafeArray::AllocData](#allocdata)|Weist Speicher für das Array zu.|
|[COleSafeArray::AllocDescriptor](#allocdescriptor)|Weist Arbeitsspeicher für den Deskriptor des sicheren Arrays zu.|
|[COleSafeArray::Attach](#attach)|Übergibt die Steuerung des vorhandenen `VARIANT` Arrays an das `COleSafeArray` -Objekt.|
|[COleSafeArray::Clear](#clear)|Gibt alle Daten in der zugrunde `VARIANT`liegenden frei.|
|[COleSafeArray::Copy](#copy)|Erstellt eine Kopie eines vorhandenen Arrays.|
|[COleSafeArray::Create](#create)|Erstellt ein sicheres Array.|
|[COleSafeArray::CreateOneDim](#createonedim)|Erstellt ein eindimensionales `COleSafeArray` -Objekt.|
|[COleSafeArray::Destroy](#destroy)|Zerstört ein vorhandenes Array.|
|[COleSafeArray::DestroyData](#destroydata)|Zerstört Daten in einem sicheren Array.|
|[COleSafeArray::DestroyDescriptor](#destroydescriptor)|Zerstört einen Deskriptor eines sicheren Arrays.|
|[COleSafeArray::Detach](#detach)|Trennt das Variant-Array vom `COleSafeArray` -Objekt (sodass die Daten nicht freigegeben werden).|
|[COleSafeArray::GetByteArray](#getbytearray)|Kopiert den Inhalt des sicheren Arrays in ein [CByteArray](../../mfc/reference/cbytearray-class.md).|
|[COleSafeArray::GetDim](#getdim)|Gibt die Anzahl der Dimensionen des Arrays zurück.|
|[COleSafeArray::GetElement](#getelement)|Ruft ein einzelnes Element des sicheren Arrays ab.|
|[COleSafeArray::GetElemSize](#getelemsize)|Gibt die Größe eines Elements in einem sicheren Array in Bytes zurück.|
|[COleSafeArray::GetLBound](#getlbound)|Gibt die untere Grenze für eine beliebige Dimension eines sicheren Arrays zurück.|
|[COleSafeArray::GetOneDimSize](#getonedimsize)|Gibt die Anzahl der Elemente im eindimensionalen `COleSafeArray` -Objekt zurück.|
|[COleSafeArray::GetUBound](#getubound)|Gibt die obere Grenze für eine beliebige Dimension eines sicheren Arrays zurück.|
|[COleSafeArray::Lock](#lock)|Erhöht die Sperrenanzahl eines Arrays und platziert einen Zeiger auf die Array Daten im Array Deskriptor.|
|[COleSafeArray::PtrOfIndex](#ptrofindex)|Gibt einen Zeiger auf das indizierte Element zurück.|
|[COleSafeArray::PutElement](#putelement)|Weist ein einzelnes Element im Array zu.|
|[COleSafeArray::Redim](#redim)|Ändert die am wenigsten bedeutende (am weitesten rechts) gebundene Grenze eines sicheren Arrays.|
|[COleSafeArray::ResizeOneDim](#resizeonedim)|Ändert die Anzahl von Elementen in einem eindimensionalen `COleSafeArray` Objekt.|
|[COleSafeArray::UnaccessData](#unaccessdata)|Verringert die Sperrenanzahl eines Arrays und erklärt den von `AccessData`abgerufenen Zeiger für ungültig.|
|[COleSafeArray::Unlock](#unlock)|Verringert die Sperrenanzahl eines Arrays, damit Sie freigegeben oder geändert werden kann.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[COleSafeArray:: Operator lpcvariant](#operator_lpcvariant)|`VARIANT` Greift`COleSafeArray` auf die zugrunde liegende Struktur des-Objekts zu.|
|[COleSafeArray:: Operator lpvariant](#operator_lpvariant)|`VARIANT` Greift`COleSafeArray` auf die zugrunde liegende Struktur des-Objekts zu.|
|[COleSafeArray::operator =](#operator_eq)|Kopiert Werte in ein `COleSafeArray` -Objekt`SAFEARRAY`( `VARIANT`, `COleVariant`,, `COleSafeArray` oder-Array).|
|[COleSafeArray::operator ==](#operator_eq_eq)|Vergleicht zwei Variant-Arrays`SAFEARRAY`( `VARIANT` `COleVariant`-,- `COleSafeArray` ,-oder-Arrays).|
|[COleSafeArray::-Operator&lt;&lt;](#operator_lt_lt)|Gibt den Inhalt eines- `COleSafeArray` Objekts in den Dumpkontext aus.|

## <a name="remarks"></a>Hinweise

`COleSafeArray`wird von der OLE `VARIANT` -Struktur abgeleitet. Die OLE `SAFEARRAY` -Element Funktionen sind über `COleSafeArray`verfügbar, sowie eine Reihe von Element Funktionen, die speziell für eindimensionale Bytearrays entwickelt wurden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`tagVARIANT`

`COleSafeArray`

## <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

##  <a name="accessdata"></a>COleSafeArray:: AccessData

Ruft einen Zeiger auf die Array Daten ab.

```
void AccessData(void** ppvData);
```

### <a name="parameters"></a>Parameter

*ppvData*<br/>
Ein Zeiger auf einen Zeiger auf die Array Daten.

### <a name="remarks"></a>Hinweise

Bei einem Fehler löst die Funktion eine [cmemoryexception](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md)aus.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#26](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]

##  <a name="allocdata"></a>COleSafeArray:: zugewiesene Daten

Weist Speicher für ein sicheres Array zu.

```
void AllocData();
```

### <a name="remarks"></a>Hinweise

Bei einem Fehler löst die Funktion eine [cmemoryexception](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md)aus.

##  <a name="allocdescriptor"></a>COleSafeArray:: Zuweisung-Deskriptor

Weist Arbeitsspeicher für den Deskriptor eines sicheren Arrays zu.

```
void AllocDescriptor(DWORD dwDims);
```

### <a name="parameters"></a>Parameter

*dwDims*<br/>
Anzahl der Dimensionen im sicheren Array.

### <a name="remarks"></a>Hinweise

Bei einem Fehler löst die Funktion eine [cmemoryexception](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md)aus.

##  <a name="attach"></a>COleSafeArray:: Attach

Ermöglicht das Steuern der Daten in einem vorhandenen `VARIANT` Array an das `COleSafeArray` -Objekt.

```
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>Parameter

*varSrc*<br/>
Ein `VARIANT`-Objekt. Der *varSrc* -Parameter muss den VarType- [VT_ARRAY](/windows/win32/api/wtypes/ne-wtypes-varenum)aufweisen.

### <a name="remarks"></a>Hinweise

Der Typ `VARIANT`der Quelle ist auf VT_EMPTY festgelegt. Diese Funktion löscht ggf. die aktuellen Array Daten.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [COleSafeArray:: AccessData](#accessdata).

##  <a name="clear"></a>COleSafeArray:: Clear

Löscht das sichere Array.

```
void Clear();
```

### <a name="remarks"></a>Hinweise

Die-Funktion löscht ein sicheres Array, indem `VARTYPE` die des-Objekts auf VT_EMPTY festgelegt wird. Der aktuelle Inhalt wird freigegeben, und das Array wird freigegeben.

##  <a name="colesafearray"></a>COleSafeArray:: COleSafeArray

Erstellt ein `COleSafeArray`-Objekt.

```
COleSafeArray();

COleSafeArray(
    const SAFEARRAY& saSrc,
    VARTYPE vtSrc);

COleSafeArray(
    LPCSAFEARRAY pSrc,
    VARTYPE vtSrc);

COleSafeArray(const COleSafeArray& saSrc);
COleSafeArray(const VARIANT& varSrc);
COleSafeArray(LPCVARIANT pSrc);
COleSafeArray(const COleVariant& varSrc);
```

### <a name="parameters"></a>Parameter

*saSrc*<br/>
Ein vorhandenes `COleSafeArray` - `SAFEARRAY` Objekt oder, das in das `COleSafeArray` neue-Objekt kopiert werden soll.

*vtSrc*<br/>
Der VarType des neuen `COleSafeArray` -Objekts.

*psaSrc*<br/>
Ein Zeiger auf einen `SAFEARRAY` , der in das neue `COleSafeArray` -Objekt kopiert werden soll.

*varSrc*<br/>
Ein `VARIANT` vorhandenes `COleVariant` -oder-Objekt, das in `COleSafeArray` das neue-Objekt kopiert werden soll.

*pSrc*<br/>
Ein Zeiger auf ein `VARIANT` -Objekt, das in das neue `COleSafeArray` -Objekt kopiert werden soll.

### <a name="remarks"></a>Hinweise

Alle diese Konstruktoren erstellen neue `COleSafeArray` -Objekte. Wenn kein-Parameter vorhanden ist, wird `COleSafeArray` ein leeres-Objekt erstellt (VT_EMPTY). Wenn der `COleSafeArray` aus einem anderen Array kopiert wird, dessen VarType implizit bekannt ist `COleSafeArray`( `COleVariant`ein, `VARIANT`oder), wird der VarType des Quell Arrays beibehalten und muss nicht angegeben werden. Wenn der `COleSafeArray` aus einem anderen Array kopiert wird, dessen VarType nicht bekannt`SAFEARRAY`ist (), muss der VarType im *vzrc* -Parameter angegeben werden.

Bei einem Fehler löst die Funktion eine [cmemoryexception](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md)aus.

##  <a name="copy"></a>COleSafeArray:: Copy

Erstellt eine Kopie eines vorhandenen sicheren Arrays.

```
void Copy(LPSAFEARRAY* ppsa);
```

### <a name="parameters"></a>Parameter

*ppsa*<br/>
Ein Zeiger auf einen Speicherort, an dem der neue Array Deskriptor zurückgegeben werden soll.

### <a name="remarks"></a>Hinweise

Bei einem Fehler löst die Funktion eine [cmemoryexception](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md)aus.

##  <a name="create"></a>COleSafeArray:: Create

Ordnet die Daten für das Array zu und initialisiert sie.

```
void Create(
    VARTYPE vtSrc,
    DWORD dwDims,
    DWORD* rgElements);

void Create(
    VARTYPE vtSrc,
    DWORD dwDims,
    SAFEARRAYBOUND* rgsabounds);
```

### <a name="parameters"></a>Parameter

*vtSrc*<br/>
Der Basistyp des Arrays (d. h. der VarType-Wert für jedes Element des Arrays). Der VarType ist auf eine Teilmenge der Variant-Typen beschränkt. Weder das VT_ARRAY-Flag noch das VT_BYREF-Flag kann festgelegt werden. VT_EMPTY und VT_NULL sind keine gültigen Basis Typen für das Array. Alle anderen Typen sind zulässig.

*dwDims*<br/>
Anzahl der Dimensionen im Array. Dies kann geändert werden, nachdem das Array mit [ReDim](#redim)erstellt wurde.

*rgElements*<br/>
Zeiger auf ein Array mit der Anzahl von Elementen für jede Dimension im Array.

*rgsabounds*<br/>
Zeiger auf einen Vektor von Begrenzungen (einen für jede Dimension), der für das Array zuzuordnen ist.

### <a name="remarks"></a>Hinweise

Diese Funktion löscht bei Bedarf die aktuellen Array Daten. Bei einem Fehler löst die Funktion eine [cmemoryexception](../../mfc/reference/cmemoryexception-class.md)aus.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

##  <a name="createonedim"></a>COleSafeArray:: erkreateonedim

Erstellt ein neues eindimensionales `COleSafeArray` -Objekt.

```
void CreateOneDim(
    VARTYPE vtSrc,
    DWORD dwElements,
    const void* pvSrcData = NULL,
    long nLBound = 0);
```

### <a name="parameters"></a>Parameter

*vtSrc*<br/>
Der Basistyp des Arrays (d. h. der VarType-Wert für jedes Element des Arrays).

*dwElements*<br/>
Anzahl der Elemente im Array. Dies kann geändert werden, nachdem das Array mit [resizeonedim](#resizeonedim)erstellt wurde.

*pvSrcData*<br/>
Ein Zeiger auf die Daten, die in das Array kopiert werden sollen.

*nLBound*<br/>
Die untere Grenze des Arrays.

### <a name="remarks"></a>Hinweise

Die-Funktion ordnet die Daten für das Array zu und initialisiert Sie, wobei die angegebenen Daten kopiert werden, wenn der Zeiger *pvsrcdata* nicht NULL ist.

Bei einem Fehler löst die Funktion eine [cmemoryexception](../../mfc/reference/cmemoryexception-class.md)aus.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#28](../../mfc/codesnippet/cpp/colesafearray-class_3.cpp)]

##  <a name="destroy"></a>COleSafeArray::D estroy

Zerstört einen vorhandenen Array Deskriptor und alle Daten im Array.

```
void Destroy();
```

### <a name="remarks"></a>Hinweise

Wenn Objekte im Array gespeichert werden, wird jedes Objekt freigegeben. Bei einem Fehler löst die Funktion eine [cmemoryexception](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md)aus.

##  <a name="destroydata"></a>COleSafeArray::D estroydata

Zerstört alle Daten in einem sicheren Array.

```
void DestroyData();
```

### <a name="remarks"></a>Hinweise

Wenn Objekte im Array gespeichert werden, wird jedes Objekt freigegeben. Bei einem Fehler löst die Funktion eine [cmemoryexception](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md)aus.

##  <a name="destroydescriptor"></a>COleSafeArray::D estroydescriptor

Zerstört einen Deskriptor eines sicheren Arrays.

```
void DestroyDescriptor();
```

### <a name="remarks"></a>Hinweise

Bei einem Fehler löst die Funktion eine [cmemoryexception](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md)aus.

##  <a name="detach"></a>COleSafeArray::D Etach

Trennt die `VARIANT` Daten aus dem `COleSafeArray` -Objekt.

```
VARIANT Detach();
```

### <a name="return-value"></a>Rückgabewert

Der zugrunde `VARIANT` liegende Wert `COleSafeArray` im-Objekt.

### <a name="remarks"></a>Hinweise

Die-Funktion trennt die Daten in einem sicheren Array, indem der VarType des-Objekts auf VT_EMPTY festgelegt wird. Es liegt in der Verantwortung des Aufrufers, das Array durch Aufrufen der Windows-Funktion [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear)freizugeben.

Bei einem Fehler löst die Funktion eine [COleException](../../mfc/reference/coleexception-class.md)aus.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [COleSafeArray::P utelement](#putelement).

##  <a name="getbytearray"></a>COleSafeArray:: getbytearray

Kopiert den Inhalt des sicheren Arrays in eine `CByteArray`.

```
void GetByteArray(CByteArray& bytes);
```

### <a name="parameters"></a>Parameter

*Satz*<br/>
Ein Verweis auf ein [CByteArray](../../mfc/reference/cbytearray-class.md) -Objekt.

##  <a name="getdim"></a>COleSafeArray:: getdim

Gibt die Anzahl der Dimensionen im `COleSafeArray` -Objekt zurück.

```
DWORD GetDim();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Dimensionen im sicheren Array.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

##  <a name="getelement"></a>COleSafeArray:: getElements

Ruft ein einzelnes Element des sicheren Arrays ab.

```
void GetElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>Parameter

*rgIndices*<br/>
Zeiger auf ein Array von Indizes für jede Dimension des Arrays.

*pvData*<br/>
Ein Zeiger auf den Speicherort, an dem das Element des Arrays platziert werden soll.

### <a name="remarks"></a>Hinweise

Diese Funktion ruft automatisch die Windows- `SafeArrayLock` Funktionen `SafeArrayUnlock` und vor und nach dem Abrufen des-Elements auf. Wenn das Datenelement eine Zeichenfolge, ein Objekt oder eine Variante ist, kopiert die Funktion das Element auf die richtige Weise. Der *pvData* -Parameter sollte auf einen ausreichend großen Puffer zeigen, um das-Element zu enthalten.

Bei einem Fehler löst die Funktion eine [cmemoryexception](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md)aus.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#29](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]

##  <a name="getelemsize"></a>COleSafeArray:: getelemsize

Ruft die Größe eines Elements in einem `COleSafeArray` -Objekt ab.

```
DWORD GetElemSize();
```

### <a name="return-value"></a>Rückgabewert

Die Größe der Elemente eines sicheren Arrays in Bytes.

##  <a name="getlbound"></a>COleSafeArray:: getlbound

Gibt die untere Grenze für eine beliebige Dimension eines `COleSafeArray` -Objekts zurück.

```
void GetLBound(
    DWORD dwDim,
    long* pLBound);
```

### <a name="parameters"></a>Parameter

*dwDim*<br/>
Die Array Dimension, für die die untere Grenze angezeigt werden soll.

*pLBound*<br/>
Zeiger auf die Position, an der die untere Grenze zurückgegeben werden soll.

### <a name="remarks"></a>Hinweise

Bei einem Fehler löst die Funktion eine [COleException](../../mfc/reference/coleexception-class.md)aus.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#30](../../mfc/codesnippet/cpp/colesafearray-class_5.cpp)]

##  <a name="getonedimsize"></a>COleSafeArray:: getonedimsize

Gibt die Anzahl der Elemente im eindimensionalen `COleSafeArray` -Objekt zurück.

```
DWORD GetOneDimSize();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente im eindimensionalen sicheren Array.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [COleSafeArray:: kreateonedim](#createonedim).

##  <a name="getubound"></a>COleSafeArray:: getubound

Gibt die obere Grenze für eine beliebige Dimension eines sicheren Arrays zurück.

```
void GetUBound(
    DWORD dwDim,
    long* pUBound);
```

### <a name="parameters"></a>Parameter

*dwDim*<br/>
Die Array Dimension, für die die obere Grenze angezeigt werden soll.

*pUBound*<br/>
Zeiger auf den Speicherort, an dem die obere Grenze zurückgegeben wird.

### <a name="remarks"></a>Hinweise

Bei einem Fehler löst die Funktion eine [COleException](../../mfc/reference/coleexception-class.md)aus.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#31](../../mfc/codesnippet/cpp/colesafearray-class_6.cpp)]

##  <a name="lock"></a>COleSafeArray:: Lock

Erhöht die Sperrenanzahl eines Arrays und platziert einen Zeiger auf die Array Daten im Array Deskriptor.

```
void Lock();
```

### <a name="remarks"></a>Hinweise

Bei einem Fehler wird eine [COleException](../../mfc/reference/coleexception-class.md)ausgelöst.

Der Zeiger im Array Deskriptor ist gültig, bis `Unlock` aufgerufen wird. Aufrufe von `Lock` können eingebettet werden. `Unlock` es ist eine gleich große Anzahl von Aufrufen von erforderlich.

Ein Array kann nicht gelöscht werden, wenn es gesperrt ist.

##  <a name="operator_lpcvariant"></a>COleSafeArray:: Operator lpcvariant

Aufrufen dieses Umwandlungs Operators, um auf `VARIANT` die zugrunde liegende `COleSafeArray` Struktur für dieses Objekt zuzugreifen.

```
operator LPCVARIANT() const;
```

##  <a name="operator_lpvariant"></a>COleSafeArray:: Operator lpvariant

Aufrufen dieses Umwandlungs Operators, um auf `VARIANT` die zugrunde liegende `COleSafeArray` Struktur für dieses Objekt zuzugreifen.

```
operator LPVARIANT();
```

### <a name="remarks"></a>Hinweise

Beachten Sie, dass beim Ändern des `VARIANT` Werts in der Struktur, auf die der von dieser Funktion zurückgegebene Zeiger zugreift, der Wert dieses `COleSafeArray` Objekts geändert wird.

##  <a name="operator_eq"></a>COleSafeArray:: Operator =

Diese überladenen Zuweisungs Operatoren kopieren den `COleSafeArray` Quellwert in dieses Objekt.

```
COleSafeArray& operator=(const COleSafeArray& saSrc);
COleSafeArray& operator=(const VARIANT& varSrc);
COleSafeArray& operator=(LPCVARIANT pSrc);
COleSafeArray& operator=(const COleVariant& varSrc);
```

### <a name="remarks"></a>Hinweise

Eine kurze Beschreibung der einzelnen Operatoren folgt:

- **Operator = (** *sasrc* **)** Kopiert ein vorhandenes `COleSafeArray` -Objekt in dieses-Objekt.

- **Operator = (** *varSrc* **)** Kopiert ein `VARIANT` vorhandenes `COleVariant` -oder-Array in dieses-Objekt.

- **Operator = (** *psrc* **)** Kopiert das `VARIANT` Array Objekt, auf das *psrc* zugreift, in dieses-Objekt.

##  <a name="operator_eq_eq"></a>COleSafeArray:: Operator = =

Dieser Operator vergleicht zwei Arrays (`SAFEARRAY` `COleVariant`, `VARIANT`, oder `COleSafeArray` Arrays) und gibt einen Wert ungleich 0 (null) zurück, wenn Sie gleich sind, andernfalls 0.

```
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;

BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;

BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;
```

### <a name="remarks"></a>Hinweise

Zwei Arrays sind gleich, wenn Sie die gleiche Anzahl von Dimensionen, die gleiche Größe in jeder Dimension und die gleichen Element Werte aufweisen.

##  <a name="operator_lt_lt"></a>COleSafeArray::-Operator&lt;&lt;

Der `COleSafeArray` Einfügungs Operator (< <) unterstützt das Diagnose- `COleSafeArray` und Speichern eines-Objekts in einem Archiv.

```
CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,
    COleSafeArray& saSrc);
```

##  <a name="ptrofindex"></a>COleSafeArray::P trofindex

Gibt einen Zeiger auf das Element zurück, das durch die Indexwerte angegeben wird.

```
void PtrOfIndex(
    long* rgIndices,
    void** ppvData);
```

### <a name="parameters"></a>Parameter

*rgIndices*<br/>
Ein Array von Indexwerten, die ein Element des Arrays identifizieren. Alle Indizes für das-Element müssen angegeben werden.

*ppvData*<br/>
Bei Rückgabe ein Zeiger auf das Element, das durch die Werte in *rgindices*identifiziert wird.

##  <a name="putelement"></a>COleSafeArray::P utelement

Weist ein einzelnes Element im Array zu.

```
void PutElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>Parameter

*rgIndices*<br/>
Zeiger auf ein Array von Indizes für jede Dimension des Arrays.

*pvData*<br/>
Zeiger auf die Daten, die dem Array zuzuweisen sind. VT_DISPATCH-, VT_UNKNOWN-und VT_BSTR-Variant-Typen sind Zeiger und erfordern keine andere Dereferenzierungsebene.

### <a name="remarks"></a>Hinweise

Diese Funktion ruft automatisch die Windows-Funktionen [safearraylock](/windows/win32/api/oleauto/nf-oleauto-safearraylock) und [safearrayunlock](/windows/win32/api/oleauto/nf-oleauto-safearrayunlock) vor und nach dem Zuweisen des-Elements auf. Ist das Datenelement eine Zeichenfolge, ein Objekt oder eine Variante, kopiert die Funktion es korrekt, und wenn das vorhandene Element eine Zeichenfolge, ein Objekt oder eine Variante ist, wird es korrekt gelöscht.

Beachten Sie, dass Sie mehrere Sperren auf einem Array verwenden können, damit Sie Elemente in einem Array platzieren können, während das Array durch andere Vorgänge gesperrt ist.

Bei einem Fehler löst die Funktion eine [cmemoryexception](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md)aus.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#32](../../mfc/codesnippet/cpp/colesafearray-class_7.cpp)]

##  <a name="redim"></a>COleSafeArray:: ReDim

Ändert die am wenigsten bedeutende (am weitesten rechts) gebundene Grenze eines sicheren Arrays.

```
void Redim(SAFEARRAYBOUND* psaboundNew);
```

### <a name="parameters"></a>Parameter

*psaboundNew*<br/>
Ein Zeiger auf eine neue, sichere Array gebundene Struktur, die die neue Array Grenze enthält. Nur die am wenigsten bedeutende Dimension eines Arrays kann geändert werden.

### <a name="remarks"></a>Hinweise

Bei einem Fehler löst die Funktion eine [COleException](../../mfc/reference/coleexception-class.md)aus.

##  <a name="resizeonedim"></a>COleSafeArray:: resizeonedim

Ändert die Anzahl von Elementen in einem eindimensionalen `COleSafeArray` Objekt.

```
void ResizeOneDim(DWORD dwElements);
```

### <a name="parameters"></a>Parameter

*dwElements*<br/>
Anzahl der Elemente im eindimensionalen sicheren Array.

### <a name="remarks"></a>Hinweise

Bei einem Fehler löst die Funktion eine [COleException](../../mfc/reference/coleexception-class.md)aus.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [COleSafeArray:: kreateonedim](#createonedim).

##  <a name="unaccessdata"></a>COleSafeArray:: unaccessdata

Verringert die Sperrenanzahl eines Arrays und erklärt den von `AccessData`abgerufenen Zeiger für ungültig.

```
void UnaccessData();
```

### <a name="remarks"></a>Hinweise

Bei einem Fehler löst die Funktion eine [COleException](../../mfc/reference/coleexception-class.md)aus.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [COleSafeArray:: AccessData](#accessdata).

##  <a name="unlock"></a>COleSafeArray:: Unlock

Verringert die Sperrenanzahl eines Arrays, damit Sie freigegeben oder geändert werden kann.

```
void Unlock();
```

### <a name="remarks"></a>Hinweise

Diese Funktion wird aufgerufen, nachdem der Zugriff auf die Daten in einem Array abgeschlossen wurde. Bei einem Fehler wird eine [COleException](../../mfc/reference/coleexception-class.md)ausgelöst.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleVariant-Klasse](../../mfc/reference/colevariant-class.md)<br/>
[CRecordset-Klasse](../../mfc/reference/crecordset-class.md)<br/>
[CDatabase-Klasse](../../mfc/reference/cdatabase-class.md)<br/>
