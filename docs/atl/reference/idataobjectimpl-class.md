---
title: Idataobjectimpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl::DAdvise
- ATLCTL/ATL::IDataObjectImpl::DUnadvise
- ATLCTL/ATL::IDataObjectImpl::EnumDAdvise
- ATLCTL/ATL::IDataObjectImpl::EnumFormatEtc
- ATLCTL/ATL::IDataObjectImpl::FireDataChange
- ATLCTL/ATL::IDataObjectImpl::GetCanonicalFormatEtc
- ATLCTL/ATL::IDataObjectImpl::GetData
- ATLCTL/ATL::IDataObjectImpl::GetDataHere
- ATLCTL/ATL::IDataObjectImpl::QueryGetData
- ATLCTL/ATL::IDataObjectImpl::SetData
helpviewer_keywords:
- data transfer [C++]
- data transfer [C++], Uniform Data Transfer
- IDataObjectImpl class
- IDataObject, ATL implementation
ms.assetid: b680f0f7-7795-40a1-a0f6-f48768201c89
ms.openlocfilehash: 80b5dfacd5f0c8b0deb8455a59d3f71b73a35ba0
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70739558"
---
# <a name="idataobjectimpl-class"></a>Idataobjectimpl-Klasse

Diese Klasse stellt Methoden zum unterstützen von Uniform Data Transfer und zum Verwalten von Verbindungen bereit.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class IDataObjectImpl
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die von `IDataObjectImpl`abgeleitete Klasse.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IDataObjectImpl::DAdvise](#dadvise)|Stellt eine Verbindung zwischen dem Datenobjekt und einer Benachrichtigungs Senke her. Dies ermöglicht es der Anmelde Senke, Benachrichtigungen über Änderungen im Objekt zu empfangen.|
|[IDataObjectImpl::DUnadvise](#dunadvise)|Beendet eine Verbindung, die zuvor `DAdvise`durch hergestellt wurde.|
|[IDataObjectImpl::EnumDAdvise](#enumdadvise)|Erstellt einen Enumerator zum Durchlaufen der aktuellen Beratungs Verbindungen.|
|[IDataObjectImpl::EnumFormatEtc](#enumformatetc)|Erstellt einen Enumerator zum Durchlaufen der `FORMATETC` vom Datenobjekt unterstützten Strukturen. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IDataObjectImpl::FireDataChange](#firedatachange)|Sendet eine Änderungs Benachrichtigung an jede Benachrichtigungs Senke zurück.|
|[IDataObjectImpl::GetCanonicalFormatEtc](#getcanonicalformatetc)|Ruft eine logisch äquivalente `FORMATETC` -Struktur zu einer komplexeren-Struktur ab. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IDataObjectImpl::GetData](#getdata)|Überträgt Daten vom Datenobjekt an den Client. Die Daten werden in einer `FORMATETC` Struktur beschrieben und durch eine `STGMEDIUM` -Struktur übertragen.|
|[IDataObjectImpl::GetDataHere](#getdatahere)|Ähnelt, mit der Ausnahme, dass der Client `STGMEDIUM` die-Struktur zuordnen muss. `GetData` Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IDataObjectImpl::QueryGetData](#querygetdata)|Bestimmt, ob das Datenobjekt eine bestimmte `FORMATETC` Struktur zum Übertragen von Daten unterstützt. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IDataObjectImpl::SetData](#setdata)|Überträgt Daten vom Client an das Datenobjekt. Die ATL-Implementierung gibt E_NOTIMPL zurück.|

## <a name="remarks"></a>Hinweise

Die [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) -Schnittstelle stellt Methoden zur Unterstützung von Uniform Data Transfer bereit. `IDataObject`verwendet die Standardformat Strukturen [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) und [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) , um Daten abzurufen und zu speichern.

`IDataObject`verwaltet auch Verbindungen, um senken zum Verarbeiten von Daten Änderungs Benachrichtigungen zu empfehlen. Damit der Client Daten Änderungs Benachrichtigungen vom Datenobjekt empfangen kann, muss der Client die [IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink) -Schnittstelle für ein Objekt implementieren, das als "Empfehlung-Senke" bezeichnet wird. Wenn der Client dann aufruft `IDataObject::DAdvise`, wird eine Verbindung zwischen dem Datenobjekt und der beratungssenke hergestellt.

Die `IDataObjectImpl` -Klasse stellt eine Standard `IDataObject` Implementierung von `IUnknown` bereit und implementiert durch das Senden von Informationen an das dumpgerät in Debugbuilds.

**Verwandte Artikel** [ATL-Tutorial](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IDataObject`

`IDataObjectImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="dadvise"></a>Idataobjectimpl::D-Empfehlung

Stellt eine Verbindung zwischen dem Datenobjekt und einer Benachrichtigungs Senke her.

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Hinweise

Dies ermöglicht es der Anmelde Senke, Benachrichtigungen über Änderungen im Objekt zu empfangen.

Um die Verbindung zu beenden, wenden Sie [dunrat](#dunadvise)an.

Weitere Informationen finden Sie unter [IDataObject::D-Empfehlung](/windows/win32/api/objidl/nf-objidl-idataobject-dadvise) im Windows SDK.

##  <a name="dunadvise"></a>Idataobjectimpl::D nicht empfohlen

Beendet eine zuvor durch [dempfehlung](#dadvise)festgelegte Verbindung.

```
HRESULT DUnadvise(DWORD dwConnection);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IDataObject::D unempfehlung](/windows/win32/api/objidl/nf-objidl-idataobject-dunadvise) im Windows SDK.

##  <a name="enumdadvise"></a>Idataobjectimpl:: enumdrat

Erstellt einen Enumerator zum Durchlaufen der aktuellen Beratungs Verbindungen.

```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IDataObject:: enumdrat](/windows/win32/api/objidl/nf-objidl-idataobject-enumdadvise) im Windows SDK.

##  <a name="enumformatetc"></a>Idataobjectimpl:: EnumFormatEtc

Erstellt einen Enumerator zum Durchlaufen der `FORMATETC` vom Datenobjekt unterstützten Strukturen.

```
HRESULT EnumFormatEtc(
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie im Windows SDK unter [IDataObject:: EnumFormatEtc](/windows/win32/api/objidl/nf-objidl-idataobject-enumformatetc) .

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

##  <a name="firedatachange"></a>Idataobjectimpl:: firedatachange

Sendet eine Änderungs Benachrichtigung zurück an jede Benachrichtigungs Senke, die gerade verwaltet wird.

```
HRESULT FireDataChange();
```

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

##  <a name="getcanonicalformatetc"></a>Idataobjectimpl:: GetCanonicalFormatEtc

Ruft eine logisch äquivalente `FORMATETC` -Struktur zu einer komplexeren-Struktur ab.

```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie im Windows SDK unter [IDataObject:: getcanonicalformatusw](/windows/win32/api/objidl/nf-objidl-idataobject-getcanonicalformatetc) .

##  <a name="getdata"></a>Idataobjectimpl:: GetData

Überträgt Daten vom Datenobjekt an den Client.

```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```

### <a name="remarks"></a>Hinweise

Der *pformatetcin* -Parameter muss den Speicher mitteltyp TYMED_MFPICT angeben.

Weitere Informationen finden Sie im Windows SDK unter [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) .

##  <a name="getdatahere"></a>Idataobjectimpl:: GetDataHere

Ähnelt, mit der Ausnahme, dass der Client `STGMEDIUM` die-Struktur zuordnen muss. `GetData`

```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie im Windows SDK unter [IDataObject:: GetDataHere](/windows/win32/api/objidl/nf-objidl-idataobject-getdatahere) .

##  <a name="querygetdata"></a>Idataobjectimpl:: QueryGetData

Bestimmt, ob das Datenobjekt eine bestimmte `FORMATETC` Struktur zum Übertragen von Daten unterstützt.

```
HRESULT QueryGetData(FORMATETC* pformatetc);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie im Windows SDK unter [IDataObject:: QueryGetData](/windows/win32/api/objidl/nf-objidl-idataobject-querygetdata) .

##  <a name="setdata"></a>Idataobjectimpl:: SetData

Überträgt Daten vom Client an das Datenobjekt.

```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie im Windows SDK unter [IDataObject:: SetData](/windows/win32/api/objidl/nf-objidl-idataobject-setdata) .

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)
