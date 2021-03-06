---
title: CMFCFilterChunkValueImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::Clear
- AFXWIN/CMFCFilterChunkValueImpl::CopyChunk
- AFXWIN/CMFCFilterChunkValueImpl::CopyFrom
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkGUID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkPID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkType
- AFXWIN/CMFCFilterChunkValueImpl::GetString
- AFXWIN/CMFCFilterChunkValueImpl::GetValue
- AFXWIN/CMFCFilterChunkValueImpl::GetValueNoAlloc
- AFXWIN/CMFCFilterChunkValueImpl::IsValid
- AFXWIN/CMFCFilterChunkValueImpl::SetBoolValue
- AFXWIN/CMFCFilterChunkValueImpl::SetDwordValue
- AFXWIN/CMFCFilterChunkValueImpl::SetFileTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetInt64Value
- AFXWIN/CMFCFilterChunkValueImpl::SetIntValue
- AFXWIN/CMFCFilterChunkValueImpl::SetLongValue
- AFXWIN/CMFCFilterChunkValueImpl::SetSystemTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetTextValue
- AFXWIN/CMFCFilterChunkValueImpl::SetChunk
helpviewer_keywords:
- CMFCFilterChunkValueImpl [MFC], CMFCFilterChunkValueImpl
- CMFCFilterChunkValueImpl [MFC], Clear
- CMFCFilterChunkValueImpl [MFC], CopyChunk
- CMFCFilterChunkValueImpl [MFC], CopyFrom
- CMFCFilterChunkValueImpl [MFC], GetChunkGUID
- CMFCFilterChunkValueImpl [MFC], GetChunkPID
- CMFCFilterChunkValueImpl [MFC], GetChunkType
- CMFCFilterChunkValueImpl [MFC], GetString
- CMFCFilterChunkValueImpl [MFC], GetValue
- CMFCFilterChunkValueImpl [MFC], GetValueNoAlloc
- CMFCFilterChunkValueImpl [MFC], IsValid
- CMFCFilterChunkValueImpl [MFC], SetBoolValue
- CMFCFilterChunkValueImpl [MFC], SetDwordValue
- CMFCFilterChunkValueImpl [MFC], SetFileTimeValue
- CMFCFilterChunkValueImpl [MFC], SetInt64Value
- CMFCFilterChunkValueImpl [MFC], SetIntValue
- CMFCFilterChunkValueImpl [MFC], SetLongValue
- CMFCFilterChunkValueImpl [MFC], SetSystemTimeValue
- CMFCFilterChunkValueImpl [MFC], SetTextValue
- CMFCFilterChunkValueImpl [MFC], SetChunk
ms.assetid: 3c833f23-5b88-4d08-9e09-ca6a8aec88bf
ms.openlocfilehash: b883d442342dd9fbbd074d9f8fcab76f81ef9864
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62237556"
---
# <a name="cmfcfilterchunkvalueimpl-class"></a>CMFCFilterChunkValueImpl-Klasse

Dies ist eine Klasse, die sowohl Block-Eigenschaft-Wert-Paar-Logik vereinfacht.

## <a name="syntax"></a>Syntax

```
class CMFCFilterChunkValueImpl : public ATL::IFilterChunkValue;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCFilterChunkValueImpl::~CMFCFilterChunkValueImpl](#_dtorcmfcfilterchunkvalueimpl)|Destructs das Objekt an.|
|[CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl](#cmfcfilterchunkvalueimpl)|Erstellt das Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCFilterChunkValueImpl::Clear](#clear)|Löscht die ChunkValue an.|
|[CMFCFilterChunkValueImpl::CopyChunk](#copychunk)|Kopiert dieses Blocks auf eine Struktur, die die Eigenschaften eines Blocks beschreibt.|
|[CMFCFilterChunkValueImpl::CopyFrom](#copyfrom)|Initialisiert diesen Block-Wert aus der andere Wert.|
|[CMFCFilterChunkValueImpl::GetChunkGUID](#getchunkguid)|Ruft den Block GUID ab.|
|[CMFCFilterChunkValueImpl::GetChunkPID](#getchunkpid)|Ruft den Block PID (Eigenschafts-ID) ab.|
|[CMFCFilterChunkValueImpl::GetChunkType](#getchunktype)|Ruft chunk Typ.|
|[CMFCFilterChunkValueImpl::GetString](#getstring)|Ruft den Zeichenfolgenwert ab.|
|[CMFCFilterChunkValueImpl::GetValue](#getvalue)|Ruft den Wert als eine zugeordnete Propvariant ab.|
|[CMFCFilterChunkValueImpl::GetValueNoAlloc](#getvaluenoalloc)|Gibt nicht zugewiesenen (interne Wert) den Wert.|
|[CMFCFilterChunkValueImpl::IsValid](#isvalid)|Überprüft, ob der Wert dieser Eigenschaft gültig ist.|
|[CMFCFilterChunkValueImpl::SetBoolValue](#setboolvalue)|Überladen. Legt die Eigenschaft über Schlüssel zu einem booleschen Wert fest.|
|[CMFCFilterChunkValueImpl::SetDwordValue](#setdwordvalue)|Legt die Eigenschaft durch den Schlüssel für einen DWORD-Wert.|
|[CMFCFilterChunkValueImpl::SetFileTimeValue](#setfiletimevalue)|Legt die Eigenschaft über Schlüssel zu einer Filetime an.|
|[CMFCFilterChunkValueImpl::SetInt64Value](#setint64value)|Legt die Eigenschaft durch Schlüssel Int64-Hashwerte.|
|[CMFCFilterChunkValueImpl::SetIntValue](#setintvalue)|Legt die Eigenschaft durch den Schlüssel für eine ganze Zahl.|
|[CMFCFilterChunkValueImpl::SetLongValue](#setlongvalue)|Legt die Eigenschaft durch die Taste, um einen Long-Wert.|
|[CMFCFilterChunkValueImpl::SetSystemTimeValue](#setsystemtimevalue)|Legt die Eigenschaft durch Schlüssel in einem SystemTime.|
|[CMFCFilterChunkValueImpl::SetTextValue](#settextvalue)|Legt die Eigenschaft durch die Taste, um eine Unicode-Zeichenfolge.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCFilterChunkValueImpl::SetChunk](#setchunk)|Eine Hilfsfunktion, die das Segment der allgemeinen Eigenschaften festlegt.|

## <a name="remarks"></a>Hinweise

Um zu verwenden, erstellen Sie einfach eine CMFCFilterChunkValueImpl-Klasse, von der richtigen

Beispiel:

CMFCFilterChunkValueImpl-Segment;

hr = chunk.SetBoolValue(PKEY_IsAttachment, true);

oder

hr = chunk.SetFileTimeValue(PKEY_ItemDate, ftLastModified);

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ATL::IFilterChunkValue`

[CMFCFilterChunkValueImpl](../../mfc/reference/cmfcfilterchunkvalueimpl-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="clear"></a>  CMFCFilterChunkValueImpl::Clear

Löscht die ChunkValue an.

```
void Clear();
```

### <a name="remarks"></a>Hinweise

##  <a name="cmfcfilterchunkvalueimpl"></a>  CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl

Erstellt das Objekt.

```
CMFCFilterChunkValueImpl();
```

### <a name="remarks"></a>Hinweise

##  <a name="_dtorcmfcfilterchunkvalueimpl"></a>  CMFCFilterChunkValueImpl:: ~ CMFCFilterChunkValueImpl

Destructs das Objekt an.

```
virtual ~CMFCFilterChunkValueImpl();
```

### <a name="remarks"></a>Hinweise

##  <a name="copychunk"></a>  CMFCFilterChunkValueImpl::CopyChunk

Kopiert dieses Blocks auf eine Struktur, die die Eigenschaften eines Blocks beschreibt.

```
HRESULT CopyChunk(STAT_CHUNK* pStatChunk);
```

### <a name="parameters"></a>Parameter

*pStatChunk*<br/>
Ein Zeiger auf den Zielwert, beschreibt die Merkmale des Blocks.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein Fehlercode.

### <a name="remarks"></a>Hinweise

##  <a name="copyfrom"></a>  CMFCFilterChunkValueImpl::CopyFrom

Initialisiert diesen Block-Wert aus der andere Wert.

```
void CopyFrom (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>Parameter

*pValue*<br/>
Gibt den Quellwert zum Kopieren aus.

### <a name="remarks"></a>Hinweise

##  <a name="getchunkguid"></a>  CMFCFilterChunkValueImpl::GetChunkGUID

Ruft den Block GUID ab.

```
REFGUID GetChunkGUID() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf eine GUID zum Identifizieren des Blocks.

### <a name="remarks"></a>Hinweise

##  <a name="getchunkpid"></a>  CMFCFilterChunkValueImpl::GetChunkPID

Ruft den Block PID (Eigenschafts-ID) ab.

```
DWORD GetChunkPID() const;
```

### <a name="return-value"></a>Rückgabewert

Eine DWORD-Wert, der mit der Eigenschafts-ID an.

### <a name="remarks"></a>Hinweise

##  <a name="getchunktype"></a>  CMFCFilterChunkValueImpl::GetChunkType

Ruft den Block-Typ ab.

```
CHUNKSTATE GetChunkType() const;
```

### <a name="return-value"></a>Rückgabewert

Ein CHUNKSTATE aufgezählt-Wert, der angibt, ob das aktuelle Segment einer Text-Type-Eigenschaft oder ein Werttyp-Eigenschaft ist.

### <a name="remarks"></a>Hinweise

##  <a name="getstring"></a>  CMFCFilterChunkValueImpl::GetString

Ruft den Zeichenfolgenwert ab.

```
CString &GetString();
```

### <a name="return-value"></a>Rückgabewert

Eine Zeichenfolge mit der Block-Wert.

### <a name="remarks"></a>Hinweise

##  <a name="getvalue"></a>  CMFCFilterChunkValueImpl::GetValue

Ruft den Wert als eine zugeordnete Propvariant ab.

```
HRESULT GetValue(PROPVARIANT** ppPropVariant);
```

### <a name="parameters"></a>Parameter

*ppPropVariant*<br/>
Wenn die Funktion zurückgibt, enthält dieser Parameter die Block-Wert.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn PROPVARIANT erfolgreich reserviert wurde und der Block-Wert erfolgreich, um kopiert wurde *PpPropVariant*; andernfalls ein Fehlercode.

### <a name="remarks"></a>Hinweise

##  <a name="getvaluenoalloc"></a>  CMFCFilterChunkValueImpl::GetValueNoAlloc

Gibt den Wert des nicht zugewiesenen (interne Wert).

```
PROPVARIANT GetValueNoAlloc ();
```

### <a name="return-value"></a>Rückgabewert

Der aktuelle Block-Wert zurückgegeben.

### <a name="remarks"></a>Hinweise

##  <a name="isvalid"></a>  CMFCFilterChunkValueImpl::IsValid

Überprüft, ob der Wert dieser Eigenschaft gültig ist.

```
BOOL IsValid() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn der aktuelle Block-Wert gültig ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

##  <a name="setboolvalue"></a>  CMFCFilterChunkValueImpl::SetBoolValue

Überladen. Legt die Eigenschaft über Schlüssel zu einem booleschen Wert fest.

```
HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,
    BOOL bVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);

HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,
    VARIANT_BOOL bVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parameter

*pkey*<br/>
Gibt einen Eigenschaftsschlüssel.

*bVal*<br/>
Gibt den Wert "Block" festgelegt.

*chunkType*<br/>
Flags geben an, ob dieses Segment einen Text-Typ oder ein Werttyp-Eigenschaft enthält. Flagwerte werden aus der CHUNKSTATE-Enumeration entnommen.

*locale*<br/>
Die Sprache und der untersprachen ein Textsegment zugeordnet werden soll. Block-Gebietsschema dokumentindexer dient, führen Sie die richtige wörtertrennung Text. Wenn das Segment weder ein Werttyp mit dem Datentyp VT_LPWSTR: VT_LPSTR oder VT_BSTR als auch vom Texttyp ist, wird dieses Feld ignoriert.

*cwcLenSource*<br/>
Die Länge in Zeichen des Quelltexts aus dem der aktuelle Datenblock abgeleitet wurde. Ein Wert von NULL gibt an, Zeichen für Zeichen-Entsprechung zwischen den Quelltext und den abgeleiteten Text. Ein Wert ungleich NULL bedeutet, dass keine solche direkte Entsprechung vorhanden ist.

*cwcStartSource*<br/>
Der Offset, von dem aus der Quelltext für einen abgeleiteten Block in der Quelle Block startet.

*chunkBreakType*<br/>
Der Typ der Pause, die den vorherigen Block von aktuellen Block trennt. Werte reichen von der CHUNK_BREAKTYPE-Enumeration.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein Fehlercode.

### <a name="remarks"></a>Hinweise

##  <a name="setchunk"></a>  CMFCFilterChunkValueImpl::SetChunk

Eine Hilfsfunktion, die das Segment der allgemeinen Eigenschaften festlegt.

```
HRESULT SetChunk(
    REFPROPERTYKEY pkey,
    CHUNKSTATE chunkType=CHUNK_VALUE,
    LCID locale=0,
    DWORD cwcLenSource=0,
    DWORD cwcStartSource=0,
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parameter

*pkey*<br/>
Gibt einen Eigenschaftsschlüssel.

*chunkType*<br/>
Flags geben an, ob dieses Segment einen Text-Typ oder ein Werttyp-Eigenschaft enthält. Flagwerte werden aus der CHUNKSTATE-Enumeration entnommen.

*locale*<br/>
Die Sprache und der untersprachen ein Textsegment zugeordnet werden soll. Block-Gebietsschema dokumentindexer dient, führen Sie die richtige wörtertrennung Text. Wenn das Segment weder ein Werttyp mit dem Datentyp VT_LPWSTR: VT_LPSTR oder VT_BSTR als auch vom Texttyp ist, wird dieses Feld ignoriert.

*cwcLenSource*<br/>
Die Länge in Zeichen des Quelltexts aus dem der aktuelle Datenblock abgeleitet wurde. Ein Wert von NULL gibt an, Zeichen für Zeichen-Entsprechung zwischen den Quelltext und den abgeleiteten Text. Ein Wert ungleich NULL bedeutet, dass keine solche direkte Entsprechung vorhanden ist.

*cwcStartSource*<br/>
Der Offset, von dem aus der Quelltext für einen abgeleiteten Block in der Quelle Block startet.

*chunkBreakType*<br/>
Der Typ der Pause, die den vorherigen Block von aktuellen Block trennt. Werte reichen von der CHUNK_BREAKTYPE-Enumeration.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls Fehlercode.

### <a name="remarks"></a>Hinweise

##  <a name="setdwordvalue"></a>  CMFCFilterChunkValueImpl::SetDwordValue

Legen Sie die Eigenschaft durch den Schlüssel für einen DWORD-Wert.

```
HRESULT SetDwordValue(
    REFPROPERTYKEY pkey,
    DWORD dwVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parameter

*pkey*<br/>
Gibt einen Eigenschaftsschlüssel.

*dwVal*<br/>
Gibt den Wert "Block" festgelegt.

*chunkType*<br/>
Flags geben an, ob dieses Segment einen Text-Typ oder ein Werttyp-Eigenschaft enthält. Flagwerte werden aus der CHUNKSTATE-Enumeration entnommen.

*locale*<br/>
Die Sprache und der untersprachen ein Textsegment zugeordnet werden soll. Block-Gebietsschema dokumentindexer dient, führen Sie die richtige wörtertrennung Text. Wenn das Segment weder ein Werttyp mit dem Datentyp VT_LPWSTR: VT_LPSTR oder VT_BSTR als auch vom Texttyp ist, wird dieses Feld ignoriert.

*cwcLenSource*<br/>
Die Länge in Zeichen des Quelltexts aus dem der aktuelle Datenblock abgeleitet wurde. Ein Wert von NULL gibt an, Zeichen für Zeichen-Entsprechung zwischen den Quelltext und den abgeleiteten Text. Ein Wert ungleich NULL bedeutet, dass keine solche direkte Entsprechung vorhanden ist.

*cwcStartSource*<br/>
Der Offset, von dem aus der Quelltext für einen abgeleiteten Block in der Quelle Block startet.

*chunkBreakType*<br/>
Der Typ der Pause, die den vorherigen Block von aktuellen Block trennt. Werte reichen von der CHUNK_BREAKTYPE-Enumeration.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein Fehlercode.

### <a name="remarks"></a>Hinweise

##  <a name="setfiletimevalue"></a>  CMFCFilterChunkValueImpl::SetFileTimeValue

Legen Sie die Eigenschaft über Schlüssel zu einer Filetime an.

```
HRESULT SetFileTimeValue(
    REFPROPERTYKEY pkey,
    FILETIME dtVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parameter

*pkey*<br/>
Gibt einen Eigenschaftsschlüssel.

*dtVal*<br/>
Gibt den Wert "Block" festgelegt.

*chunkType*<br/>
Flags geben an, ob dieses Segment einen Text-Typ oder ein Werttyp-Eigenschaft enthält. Flagwerte werden aus der CHUNKSTATE-Enumeration entnommen.

*locale*<br/>
Die Sprache und der untersprachen ein Textsegment zugeordnet werden soll. Block-Gebietsschema dokumentindexer dient, führen Sie die richtige wörtertrennung Text. Wenn das Segment weder ein Werttyp mit dem Datentyp VT_LPWSTR: VT_LPSTR oder VT_BSTR als auch vom Texttyp ist, wird dieses Feld ignoriert.

*cwcLenSource*<br/>
Die Länge in Zeichen des Quelltexts aus dem der aktuelle Datenblock abgeleitet wurde. Ein Wert von NULL gibt an, Zeichen für Zeichen-Entsprechung zwischen den Quelltext und den abgeleiteten Text. Ein Wert ungleich NULL bedeutet, dass keine solche direkte Entsprechung vorhanden ist.

*cwcStartSource*<br/>
Der Offset, von dem aus der Quelltext für einen abgeleiteten Block in der Quelle Block startet.

*chunkBreakType*<br/>
Der Typ der Pause, die den vorherigen Block von aktuellen Block trennt. Werte reichen von der CHUNK_BREAKTYPE-Enumeration.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein Fehlercode.

### <a name="remarks"></a>Hinweise

##  <a name="setint64value"></a>  CMFCFilterChunkValueImpl::SetInt64Value

Festlegen Sie die Eigenschaft durch Schlüssel ein Int64.

```
HRESULT SetInt64Value(
    REFPROPERTYKEY pkey,
    __int64 nVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parameter

*pkey*<br/>
Gibt einen Eigenschaftsschlüssel.

*nVal*<br/>
Gibt den Wert "Block" festgelegt.

*chunkType*<br/>
Flags geben an, ob dieses Segment einen Text-Typ oder ein Werttyp-Eigenschaft enthält. Flagwerte werden aus der CHUNKSTATE-Enumeration entnommen.

*locale*<br/>
Die Sprache und der untersprachen ein Textsegment zugeordnet werden soll. Block-Gebietsschema dokumentindexer dient, führen Sie die richtige wörtertrennung Text. Wenn das Segment weder ein Werttyp mit dem Datentyp VT_LPWSTR: VT_LPSTR oder VT_BSTR als auch vom Texttyp ist, wird dieses Feld ignoriert.

*cwcLenSource*<br/>
Die Länge in Zeichen des Quelltexts aus dem der aktuelle Datenblock abgeleitet wurde. Ein Wert von NULL gibt an, Zeichen für Zeichen-Entsprechung zwischen den Quelltext und den abgeleiteten Text. Ein Wert ungleich NULL bedeutet, dass keine solche direkte Entsprechung vorhanden ist.

*cwcStartSource*<br/>
Der Offset, von dem aus der Quelltext für einen abgeleiteten Block in der Quelle Block startet.

*chunkBreakType*<br/>
Der Typ der Pause, die den vorherigen Block von aktuellen Block trennt. Werte reichen von der CHUNK_BREAKTYPE-Enumeration.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein Fehlercode.

### <a name="remarks"></a>Hinweise

##  <a name="setintvalue"></a>  CMFCFilterChunkValueImpl::SetIntValue

Legen Sie die Eigenschaft durch den Schlüssel für eine ganze Zahl.

```
HRESULT SetIntValue(
    REFPROPERTYKEY pkey,
    int nVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parameter

*pkey*<br/>
Gibt einen Eigenschaftsschlüssel.

*nVal*<br/>
Gibt den Wert "Block" festgelegt.

*chunkType*<br/>
Flags geben an, ob dieses Segment einen Text-Typ oder ein Werttyp-Eigenschaft enthält. Flagwerte werden aus der CHUNKSTATE-Enumeration entnommen.

*locale*<br/>
Die Sprache und der untersprachen ein Textsegment zugeordnet werden soll. Block-Gebietsschema dokumentindexer dient, führen Sie die richtige wörtertrennung Text. Wenn das Segment weder ein Werttyp mit dem Datentyp VT_LPWSTR: VT_LPSTR oder VT_BSTR als auch vom Texttyp ist, wird dieses Feld ignoriert.

*cwcLenSource*<br/>
Die Länge in Zeichen des Quelltexts aus dem der aktuelle Datenblock abgeleitet wurde. Ein Wert von NULL gibt an, Zeichen für Zeichen-Entsprechung zwischen den Quelltext und den abgeleiteten Text. Ein Wert ungleich NULL bedeutet, dass keine solche direkte Entsprechung vorhanden ist.

*cwcStartSource*<br/>
Der Offset, von dem aus der Quelltext für einen abgeleiteten Block in der Quelle Block startet.

*chunkBreakType*<br/>
Der Typ der Pause, die den vorherigen Block von aktuellen Block trennt. Werte reichen von der CHUNK_BREAKTYPE-Enumeration.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein Fehlercode.

### <a name="remarks"></a>Hinweise

##  <a name="setlongvalue"></a>  CMFCFilterChunkValueImpl::SetLongValue

Legen Sie die Eigenschaft, durch die Taste, um einen Long-Wert.

```
HRESULT SetLongValue(
    REFPROPERTYKEY pkey,
    long lVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parameter

*pkey*<br/>
Gibt einen Eigenschaftsschlüssel.

*lVal*<br/>
Gibt den Wert "Block" festgelegt.

*chunkType*<br/>
Flags geben an, ob dieses Segment einen Text-Typ oder ein Werttyp-Eigenschaft enthält. Flagwerte werden aus der CHUNKSTATE-Enumeration entnommen.

*locale*<br/>
Die Sprache und der untersprachen ein Textsegment zugeordnet werden soll. Block-Gebietsschema dokumentindexer dient, führen Sie die richtige wörtertrennung Text. Wenn das Segment weder ein Werttyp mit dem Datentyp VT_LPWSTR: VT_LPSTR oder VT_BSTR als auch vom Texttyp ist, wird dieses Feld ignoriert.

*cwcLenSource*<br/>
Die Länge in Zeichen des Quelltexts aus dem der aktuelle Datenblock abgeleitet wurde. Ein Wert von NULL gibt an, Zeichen für Zeichen-Entsprechung zwischen den Quelltext und den abgeleiteten Text. Ein Wert ungleich NULL bedeutet, dass keine solche direkte Entsprechung vorhanden ist.

*cwcStartSource*<br/>
Der Offset, von dem aus der Quelltext für einen abgeleiteten Block in der Quelle Block startet.

*chunkBreakType*<br/>
Der Typ der Pause, die den vorherigen Block von aktuellen Block trennt. Werte reichen von der CHUNK_BREAKTYPE-Enumeration.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein Fehlercode.

### <a name="remarks"></a>Hinweise

##  <a name="setsystemtimevalue"></a>  CMFCFilterChunkValueImpl::SetSystemTimeValue

Legt die Eigenschaft durch Schlüssel in einem SystemTime.

```
HRESULT SetSystemTimeValue(
    REFPROPERTYKEY pkey,
    const SYSTEMTIME& systemTime,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale=0,
    DWORD cwcLenSource=0,
    DWORD cwcStartSource=0,
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parameter

*pkey*<br/>
Gibt einen Eigenschaftsschlüssel.

*systemTime*<br/>
Gibt den Wert "Block" festgelegt.

*chunkType*<br/>
Flags geben an, ob dieses Segment einen Text-Typ oder ein Werttyp-Eigenschaft enthält. Flagwerte werden aus der CHUNKSTATE-Enumeration entnommen.

*locale*<br/>
Die Sprache und der untersprachen ein Textsegment zugeordnet werden soll. Block-Gebietsschema dokumentindexer dient, führen Sie die richtige wörtertrennung Text. Wenn das Segment weder ein Werttyp mit dem Datentyp VT_LPWSTR: VT_LPSTR oder VT_BSTR als auch vom Texttyp ist, wird dieses Feld ignoriert.

*cwcLenSource*<br/>
Die Länge in Zeichen des Quelltexts aus dem der aktuelle Datenblock abgeleitet wurde. Ein Wert von NULL gibt an, Zeichen für Zeichen-Entsprechung zwischen den Quelltext und den abgeleiteten Text. Ein Wert ungleich NULL bedeutet, dass keine solche direkte Entsprechung vorhanden ist.

*cwcStartSource*<br/>
Der Offset, von dem aus der Quelltext für einen abgeleiteten Block in der Quelle Block startet.

*chunkBreakType*<br/>
Der Typ der Pause, die den vorherigen Block von aktuellen Block trennt. Werte reichen von der CHUNK_BREAKTYPE-Enumeration.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein Fehlercode.

### <a name="remarks"></a>Hinweise

##  <a name="settextvalue"></a>  CMFCFilterChunkValueImpl::SetTextValue

Legt die Eigenschaft durch die Taste, um eine Unicode-Zeichenfolge.

```
HRESULT SetTextValue(
    REFPROPERTYKEY pkey,
    LPCTSTR pszValue,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parameter

*pkey*<br/>
Gibt einen Eigenschaftsschlüssel.

*pszValue*<br/>
Gibt den Wert "Block" festgelegt.

*chunkType*<br/>
Flags geben an, ob dieses Segment einen Text-Typ oder ein Werttyp-Eigenschaft enthält. Flagwerte werden aus der CHUNKSTATE-Enumeration entnommen.

*locale*<br/>
Die Sprache und der untersprachen ein Textsegment zugeordnet werden soll. Block-Gebietsschema dokumentindexer dient, führen Sie die richtige wörtertrennung Text. Wenn das Segment weder ein Werttyp mit dem Datentyp VT_LPWSTR: VT_LPSTR oder VT_BSTR als auch vom Texttyp ist, wird dieses Feld ignoriert.

*cwcLenSource*<br/>
Die Länge in Zeichen des Quelltexts aus dem der aktuelle Datenblock abgeleitet wurde. Ein Wert von NULL gibt an, Zeichen für Zeichen-Entsprechung zwischen den Quelltext und den abgeleiteten Text. Ein Wert ungleich NULL bedeutet, dass keine solche direkte Entsprechung vorhanden ist.

*cwcStartSource*<br/>
Der Offset, von dem aus der Quelltext für einen abgeleiteten Block in der Quelle Block startet.

*chunkBreakType*<br/>
Der Typ der Pause, die den vorherigen Block von aktuellen Block trennt. Werte reichen von der CHUNK_BREAKTYPE-Enumeration.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein Fehlercode.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
