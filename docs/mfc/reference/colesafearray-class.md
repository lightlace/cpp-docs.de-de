---
title: COleSafeArray-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1af4f8bbbfc6d7a90120fe367c608db37cb055a1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392995"
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
|[COleSafeArray::AccessData](#accessdata)|Ruft einen Zeiger auf die Daten des Arrays ab.|
|[COleSafeArray::AllocData](#allocdata)|Belegt Speicher für das Array.|
|[COleSafeArray::AllocDescriptor](#allocdescriptor)|Belegt Speicher für den Deskriptor des sicheren Arrays an.|
|[COleSafeArray::Attach](#attach)|Gibt die Kontrolle der vorhandenen `VARIANT` array an die `COleSafeArray` Objekt.|
|[COleSafeArray::Clear](#clear)|Alle Daten in der zugrunde liegenden frei `VARIANT`.|
|[COleSafeArray::Copy](#copy)|Erstellt eine Kopie eines vorhandenen Arrays.|
|[COleSafeArray::Create](#create)|Erstellt ein sicheres Array.|
|[COleSafeArray::CreateOneDim](#createonedim)|Erstellt ein eindimensionales `COleSafeArray` Objekt.|
|[COleSafeArray::Destroy](#destroy)|Löscht ein vorhandenes Array.|
|[COleSafeArray::DestroyData](#destroydata)|Daten in ein sicheres Array wird zerstört.|
|[COleSafeArray::DestroyDescriptor](#destroydescriptor)|Zerstört einen Deskriptor eines sicheren Arrays an.|
|[COleSafeArray::Detach](#detach)|Trennt den VARIANT-Array, aus der `COleSafeArray` Objekt (sodass die Daten nicht freigegeben werden).|
|[COleSafeArray::GetByteArray](#getbytearray)|Kopiert den Inhalt des sicheren Arrays in ein [CByteArray](../../mfc/reference/cbytearray-class.md).|
|[COleSafeArray::GetDim](#getdim)|Gibt die Anzahl der Dimensionen des Arrays zurück.|
|[Colesafearray:: GetElement](#getelement)|Ruft ein einzelnes Element des sicheren Arrays ab.|
|[COleSafeArray::GetElemSize](#getelemsize)|Gibt die Größe in Bytes, der ein Element in ein sicheres Array zurück.|
|[COleSafeArray::GetLBound](#getlbound)|Gibt die untere Grenze für eine bestimmte Dimension eines sicheren Arrays zurück.|
|[COleSafeArray::GetOneDimSize](#getonedimsize)|Gibt die Anzahl von Elementen im eindimensionalen `COleSafeArray` Objekt.|
|[COleSafeArray::GetUBound](#getubound)|Gibt die obere Grenze für eine bestimmte Dimension eines sicheren Arrays zurück.|
|[COleSafeArray::Lock](#lock)|Erhöht die Sperrenanzahl eines Arrays aus, und fügt einen Zeiger auf die Daten des Arrays, in der Deskriptor des Arrays.|
|[COleSafeArray::PtrOfIndex](#ptrofindex)|Gibt einen Zeiger auf das indizierte Element zurück.|
|[COleSafeArray::PutElement](#putelement)|Weist ein einzelnes Element im Array zu.|
|[COleSafeArray::Redim](#redim)|Ändert die unwichtigste (ganz rechts) Grenze eines sicheren Arrays an.|
|[COleSafeArray::ResizeOneDim](#resizeonedim)|Ändert die Anzahl der Elemente in einem eindimensionalen `COleSafeArray` Objekt.|
|[COleSafeArray::UnaccessData](#unaccessdata)|Verringert die Sperre eines Arrays zu zählen und erklärt den Zeiger abgerufen, indem `AccessData`.|
|[COleSafeArray::Unlock](#unlock)|Verringert die Sperrenanzahl eines Arrays, sodass es freigegeben oder geändert werden kann.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[COleSafeArray::operator LPCVARIANT](#operator_lpcvariant)|Greift auf die zugrunde liegende `VARIANT` Struktur der `COleSafeArray` Objekt.|
|[COleSafeArray::operator LPVARIANT](#operator_lpvariant)|Greift auf die zugrunde liegende `VARIANT` Struktur der `COleSafeArray` Objekt.|
|[COleSafeArray::operator =](#operator_eq)|Kopiert die Werte in einer `COleSafeArray` Objekt (`SAFEARRAY`, `VARIANT`, `COleVariant`, oder `COleSafeArray` Array).|
|[COleSafeArray::operator ==](#operator_eq_eq)|Vergleicht zwei Varianten Arrays (`SAFEARRAY`, `VARIANT`, `COleVariant`, oder `COleSafeArray` Arrays).|
|[COleSafeArray::operator &lt;&lt;](#operator_lt_lt)|Gibt den Inhalt von einem `COleSafeArray` Objekt in der Dumpkontext.|

## <a name="remarks"></a>Hinweise

`COleSafeArray` leitet sich von der OLE `VARIANT` Struktur. Die OLE `SAFEARRAY` Member-Funktionen stehen über `COleSafeArray`, auch als einen Satz von Memberfunktionen, die speziell für eindimensionale Arrays von Bytes.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`tagVARIANT`

`COleSafeArray`

## <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

##  <a name="accessdata"></a>  COleSafeArray::AccessData

Ruft einen Zeiger auf die Daten des Arrays ab.

```
void AccessData(void** ppvData);
```

### <a name="parameters"></a>Parameter

*ppvData*<br/>
Ein Zeiger auf einen Zeiger auf die Daten des Arrays.

### <a name="remarks"></a>Hinweise

Bei einem Fehler löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#26](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]

##  <a name="allocdata"></a>  COleSafeArray::AllocData

Belegt Speicher für ein sicheres Array.

```
void AllocData();
```

### <a name="remarks"></a>Hinweise

Bei einem Fehler löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="allocdescriptor"></a>  COleSafeArray::AllocDescriptor

Belegt Speicher für den Deskriptor eines sicheren Arrays an.

```
void AllocDescriptor(DWORD dwDims);
```

### <a name="parameters"></a>Parameter

*dwDims*<br/>
Anzahl der Dimensionen im sicheren Array.

### <a name="remarks"></a>Hinweise

Bei einem Fehler löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="attach"></a>  COleSafeArray::Attach

Steuerung der Daten in einer vorhandenen `VARIANT` array an die `COleSafeArray` Objekt.

```
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>Parameter

*varSrc*<br/>
Ein `VARIANT`-Objekt. Die *VarSrc* Parameter müssen VARTYPE [VT_ARRAY](/windows/desktop/api/wtypes/ne-wtypes-varenum).

### <a name="remarks"></a>Hinweise

Die Quelle `VARIANT`Typ auf VT_EMPTY festgelegt ist. Diese Funktion löscht die aktuellen Daten des Arrays, sofern vorhanden.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [COleSafeArray::AccessData](#accessdata).

##  <a name="clear"></a>  COleSafeArray::Clear

Löscht das sichere Array an.

```
void Clear();
```

### <a name="remarks"></a>Hinweise

Die Funktion löscht ein sicheres Array durch Festlegen der `VARTYPE` des Objekts auf VT_EMPTY. Den aktuellen Inhalt veröffentlicht werden, und das Array wird freigegeben.

##  <a name="colesafearray"></a>  COleSafeArray::COleSafeArray

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
Eine vorhandene `COleSafeArray` Objekt oder `SAFEARRAY` in die neue kopiert werden `COleSafeArray` Objekt.

*vtSrc*<br/>
Der neuen VARTYPE `COleSafeArray` Objekt.

*psaSrc*<br/>
Ein Zeiger auf eine `SAFEARRAY` in die neue kopiert werden `COleSafeArray` Objekt.

*varSrc*<br/>
Eine vorhandene `VARIANT` oder `COleVariant` Objekt, das in die neue kopiert werden `COleSafeArray` Objekt.

*pSrc*<br/>
Ein Zeiger auf eine `VARIANT` Objekt, das in die neue kopiert werden `COleSafeArray` Objekt.

### <a name="remarks"></a>Hinweise

Alle diese Konstruktoren erstellen neue `COleSafeArray` Objekte. Wenn es keinen Parameter, ein leeres gibt `COleSafeArray` Objekt erstellt (VT_EMPTY). Wenn die `COleSafeArray` wird kopiert, aus einem anderen Array, dessen VARTYPE wird implizit bezeichnet (eine `COleSafeArray`, `COleVariant`, oder `VARIANT`), VARTYPE des Quellarrays beibehalten wird und muss nicht angegeben werden. Wenn die `COleSafeArray` wird kopiert, aus einem anderen Array, dessen VARTYPE ist nicht bekannt (`SAFEARRAY`), VARTYPE muss angegeben werden, der *VtSrc* Parameter.

Bei einem Fehler löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="copy"></a>  COleSafeArray::Copy

Erstellt eine Kopie eines vorhandenen sicheren Arrays.

```
void Copy(LPSAFEARRAY* ppsa);
```

### <a name="parameters"></a>Parameter

*ppsa*<br/>
Zeiger auf einen Speicherort in dem die neue Deskriptor des Arrays zurückgegeben.

### <a name="remarks"></a>Hinweise

Bei einem Fehler löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="create"></a>  COleSafeArray::Create

Reserviert und die Daten für das Array initialisiert.

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
Der Basistyp des Arrays (d. h. VARTYPE jedes Elements des Arrays). VARTYPE ist beschränkt auf eine Teilmenge von Varianten-Typen. Weder die VT_ARRAY noch VT_BYREF-Flag kann festgelegt werden. VT_EMPTY und VT_NULL sind nicht gültig Basistypen für das Array. Alle anderen Typen sind zulässig.

*dwDims*<br/>
Anzahl der Dimensionen im Array. Dies kann geändert werden, nach der Erstellung des Arrays mit [Redim](#redim).

*rgElements*<br/>
Zeiger auf ein Array von der Anzahl der Elemente für jede Dimension im Array.

*rgsabounds*<br/>
Zeiger auf einen Vektor von Grenzen (eine für jede Dimension) für das Array zuweisen.

### <a name="remarks"></a>Hinweise

Diese Funktion wird die aktuelle Arraydaten bei Bedarf gelöscht werden. Bei einem Fehler löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

##  <a name="createonedim"></a>  COleSafeArray::CreateOneDim

Erstellt ein neues eindimensionales `COleSafeArray` Objekt.

```
void CreateOneDim(
    VARTYPE vtSrc,
    DWORD dwElements,
    const void* pvSrcData = NULL,
    long nLBound = 0);
```

### <a name="parameters"></a>Parameter

*vtSrc*<br/>
Der Basistyp des Arrays (d. h. VARTYPE jedes Elements des Arrays).

*dwElements*<br/>
Anzahl der Elemente im Array. Dies kann geändert werden, nach der Erstellung des Arrays mit [ResizeOneDim](#resizeonedim).

*pvSrcData*<br/>
Zeiger auf die Daten in das Array kopiert.

*nLBound*<br/>
Die untere Grenze des Arrays.

### <a name="remarks"></a>Hinweise

Die Funktion zugewiesen, und initialisiert Sie die Daten für das Array, das die angegebenen Daten zu kopieren, wenn der Zeiger *PvSrcData* nicht NULL ist.

Bei einem Fehler löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#28](../../mfc/codesnippet/cpp/colesafearray-class_3.cpp)]

##  <a name="destroy"></a>  COleSafeArray::Destroy

Löscht ein vorhandenes Arraydeskriptor und alle Daten im Array.

```
void Destroy();
```

### <a name="remarks"></a>Hinweise

Wenn Objekte im Array gespeichert sind, wird jedes Objekt freigegeben. Bei einem Fehler löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="destroydata"></a>  COleSafeArray::DestroyData

Löscht alle Daten in ein sicheres Array.

```
void DestroyData();
```

### <a name="remarks"></a>Hinweise

Wenn Objekte im Array gespeichert sind, wird jedes Objekt freigegeben. Bei einem Fehler löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="destroydescriptor"></a>  COleSafeArray::DestroyDescriptor

Zerstört einen Deskriptor eines sicheren Arrays an.

```
void DestroyDescriptor();
```

### <a name="remarks"></a>Hinweise

Bei einem Fehler löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="detach"></a>  COleSafeArray::Detach

Trennt die `VARIANT` Daten aus der `COleSafeArray` Objekt.

```
VARIANT Detach();
```

### <a name="return-value"></a>Rückgabewert

Die zugrunde liegende `VARIANT` Wert in der `COleSafeArray` Objekt.

### <a name="remarks"></a>Hinweise

Die Funktion trennt die Daten in ein sicheres Array von VARTYPE des Objekts auf VT_EMPTY festgelegt. Es ist der Verantwortung des Aufrufers, das Array durch Aufrufen der Windows-Funktion freizugeben [VariantClear](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantclear).

Bei einem Fehler löst die Funktion eine [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [COleSafeArray::PutElement](#putelement).

##  <a name="getbytearray"></a>  COleSafeArray::GetByteArray

Kopiert den Inhalt des sicheren Arrays in ein `CByteArray`.

```
void GetByteArray(CByteArray& bytes);
```

### <a name="parameters"></a>Parameter

*Bytes*<br/>
Ein Verweis auf eine [CByteArray](../../mfc/reference/cbytearray-class.md) Objekt.

##  <a name="getdim"></a>  COleSafeArray::GetDim

Gibt die Anzahl der Dimensionen in der `COleSafeArray` Objekt.

```
DWORD GetDim();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Dimensionen im sicheren Array.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

##  <a name="getelement"></a>  Colesafearray:: GetElement

Ruft ein einzelnes Element des sicheren Arrays ab.

```
void GetElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>Parameter

*rgIndices*<br/>
Zeiger auf ein Array von Indizes für jede Dimension des Arrays.

*"pvData"*<br/>
Zeiger auf den Speicherort für das Element des Arrays.

### <a name="remarks"></a>Hinweise

Diese Funktion ruft automatisch die Windows-Funktionen `SafeArrayLock` und `SafeArrayUnlock` vor und nach dem Abrufen des Elements. Wenn das Datenelement eine Zeichenfolge, Objekt oder Variante ist, kopiert die Funktion das Element in korrekter Weise ab. Der Parameter *"pvData"* sollte zeigen Sie auf eine große genügend Puffer für den das Element enthalten.

Bei einem Fehler löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#29](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]

##  <a name="getelemsize"></a>  COleSafeArray::GetElemSize

Ruft die Größe eines Elements in einem `COleSafeArray` Objekt.

```
DWORD GetElemSize();
```

### <a name="return-value"></a>Rückgabewert

Die Größe der Elemente eines sicheren Arrays in Bytes.

##  <a name="getlbound"></a>  COleSafeArray::GetLBound

Gibt die untere Grenze für eine bestimmte Dimension des eine `COleSafeArray` Objekt.

```
void GetLBound(
    DWORD dwDim,
    long* pLBound);
```

### <a name="parameters"></a>Parameter

*dwDim*<br/>
Die Arraydimension, für das die untere Grenze abgerufen werden soll.

*pLBound*<br/>
Zeiger auf die Position, an die untere Grenze zurück.

### <a name="remarks"></a>Hinweise

Bei einem Fehler löst die Funktion eine [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#30](../../mfc/codesnippet/cpp/colesafearray-class_5.cpp)]

##  <a name="getonedimsize"></a>  COleSafeArray::GetOneDimSize

Gibt die Anzahl von Elementen im eindimensionalen `COleSafeArray` Objekt.

```
DWORD GetOneDimSize();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl von Elementen im eindimensionalen sicheren Array.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [COleSafeArray::CreateOneDim](#createonedim).

##  <a name="getubound"></a>  COleSafeArray::GetUBound

Gibt die obere Grenze für eine bestimmte Dimension eines sicheren Arrays zurück.

```
void GetUBound(
    DWORD dwDim,
    long* pUBound);
```

### <a name="parameters"></a>Parameter

*dwDim*<br/>
Die Arraydimension, für die die obere Grenze abgerufen werden soll.

*pUBound*<br/>
Zeiger auf die Position, an die obere Grenze zurück.

### <a name="remarks"></a>Hinweise

Bei einem Fehler löst die Funktion eine [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#31](../../mfc/codesnippet/cpp/colesafearray-class_6.cpp)]

##  <a name="lock"></a>  COleSafeArray::Lock

Erhöht die Sperrenanzahl von einem Array und einer Stelle ein Zeiger auf die Daten im Arraydeskriptor des Arrays.

```
void Lock();
```

### <a name="remarks"></a>Hinweise

Bei einem Fehler löst eine [COleException](../../mfc/reference/coleexception-class.md).

Der Zeiger in der Deskriptor des Arrays ist gültig bis `Unlock` aufgerufen wird. Aufrufe von `Lock` können geschachtelt werden, eine gleiche Anzahl von Aufrufen an `Unlock` erforderlich sind.

Ein Array kann nicht gelöscht werden, solange sie gesperrt ist.

##  <a name="operator_lpcvariant"></a>  COleSafeArray::operator LPCVARIANT

Rufen Sie diese Umwandlungsoperator für den Zugriff auf die zugrunde liegende `VARIANT` Struktur für diese `COleSafeArray` Objekt.

```
operator LPCVARIANT() const;
```

##  <a name="operator_lpvariant"></a>  COleSafeArray::operator LPVARIANT

Rufen Sie diese Umwandlungsoperator für den Zugriff auf die zugrunde liegende `VARIANT` Struktur für diese `COleSafeArray` Objekt.

```
operator LPVARIANT();
```

### <a name="remarks"></a>Hinweise

Beachten Sie, dass Änderungen des Werts in der `VARIANT` Struktur, die Zugriff auf die von dieser Funktion zurückgegebenen Zeiger ändert sich den Wert dieser `COleSafeArray` Objekt.

##  <a name="operator_eq"></a>  COleSafeArray::operator =

Diese überladenen Zuweisungsoperatoren kopieren Sie den Wert des in dieser `COleSafeArray` Objekt.

```
COleSafeArray& operator=(const COleSafeArray& saSrc);
COleSafeArray& operator=(const VARIANT& varSrc);
  COleSafeArray& operator=(LPCVARIANT pSrc);
COleSafeArray& operator=(const COleVariant& varSrc);
```

### <a name="remarks"></a>Hinweise

Es folgt eine kurze Beschreibung der einzelnen Operatoren:

- **Operator = (** *SaSrc* **)** kopiert eine vorhandene `COleSafeArray` Objekt in dieses Objekt.

- **Operator = (** *VarSrc* **)** kopiert eine vorhandene `VARIANT` oder `COleVariant` Array, in dieses Objekt.

- **Operator = (** *pSrc* **)** Kopien der `VARIANT` Array-Objekt zugegriffen *pSrc* in dieses Objekt.

##  <a name="operator_eq_eq"></a>  COleSafeArray::operator ==

Dieser Operator vergleicht zwei Arrays (`SAFEARRAY`, `VARIANT`, `COleVariant`, oder `COleSafeArray` Arrays) und ungleich NULL, wenn sie gleich; andernfalls 0 sind zurückgibt.

```
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;

BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;

BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;
```

### <a name="remarks"></a>Hinweise

Zwei Arrays sind gleich, wenn sie eine gleiche Anzahl von Dimensionen, gleicher Größe in jeder Dimension und die Elementwerte gleich verfügen.

##  <a name="operator_lt_lt"></a>  COleSafeArray::operator &lt;&lt;

Die `COleSafeArray` einfügen (<<) Operator unterstützt diagnostic Dump-Sicherungen und die Speicherung der ein `COleSafeArray` Objekt in ein Archiv.

```
CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,
    COleSafeArray& saSrc);
```

##  <a name="ptrofindex"></a>  COleSafeArray::PtrOfIndex

Gibt einen Zeiger auf das Element, das durch die Indexwerte angegeben.

```
void PtrOfIndex(
    long* rgIndices,
    void** ppvData);
```

### <a name="parameters"></a>Parameter

*rgIndices*<br/>
Ein Array der Indexwerte, die ein Element des Arrays zu identifizieren. Alle Indizes für das Element müssen angegeben werden.

*ppvData*<br/>
Bei return, ein Zeiger auf das Element identifiziert, die nach den Werten in *RgIndices*.

##  <a name="putelement"></a>  COleSafeArray::PutElement

Weist ein einzelnes Element im Array zu.

```
void PutElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>Parameter

*rgIndices*<br/>
Zeiger auf ein Array von Indizes für jede Dimension des Arrays.

*"pvData"*<br/>
Zeiger auf die Daten, die dem Array zuzuweisen sind. VT_BSTR, "VT_DISPATCH" und "VT_UNKNOWN" Variante-Typen sind Zeiger und erfordern kein anderes Maß an Dereferenzierung.

### <a name="remarks"></a>Hinweise

Diese Funktion ruft automatisch die Windows-Funktionen [SafeArrayLock](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraylock) und [SafeArrayUnlock](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearrayunlock) vor und nach dem Zuweisen des Elements. Ist das Datenelement eine Zeichenfolge, ein Objekt oder eine Variante, kopiert die Funktion es korrekt, und wenn das vorhandene Element eine Zeichenfolge, ein Objekt oder eine Variante ist, wird es korrekt gelöscht.

Beachten Sie, dass Sie mehrere Sperren auf einem Array verwenden können, damit Sie Elemente in einem Array platzieren können, während das Array durch andere Vorgänge gesperrt ist.

Bei einem Fehler löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#32](../../mfc/codesnippet/cpp/colesafearray-class_7.cpp)]

##  <a name="redim"></a>  COleSafeArray::Redim

Ändert die unwichtigste (ganz rechts) Grenze eines sicheren Arrays an.

```
void Redim(SAFEARRAYBOUND* psaboundNew);
```

### <a name="parameters"></a>Parameter

*psaboundNew*<br/>
Zeiger auf ein neues sicheres Array gebunden, Struktur, enthält das neue Array gebunden wird. Nur der unwichtigste Dimension eines Arrays kann geändert werden.

### <a name="remarks"></a>Hinweise

Bei einem Fehler löst die Funktion eine [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="resizeonedim"></a>  COleSafeArray::ResizeOneDim

Ändert die Anzahl der Elemente in einem eindimensionalen `COleSafeArray` Objekt.

```
void ResizeOneDim(DWORD dwElements);
```

### <a name="parameters"></a>Parameter

*dwElements*<br/>
Anzahl von Elementen im eindimensionalen sicheren Array.

### <a name="remarks"></a>Hinweise

Bei einem Fehler löst die Funktion eine [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [COleSafeArray::CreateOneDim](#createonedim).

##  <a name="unaccessdata"></a>  COleSafeArray::UnaccessData

Verringert die Sperre eines Arrays zu zählen und erklärt den Zeiger abgerufen, indem `AccessData`.

```
void UnaccessData();
```

### <a name="remarks"></a>Hinweise

Bei einem Fehler löst die Funktion eine [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [COleSafeArray::AccessData](#accessdata).

##  <a name="unlock"></a>  COleSafeArray::Unlock

Verringert die Sperrenanzahl eines Arrays, sodass es freigegeben oder geändert werden kann.

```
void Unlock();
```

### <a name="remarks"></a>Hinweise

Diese Funktion wird aufgerufen, nach dem Zugriff auf die Daten in einem Array ist. Bei einem Fehler löst eine [COleException](../../mfc/reference/coleexception-class.md).

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleVariant-Klasse](../../mfc/reference/colevariant-class.md)<br/>
[CRecordset-Klasse](../../mfc/reference/crecordset-class.md)<br/>
[CDatabase-Klasse](../../mfc/reference/cdatabase-class.md)<br/>
