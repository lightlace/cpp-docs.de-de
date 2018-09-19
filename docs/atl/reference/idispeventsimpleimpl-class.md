---
title: IDispEventSimpleImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl::Advise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventAdvise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventUnadvise
- ATLCOM/ATL::IDispEventSimpleImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventSimpleImpl::Invoke
- ATLCOM/ATL::IDispEventSimpleImpl::Unadvise
dev_langs:
- C++
helpviewer_keywords:
- IDispEventSimpleImpl class
ms.assetid: 971d82b7-a921-47fa-a4d8-909bed377ab0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9eb111b3fa1376be8a43bfc9a04c7865164bff76
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084574"
---
# <a name="idispeventsimpleimpl-class"></a>IDispEventSimpleImpl-Klasse

Diese Klasse stellt Implementierungen von der `IDispatch` Methoden ohne das Abrufen von Typinformationen aus einer Typbibliothek.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <UINT nID, class T, const IID* pdiid>
class ATL_NO_VTABLE IDispEventSimpleImpl : public _IDispEventLocator<nID, pdiid>
```

#### <a name="parameters"></a>Parameter

*nID*<br/>
Ein eindeutiger Bezeichner für das Quellobjekt. Wenn `IDispEventSimpleImpl` ist die Basisklasse für ein zusammengesetztes Steuerelement ist, verwenden Sie die Ressourcen-ID des gewünschten enthaltenen Steuerelements für diesen Parameter. Verwenden Sie in anderen Fällen eine beliebige positive ganze Zahl.

*T*<br/>
Der Benutzer-Klasse, die abgeleitet wird `IDispEventSimpleImpl`.

*pdiid*<br/>
Der Zeiger auf die IID für die ereignisanzeigeschnittstelle, die von dieser Klasse implementiert.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IDispEventSimpleImpl::Advise](#advise)|Herstellen einer Verbindung mit der Standard-Ereignisquelle.|
|[IDispEventSimpleImpl:: DispEventAdvise](#dispeventadvise)|Herstellen einer Verbindung mit der Ereignisquelle.|
|[IDispEventSimpleImpl::DispEventUnadvise](#dispeventunadvise)|Trennt die Verbindung mit der Ereignisquelle.|
|[IDispEventSimpleImpl::GetIDsOfNames](#getidsofnames)|Gibt E_NOTIMPL zurück.|
|[IDispEventSimpleImpl::GetTypeInfo](#gettypeinfo)|Gibt E_NOTIMPL zurück.|
|[IDispEventSimpleImpl::GetTypeInfoCount](#gettypeinfocount)|Gibt E_NOTIMPL zurück.|
|[IDispEventSimpleImpl::Invoke](#invoke)|Ruft die Ereignishandler aufgeführt in der ereignismeldung Sink-Zuordnung.|
|[IDispEventSimpleImpl::Unadvise](#unadvise)|Trennt die Verbindung mit der Standard-Ereignisquelle.|

## <a name="remarks"></a>Hinweise

`IDispEventSimpleImpl` bietet eine Möglichkeit der Implementierung einer ereignisanzeigeschnittstelle ohne Implementierungscode für jede Methode bzw. dieses Ereignis auf dieser Schnittstelle bereitstellen. `IDispEventSimpleImpl` Implementierungen von der `IDispatch` Methoden. Sie müssen nur Implementierungen für die Ereignisse angeben, dass Sie bei der Verwendung von Interesse sind.

`IDispEventSimpleImpl` funktioniert in Verbindung mit der Ereignis-Sink-Zuordnung in der Klasse zum Weiterleiten von Ereignissen an die entsprechenden Handler-Funktion. Diese Klasse verwenden zu können:

- Hinzufügen einer [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info) Makro, um die Zuordnung des Ereignis-Senke für jedes Ereignis auf jedes Objekt, das Sie behandeln möchten.

- Angeben von Typinformationen für jedes Ereignis durch die Übergabe eines Zeigers auf ein [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) Struktur als Parameter für jeden Eintrag. Auf der X86-Plattform, die `_ATL_FUNC_INFO.cc` Wert muss CC_CDECL sein, mit der Callback-Funktion aufrufen __stdcall-Methode.

- Rufen Sie [DispEventAdvise](#dispeventadvise) zum Herstellen der Verbindung zwischen dem Quellobjekt und die Basisklasse.

- Rufen Sie [DispEventUnadvise](#dispeventunadvise) um die Verbindung trennen.

Durch Ableiten von `IDispEventSimpleImpl` (verwenden einen eindeutigen Wert für *nID*) für jedes Objekt, das für die Ereignisse behandelt werden sollen. Sie können die Basisklasse wiederverwenden, indem Sie für ein Quellobjekt, klicken Sie dann für eine andere Quellobjekt berät abmelden, aber die maximale Anzahl von-Objekte, die von einem einzigen Objekt gleichzeitig verarbeitet werden kann, wird durch die Anzahl der beschränkt `IDispEventSimpleImpl` Basisklassen.

`IDispEventSimplImpl` bietet die gleiche Funktionalität wie [IDispEventImpl](../../atl/reference/idispeventimpl-class.md), außer dass sie nicht über Informationen über die Schnittstelle aus einer Typbibliothek erhält. Die Assistenten generieren basiert nur auf Code `IDispEventImpl`, aber Sie können `IDispEventSimpleImpl` durch den Code manuell hinzufügen. Verwendung `IDispEventSimpleImpl` Wenn Sie eine Typbibliothek, die die Schnittstelle beschreibt haben oder den Aufwand in Zusammenhang mit der Verwendung der Typbibliothek vermeiden möchten, nicht.

> [!NOTE]
> `IDispEventImpl` und `IDispEventSimpleImpl` Geben Sie ihre eigene Implementierung des `IUnknown::QueryInterface` Aktivieren der einzelnen `IDispEventImpl` oder `IDispEventSimpleImpl` Basisklasse fungieren Sie als separate COM-Identität während nach wie vor direkten Zugriffs auf Klassenmember in Ihre wichtigsten COM-Objekt.

CE ATL-Implementierung von ActiveX-Ereignissenken nur unterstützt die Rückgabewerte vom Typ HRESULT oder "void" Ihre Ereignishandlermethoden; Jeder andere Rückgabewert wird nicht unterstützt, und das Verhalten nicht definiert ist.

Weitere Informationen finden Sie unter [unterstützen von IDispEventImpl](../../atl/supporting-idispeventimpl.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`_IDispEvent`

`_IDispEventLocator`

`IDispEventSimpleImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="advise"></a>  IDispEventSimpleImpl::Advise

Rufen Sie diese Methode zum Herstellen einer Verbindung mit der Ereignisquelle durch dargestellt *pUnk*.

```
HRESULT Advise(IUnknown* pUnk);
```

### <a name="parameters"></a>Parameter

*pUnk*<br/>
[in] Ein Zeiger auf die `IUnknown` Schnittstelle das Ereignisquellobjekt.

### <a name="return-value"></a>Rückgabewert

S_OK oder Fehler HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Sobald die Verbindung hergestellt wurde, werden Ereignisse aus ausgelöst *pUnk* an Handler in der Klasse über die Zuordnung der Ereignis-Senke weitergeleitet werden.

> [!NOTE]
>  Wenn Ihre Klasse abgeleitet, aus mehreren wird `IDispEventSimpleImpl` Klassen müssen Sie die Aufrufe dieser Methode durch den Aufruf mit der bestimmten Basisklasse, die Sie interessiert sind Bereichsauswahl unterscheiden.

`Advise` Stellt eine Verbindung her mit der Standard-Ereignisquelle, ruft es ab, die IID für die Ereignisquelle "Standard" des Objekts gemäß [AtlGetObjectSourceInterface](composite-control-global-functions.md#atlgetobjectsourceinterface).

##  <a name="dispeventadvise"></a>  IDispEventSimpleImpl:: DispEventAdvise

Rufen Sie diese Methode zum Herstellen einer Verbindung mit der Ereignisquelle durch dargestellt *pUnk*.

```
HRESULT DispEventAdvise(IUnknown* pUnk  const IID* piid);
```

### <a name="parameters"></a>Parameter

*pUnk*<br/>
[in] Ein Zeiger auf die `IUnknown` Schnittstelle das Ereignisquellobjekt.

*piid*<br/>
Ein Zeiger auf die IID für das Ereignisquellobjekt.

### <a name="return-value"></a>Rückgabewert

S_OK oder Fehler HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Anschließend Ereignisse ausgelöst von *pUnk* an Handler in der Klasse über die Zuordnung der Ereignis-Senke weitergeleitet werden.

> [!NOTE]
>  Wenn Ihre Klasse abgeleitet, aus mehreren wird `IDispEventSimpleImpl` Klassen müssen Sie die Aufrufe dieser Methode durch den Aufruf mit der bestimmten Basisklasse, die Sie interessiert sind Bereichsauswahl unterscheiden.

`DispEventAdvise` Stellt eine Verbindung her, wobei die Ereignisquelle, die im angegebenen `pdiid`.

##  <a name="dispeventunadvise"></a>  IDispEventSimpleImpl::DispEventUnadvise

Unterbrechen Sie die Verbindung mit der Ereignisquelle durch dargestellt *pUnk*.

```
HRESULT DispEventUnadvise(IUnknown* pUnk  const IID* piid);
```

### <a name="parameters"></a>Parameter

*pUnk*<br/>
[in] Ein Zeiger auf die `IUnknown` Schnittstelle das Ereignisquellobjekt.

*piid*<br/>
Ein Zeiger auf die IID für das Ereignisquellobjekt.

### <a name="return-value"></a>Rückgabewert

S_OK oder Fehler HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Nachdem die Verbindung unterbrochen wird, werden Ereignisse nicht mehr an Handlerfunktionen in die Senke ereigniszuordnung weitergeleitet werden.

> [!NOTE]
>  Wenn Ihre Klasse abgeleitet, aus mehreren wird `IDispEventSimpleImpl` Klassen müssen Sie die Aufrufe dieser Methode durch den Aufruf mit der bestimmten Basisklasse, die Sie interessiert sind Bereichsauswahl unterscheiden.

`DispEventAdvise` eine Verbindung mit der Ereignisquelle, die im angegebenen aufgebaut wurde unterbrochen `pdiid`.

##  <a name="getidsofnames"></a>  IDispEventSimpleImpl::GetIDsOfNames

Diese Implementierung der `IDispatch::GetIDsOfNames` gibt E_NOTIMPL zurück.

```
STDMETHOD(GetIDsOfNames)(
    REFIID /* riid */,
    LPOLESTR* /* rgszNames */,
    UINT /* cNames */,
    LCID /* lcid */,
    DISPID* /* rgdispid */);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [GetIDsOfNames](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-getidsofnames) in das Windows SDK.

##  <a name="gettypeinfo"></a>  IDispEventSimpleImpl::GetTypeInfo

Diese Implementierung der `IDispatch::GetTypeInfo` gibt E_NOTIMPL zurück.

```
STDMETHOD(GetTypeInfo)(
    UINT /* itinfo */,
    LCID /* lcid */,
    ITypeInfo** /* pptinfo */);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IDispatch:: GetTypeInfo](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-gettypeinfo) in das Windows SDK.

##  <a name="gettypeinfocount"></a>  IDispEventSimpleImpl::GetTypeInfoCount

Diese Implementierung der `IDispatch::GetTypeInfoCount` gibt E_NOTIMPL zurück.

```
STDMETHOD(GetTypeInfoCount)(UINT* /* pctinfo */);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IDispatch:: GetTypeInfoCount](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-gettypeinfocount) in das Windows SDK.

##  <a name="invoke"></a>  IDispEventSimpleImpl::Invoke

Diese Implementierung der `IDispatch::Invoke` Aufrufe, die die Ereignishandler aufgeführt in der ereignismeldung Sink-Zuordnung.

```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID /* riid */,
    LCID lcid,
    WORD /* wFlags */,
    DISPPARMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* /* pexcepinfo */,
    UINT* /* puArgErr */);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IDispatch:: Invoke](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke).

##  <a name="unadvise"></a>  IDispEventSimpleImpl::Unadvise

Unterbrechen Sie die Verbindung mit der Ereignisquelle durch dargestellt *pUnk*.

```
HRESULT Unadvise(IUnknown* pUnk);
```

### <a name="parameters"></a>Parameter

*pUnk*<br/>
[in] Ein Zeiger auf die `IUnknown` Schnittstelle das Ereignisquellobjekt.

### <a name="return-value"></a>Rückgabewert

S_OK oder Fehler HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Nachdem die Verbindung unterbrochen wird, werden Ereignisse nicht mehr an Handlerfunktionen in die Senke ereigniszuordnung weitergeleitet werden.

> [!NOTE]
>  Wenn Ihre Klasse abgeleitet, aus mehreren wird `IDispEventSimpleImpl` Klassen müssen Sie die Aufrufe dieser Methode durch den Aufruf mit der bestimmten Basisklasse, die Sie interessiert sind Bereichsauswahl unterscheiden.

`Unadvise` eine Verbindung mit der Standard-Ereignisquelle, die im angegebenen aufgebaut wurde unterbrochen `pdiid`.

`Unavise` unterbricht eine Verbindung mit der Standard-Ereignisquelle, ruft die IID der Ereignisquelle des Objekts gemäß Standardeinstellung ab [AtlGetObjectSourceInterface](composite-control-global-functions.md#atlgetobjectsourceinterface).

## <a name="see-also"></a>Siehe auch

[_ATL_FUNC_INFO-Struktur](../../atl/reference/atl-func-info-structure.md)<br/>
[IDispatchImpl-Klasse](../../atl/reference/idispatchimpl-class.md)<br/>
[IDispEventImpl-Klasse](../../atl/reference/idispeventimpl-class.md)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
