---
title: IDispEventImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IDispEventImpl
- ATLCOM/ATL::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::GetFuncInfoFromId
- ATLCOM/ATL::IDispEventImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventImpl::GetUserDefinedType
dev_langs:
- C++
helpviewer_keywords:
- IDispEventImpl class
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 815a276cb07a91da73acb68a32cceef4b2138325
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093839"
---
# <a name="idispeventimpl-class"></a>IDispEventImpl-Klasse

Diese Klasse stellt Implementierungen von der `IDispatch` Methoden.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

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
Ein eindeutiger Bezeichner für das Quellobjekt. Wenn `IDispEventImpl` ist die Basisklasse für ein zusammengesetztes Steuerelement ist, verwenden Sie die Ressourcen-ID des gewünschten enthaltenen Steuerelements für diesen Parameter. Verwenden Sie in anderen Fällen eine beliebige positive ganze Zahl.

*T*<br/>
Der Benutzer-Klasse, die abgeleitet wird `IDispEventImpl`.

*pdiid*<br/>
Der Zeiger auf die IID für die ereignisanzeigeschnittstelle, die von dieser Klasse implementiert. Diese Schnittstelle muss definiert werden, in der Typbibliothek gekennzeichnet durch *Plibid*, *wMajor*, und *wMinor*.

*plibid*<br/>
Ein Zeiger auf die Typbibliothek, die die Dispatchschnittstelle definiert verweist *Pdiid*. Wenn **& GUID_NULL**, aus dem Objekt, das als Quelle der Ereignisse wird die Typbibliothek geladen werden.

*wMajor*<br/>
Die Hauptversion der Typbibliothek Der Standardwert ist 0.

*wMinor*<br/>
Die Nebenversion der Typbibliothek Der Standardwert ist 0.

*tihclass*<br/>
Die Klasse, die zum Verwalten von Informationen für den *T*. Der Standardwert ist eine Klasse vom Typ `CComTypeInfoHolder`, aber Sie können diesen Vorlagenparameter überschreiben, indem Sie eine Klasse von einem Typ außer bereitstellen `CComTypeInfoHolder`.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|[IDispEventImpl::_tihclass](../../atl/reference/idispeventimpl-class.md)|Die Klasse verwendet, um die Typinformationen zu verwalten. In der Standardeinstellung `CComTypeInfoHolder`.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[IDispEventImpl::IDispEventImpl](#idispeventimpl)|Der Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IDispEventImpl::GetFuncInfoFromId](#getfuncinfofromid)|Sucht den Index der Funktion für den angegebenen Dispatchbezeichner.|
|[IDispEventImpl::GetIDsOfNames](#getidsofnames)|Ordnet einen entsprechenden Satz von ganzzahligen DISPIDs ein einzelnes Element und einen optionalen Satz von Argumentnamen.|
|[IDispEventImpl::GetTypeInfo](#gettypeinfo)|Ruft die Typinformationen für ein Objekt ab.|
|[IDispEventImpl::GetTypeInfoCount](#gettypeinfocount)|Ruft die Anzahl der Schnittstellen mit Typinformationen ab.|
|[IDispEventImpl::GetUserDefinedType](#getuserdefinedtype)|Ruft den einfachen Typ eines benutzerdefinierten Typs ab.|

## <a name="remarks"></a>Hinweise

`IDispEventImpl` bietet eine Möglichkeit der Implementierung einer ereignisanzeigeschnittstelle ohne Implementierungscode für jede Methode bzw. dieses Ereignis auf dieser Schnittstelle bereitstellen. `IDispEventImpl` Implementierungen von der `IDispatch` Methoden. Sie müssen nur Implementierungen für die Ereignisse angeben, dass Sie bei der Verwendung von Interesse sind.

`IDispEventImpl` funktioniert in Verbindung mit der Ereignis-Sink-Zuordnung in der Klasse zum Weiterleiten von Ereignissen an die entsprechenden Handler-Funktion. Diese Klasse verwenden zu können:

Hinzufügen einer [SINK_ENTRY](composite-control-macros.md#sink_entry) oder [SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex) Makro, um die Zuordnung des Ereignis-Senke für jedes Ereignis auf jedes Objekt, das Sie behandeln möchten. Bei Verwendung `IDispEventImpl` einer Basisklasse eines zusammengesetzten Steuerelements können Sie aufrufen [AtlAdviseSinkMap](connection-point-global-functions.md#atladvisesinkmap) herstellen und trennen die Verbindung mit der der Ereignisquelle aus, für alle Einträge in dieser Zuordnung Senke. Rufen Sie in anderen Fällen, oder für größere Kontrolle, [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) zum Herstellen der Verbindung zwischen dem Quellobjekt und die Basisklasse. Rufen Sie [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise) um die Verbindung trennen.  

Durch Ableiten von `IDispEventImpl` (verwenden einen eindeutigen Wert für *nID*) für jedes Objekt, das für die Ereignisse behandelt werden sollen. Sie können die Basisklasse wiederverwenden, indem Sie für ein Quellobjekt, klicken Sie dann für eine andere Quellobjekt berät abmelden, aber die maximale Anzahl von-Objekte, die von einem einzigen Objekt gleichzeitig verarbeitet werden kann, wird durch die Anzahl der beschränkt `IDispEventImpl` Basisklassen.

`IDispEventImpl` bietet die gleiche Funktionalität wie [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md), außer dass die Informationen über die Schnittstelle aus einer Typbibliothek, anstatt sie als Zeiger auf bereitgestellt werden wird eine [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) -Struktur. Verwendung `IDispEventSimpleImpl` Wenn Sie eine Typbibliothek, beschreibt die Schnittstelle bzw. keine den Aufwand in Zusammenhang mit der Verwendung der Typbibliothek vermeiden möchten.

> [!NOTE]
> `IDispEventImpl` und `IDispEventSimpleImpl` Geben Sie ihre eigene Implementierung des `IUnknown::QueryInterface` Aktivieren der einzelnen `IDispEventImpl` und `IDispEventSimpleImpl` Basisklasse fungieren Sie als separate COM-Identität während nach wie vor direkten Zugriffs auf Klassenmember in Ihre wichtigsten COM-Objekt.

CE ATL-Implementierung von ActiveX-Ereignissenken nur unterstützt die Rückgabewerte vom Typ HRESULT oder "void" Ihre Ereignishandlermethoden; Jeder andere Rückgabewert wird nicht unterstützt, und das Verhalten nicht definiert ist.

Weitere Informationen finden Sie unter [unterstützen von IDispEventImpl](../../atl/supporting-idispeventimpl.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`_IDispEvent`

`_IDispEventLocator`

[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)

`IDispEventImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="getfuncinfofromid"></a>  IDispEventImpl::GetFuncInfoFromId

Sucht den Index der Funktion für den angegebenen Dispatchbezeichner.

```
HRESULT GetFuncInfoFromId(
    const IID& iid,
    DISPID dispidMember,
    LCID lcid,
    _ATL_FUNC_INFO& info);
```

### <a name="parameters"></a>Parameter

*IID*<br/>
[in] Ein Verweis auf die ID der Funktion.

*dispidMember*<br/>
[in] Die Dispatch-ID der Funktion.

*lcid*<br/>
[in] Der Gebietsschemakontext, von der Funktions-ID

*Info*<br/>
[in] Die Struktur, der angibt, wie die Funktion aufgerufen wird.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="getidsofnames"></a>  IDispEventImpl::GetIDsOfNames

Ordnet einen entsprechenden Satz von ganzzahligen DISPIDs, die bei nachfolgenden Aufrufen verwendet werden kann ein einzelnes Element und einen optionalen Satz von Namen des Funktionsarguments [IDispatch:: Invoke](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke).

```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [GetIDsOfNames](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-getidsofnames) in das Windows SDK.

##  <a name="gettypeinfo"></a>  IDispEventImpl::GetTypeInfo

Ruft die Typinformationen für ein Objekt ab, die dann zum Abrufen der Typinformationen für eine Schnittstelle verwendet werden können.

```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Hinweise

##  <a name="gettypeinfocount"></a>  IDispEventImpl::GetTypeInfoCount

Ruft die Anzahl der Schnittstellen mit Typinformationen ab, die von einem Objekt bereitgestellt werden (0 oder 1).

```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IDispatch:: GetTypeInfoCount](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-gettypeinfocount) in das Windows SDK.

##  <a name="getuserdefinedtype"></a>  IDispEventImpl::GetUserDefinedType

Ruft den einfachen Typ eines benutzerdefinierten Typs ab.

```
VARTYPE GetUserDefinedType(
    ITypeInfo* pTI,
    HREFTYPE hrt);
```

### <a name="parameters"></a>Parameter

*PTI*<br/>
[in] Ein Zeiger auf die [ITypeInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) Schnittstelle, die den benutzerdefinierten Typ enthält.

*hrt*<br/>
[in] Ein Handle für die Beschreibung abgerufen werden sollen.

### <a name="return-value"></a>Rückgabewert

Der Typ der Variante.

### <a name="remarks"></a>Hinweise

Finden Sie unter [ITypeInfo:: GetRefTypeInfo](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-itypeinfo-getreftypeinfo).

##  <a name="idispeventimpl"></a>  IDispEventImpl::IDispEventImpl

Der Konstruktor. Speichert die Werte der Vorlagenparameter Klasse *Plibid*, *Pdiid*, *wMajor*, und *wMinor*.

```
IDispEventImpl();
```

##  <a name="tihclass"></a>  IDispEventImpl::tihclass

Diese Typdefinition ist eine Instanz der Klassenvorlagenparameter *Tihclass*.

```
typedef tihclass _tihclass;
```

### <a name="remarks"></a>Hinweise

Standardmäßig ist die Klasse `CComTypeInfoHolder`. `CComTypeInfoHolder` verwaltet die Typinformationen für die Klasse an.

## <a name="see-also"></a>Siehe auch

[_ATL_FUNC_INFO-Struktur](../../atl/reference/atl-func-info-structure.md)<br/>
[IDispatchImpl-Klasse](../../atl/reference/idispatchimpl-class.md)<br/>
[IDispEventSimpleImpl-Klasse](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[SINK_ENTRY](composite-control-macros.md#sink_entry)<br/>
[SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)