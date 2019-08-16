---
title: IDispEventImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IDispEventImpl
- ATLCOM/ATL::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::GetFuncInfoFromId
- ATLCOM/ATL::IDispEventImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventImpl::GetUserDefinedType
helpviewer_keywords:
- IDispEventImpl class
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
ms.openlocfilehash: e82a397b6d2abb66f773908c72a287c979e5ae1d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495934"
---
# <a name="idispeventimpl-class"></a>IDispEventImpl-Klasse

Diese Klasse stellt Implementierungen der `IDispatch` -Methoden bereit.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template <UINT nID, class T,
    const IID* pdiid = &IID_NULL,
    const GUID* plibid = &GUID_NULL,
    WORD wMajor = 0,
    WORD wMinor = 0,
    class tihclass = CcomTypeInfoHolder>
class ATL_NO_VTABLE IDispEventImpl : public IDispEventSimpleImpl<nID, T, pdiid>
```

#### <a name="parameters"></a>Parameter

*nID*<br/>
Ein eindeutiger Bezeichner für das Quell Objekt. Wenn `IDispEventImpl` die Basisklasse für ein zusammengesetztes Steuerelement ist, verwenden Sie die Ressourcen-ID des gewünschten enthaltenen Steuer Elements für diesen Parameter. Verwenden Sie in anderen Fällen eine beliebige positive ganze Zahl.

*T*<br/>
Die Klasse des Benutzers, die von `IDispEventImpl`abgeleitet ist.

*pdiid*<br/>
Der Zeiger auf die IID der Ereignis dispinterface, die von dieser Klasse implementiert wird. Diese Schnittstelle muss in der Typbibliothek definiert werden, die von " *plibid*", " *wMajor*" und " *wMinor*" angegeben wird.

*plibid*<br/>
Ein Zeiger auf die Typbibliothek, die die Dispatchschnittstelle definiert, auf die von *pdiid*verwiesen wird. Wenn **& GUID_NULL**, wird die Typbibliothek aus dem Objekt geladen, das die Ereignisse aufführt.

*wMajor*<br/>
Die Hauptversion der Typbibliothek Der Standardwert ist 0.

*wMinor*<br/>
Die Nebenversion der Typbibliothek Der Standardwert ist 0.

*tihclass*<br/>
Die Klasse, mit der die Typinformationen für *T*verwaltet werden. Der Standardwert ist eine Klasse vom Typ `CComTypeInfoHolder`. Sie können diesen Vorlagen Parameter jedoch außer Kraft setzen, indem Sie eine Klasse von einem anderen `CComTypeInfoHolder`Typ als bereitstellen.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|[IDispEventImpl:: _tihclass](../../atl/reference/idispeventimpl-class.md)|Die Klasse, die verwendet wird, um die Typinformationen zu verwalten. Standardmäßig `CComTypeInfoHolder`lautet der Wert.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[IDispEventImpl::IDispEventImpl](#idispeventimpl)|Der Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IDispEventImpl::GetFuncInfoFromId](#getfuncinfofromid)|Sucht den Funktions Index für den angegebenen Dispatchbezeichner.|
|[IDispEventImpl::GetIDsOfNames](#getidsofnames)|Ordnet einem entsprechenden Satz von ganzzahligen DispIds einen einzelnen Member und einen optionalen Satz von Argument Namen zu.|
|[IDispEventImpl::GetTypeInfo](#gettypeinfo)|Ruft die Typinformationen für ein Objekt ab.|
|[IDispEventImpl::GetTypeInfoCount](#gettypeinfocount)|Ruft die Anzahl der Schnittstellen für Typinformationen ab.|
|[IDispEventImpl::GetUserDefinedType](#getuserdefinedtype)|Ruft den Basistyp eines benutzerdefinierten Typs ab.|

## <a name="remarks"></a>Hinweise

`IDispEventImpl`bietet eine Möglichkeit, eine Ereignis-dispinterface zu implementieren, ohne dass Sie Implementierungs Code für jede Methode bzw. jedes Ereignis an dieser Schnittstelle bereitstellen müssen. `IDispEventImpl`stellt Implementierungen der `IDispatch` -Methoden bereit. Sie müssen nur Implementierungen für die Ereignisse bereitstellen, die Sie behandeln möchten.

`IDispEventImpl`arbeitet in Verbindung mit der Ereignis senkenzuordnung in der-Klasse, um Ereignisse an die entsprechende Handlerfunktion weiterzuleiten. So verwenden Sie diese Klasse:

Fügen Sie ein [SINK_ENTRY](composite-control-macros.md#sink_entry) -oder [SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex) -Makro der Ereignis senkenzuordnung für jedes Ereignis für jedes Objekt hinzu, das Sie verarbeiten möchten. Wenn Sie `IDispEventImpl` als Basisklasse für ein zusammengesetztes Steuerelement verwenden, können Sie [atladvisesinkmap](connection-point-global-functions.md#atladvisesinkmap) zum Einrichten und Unterbrechen der Verbindung mit den Ereignis Quellen für alle Einträge in der Ereignis Senke-Zuordnung verwenden. In anderen Fällen oder bei größerer Kontrolle, wenden Sie [dispeventempfehlung](idispeventsimpleimpl-class.md#dispeventadvise) an, um die Verbindung zwischen dem Quell Objekt und der Basisklasse herzustellen. Bitten Sie [dispeventunempfehlung](idispeventsimpleimpl-class.md#dispeventunadvise) , die Verbindung zu unterbrechen.

Sie müssen für jedes `IDispEventImpl` Objekt, für das Sie Ereignisse behandeln müssen, von (mit einem eindeutigen Wert für *NID*) abgeleitet werden. Sie können die Basisklasse wieder verwenden, indem Sie die Verwendung eines Quell Objekts ablehnen und dann ein anderes Quell Objekt verwenden, aber die maximale Anzahl von Quell Objekten, die von einem einzelnen Objekt gleichzeitig verarbeitet werden können, ist durch `IDispEventImpl` die Anzahl der Basisklassen beschränkt.

`IDispEventImpl`bietet die gleiche Funktionalität wie [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md), mit dem Unterschied, dass Sie Typinformationen über die Schnittstelle aus einer Typbibliothek abruft, anstatt Sie als Zeiger auf eine [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) -Struktur bereitzustellen. Verwenden `IDispEventSimpleImpl` Sie, wenn Sie nicht über eine Typbibliothek verfügen, die die Ereignis Schnittstelle beschreibt, oder möchten Sie den Aufwand vermeiden, der mit der Verwendung der Typbibliothek verknüpft ist.

> [!NOTE]
> `IDispEventImpl`und `IDispEventSimpleImpl` stellen eine eigene Implementierung bereit `IUnknown::QueryInterface` , mit `IDispEventImpl` der `IDispEventSimpleImpl` jede-und-Basisklasse als separate com-Identität fungieren kann und gleichzeitig den direkten Zugriff auf Klassenmember in Ihrem Haupt-com-Objekt zulässt.

Die CE-ATL-Implementierung von ActiveX-Ereignis senken unterstützt nur Rückgabewerte vom Typ HRESULT oder void aus den Ereignishandlermethoden. alle anderen Rückgabewerte werden nicht unterstützt, und ihr Verhalten ist nicht definiert.

Weitere Informationen finden Sie [unter Unterstützung von IDispEventImpl](../../atl/supporting-idispeventimpl.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`_IDispEvent`

`_IDispEventLocator`

[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)

`IDispEventImpl`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="getfuncinfofromid"></a>IDispEventImpl:: getfuncinfofromid

Sucht den Funktions Index für den angegebenen Dispatchbezeichner.

```
HRESULT GetFuncInfoFromId(
    const IID& iid,
    DISPID dispidMember,
    LCID lcid,
    _ATL_FUNC_INFO& info);
```

### <a name="parameters"></a>Parameter

*iid*<br/>
in Ein Verweis auf die ID der Funktion.

*dispidMember*<br/>
in Die Dispatch-ID der Funktion.

*lcid*<br/>
in Der Gebiets Schema Kontext der Funktions-ID.

*info*<br/>
in Die-Struktur, die angibt, wie die-Funktion aufgerufen wird.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

##  <a name="getidsofnames"></a>IDispEventImpl:: GetIDsOfNames

Ordnet einen einzelnen Member und einen optionalen Satz von Argument Namen einem entsprechenden Satz von ganzzahligen DispIds zu, der bei nachfolgenden Aufrufen von [IDispatch:: Aufrufen](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)verwendet werden kann.

```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IDispatch:: GetIDsOfNames](/windows/win32/api/oaidl/nf-oaidl-idispatch-getidsofnames) im Windows SDK.

##  <a name="gettypeinfo"></a>IDispEventImpl:: gettypeingefo

Ruft die Typinformationen für ein Objekt ab, die dann zum Abrufen der Typinformationen für eine Schnittstelle verwendet werden können.

```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Hinweise

##  <a name="gettypeinfocount"></a>IDispEventImpl:: gettypanfocount

Ruft die Anzahl der Schnittstellen mit Typinformationen ab, die von einem Objekt bereitgestellt werden (0 oder 1).

```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IDispatch:: gettypeingefocount](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfocount) in der Windows SDK.

##  <a name="getuserdefinedtype"></a>IDispEventImpl:: getuserdefinedtype

Ruft den Basistyp eines benutzerdefinierten Typs ab.

```
VARTYPE GetUserDefinedType(
    ITypeInfo* pTI,
    HREFTYPE hrt);
```

### <a name="parameters"></a>Parameter

*pTI*<br/>
in Ein Zeiger auf die [ITypeInfo](/windows/win32/api/oaidl/nn-oaidl-itypeinfo) -Schnittstelle, die den benutzerdefinierten Typ enthält.

*hrt*<br/>
in Ein Handle für die Typbeschreibung, die abgerufen werden soll.

### <a name="return-value"></a>Rückgabewert

Der Typ der Variante.

### <a name="remarks"></a>Hinweise

Siehe [itypeingefo:: getreftypeingefo](/windows/win32/api/oaidl/nf-oaidl-itypeinfo-getreftypeinfo).

##  <a name="idispeventimpl"></a>IDispEventImpl:: IDispEventImpl

Der Konstruktor. Speichert die Werte der Klassen Vorlagen Parameter " *plibid*", " *pdiid*", " *wMajor*" und " *wMinor*".

```
IDispEventImpl();
```

##  <a name="tihclass"></a>IDispEventImpl:: tihclass

Diese TypeDef ist eine Instanz des Klassen Vorlagen Parameters *tihclass*.

```
typedef tihclass _tihclass;
```

### <a name="remarks"></a>Hinweise

Standardmäßig ist `CComTypeInfoHolder`die-Klasse. `CComTypeInfoHolder`verwaltet die Typinformationen für die-Klasse.

## <a name="see-also"></a>Siehe auch

[_ATL_FUNC_INFO-Struktur](../../atl/reference/atl-func-info-structure.md)<br/>
[IDispatchImpl-Klasse](../../atl/reference/idispatchimpl-class.md)<br/>
[IDispEventSimpleImpl-Klasse](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[SINK_ENTRY](composite-control-macros.md#sink_entry)<br/>
[SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
