---
title: IDispatchImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IDispatchImpl
- ATLCOM/ATL::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::GetIDsOfNames
- ATLCOM/ATL::IDispatchImpl::GetTypeInfo
- ATLCOM/ATL::IDispatchImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispatchImpl::Invoke
helpviewer_keywords:
- dual interfaces, classes
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 8108eb36-1228-4127-a203-3ab5ba488892
ms.openlocfilehash: 7e9cb903742cdc31c1d9bba2c4aabbb0472407c1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495953"
---
# <a name="idispatchimpl-class"></a>IDispatchImpl-Klasse

Stellt eine Standard Implementierung für den `IDispatch` Teil einer Dual-Schnittstelle bereit.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template<class T,
        const IID* piid= &__uuidof(T),
        const GUID* plibid = &CAtlModule::m_libid,
        WORD wMajor = 1,
        WORD wMinor = 0,
        class tihclass = CComTypeInfoHolder>
class ATL_NO_VTABLE IDispatchImpl : public T
```

#### <a name="parameters"></a>Parameter

*T*<br/>
in Eine duale Schnittstelle.

*piid*<br/>
in Ein Zeiger auf die IID von *T*.

*plibid*<br/>
in Ein Zeiger auf die LIBID der Typbibliothek, die Informationen über die Schnittstelle enthält. Standardmäßig wird die Typbibliothek auf Serverebene übermittelt.

*wMajor*<br/>
in Die Hauptversion der Typbibliothek. Standardmäßig ist der Wert 1.

*wMinor*<br/>
in Die neben Version der Typbibliothek. Standardmäßig ist der Wert 0.

*tihclass*<br/>
in Die Klasse, mit der die Typinformationen für *T*verwaltet werden. In der Standardeinstellung ist der Wert `CComTypeInfoHolder`.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[IDispatchImpl::IDispatchImpl](#idispatchimpl)|Der Konstruktor. Ruft `AddRef` die geschützte Member-Variable auf, die die Typinformationen für die duale Schnittstelle verwaltet. Der Destruktor ruft `Release` auf.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IDispatchImpl::GetIDsOfNames](#getidsofnames)|Ordnet eine Reihe von Namen einer entsprechenden Reihe von Dispatchbezeichnern zu.|
|[IDispatchImpl::GetTypeInfo](#gettypeinfo)|Ruft die Typinformationen für die duale Schnittstelle ab.|
|[IDispatchImpl::GetTypeInfoCount](#gettypeinfocount)|Bestimmt, ob für die duale Schnittstelle Typinformationen verfügbar sind.|
|[IDispatchImpl::Invoke](#invoke)|Bietet Zugriff auf die Methoden und Eigenschaften, die von der Dual-Schnittstelle verfügbar gemacht werden.|

## <a name="remarks"></a>Hinweise

`IDispatchImpl`stellt eine Standard Implementierung für den `IDispatch` Teil einer beliebigen Dual-Schnittstelle für ein Objekt bereit. Eine duale Schnittstelle wird `IDispatch` von abgeleitet und verwendet nur Automatisierungs kompatible Typen. Wie eine dispinterface unterstützt eine duale Schnittstelle eine frühe Bindung und spätes Binden. eine duale Schnittstelle unterstützt jedoch auch die Vtable-Bindung.

Das folgende Beispiel zeigt eine typische Implementierung von `IDispatchImpl`.

[!code-cpp[NVC_ATL_COM#47](../../atl/codesnippet/cpp/idispatchimpl-class_1.h)]

Standardmäßig sucht die `IDispatchImpl` -Klasse in der Registrierung nach den Typinformationen für *T* . Um eine nicht registrierte Schnittstelle zu implementieren, können Sie `IDispatchImpl` die-Klasse verwenden, ohne auf die Registrierung zuzugreifen, indem Sie eine vordefinierte Versionsnummer verwenden. Wenn Sie ein `IDispatchImpl` Objekt erstellen, das 0xFFFF als Wert für *wMajor* und 0xFFFF als Wert für *wMinor*hat, ruft die `IDispatchImpl` -Klasse die Typbibliothek aus der DLL-Datei anstelle der Registrierung ab.

`IDispatchImpl`enthält einen statischen Member vom Typ `CComTypeInfoHolder` , der die Typinformationen für die duale Schnittstelle verwaltet. Wenn Sie über mehrere Objekte verfügen, die dieselbe duale Schnittstelle implementieren, wird nur `CComTypeInfoHolder` eine Instanz von verwendet.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`T`

`IDispatchImpl`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="getidsofnames"></a>IDispatchImpl:: GetIDsOfNames

Ordnet eine Reihe von Namen einer entsprechenden Reihe von Dispatchbezeichnern zu.

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

##  <a name="gettypeinfo"></a>IDispatchImpl:: gettypeingefo

Ruft die Typinformationen für die duale Schnittstelle ab.

```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IDispatch:: gettypeingefo](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfo) im Windows SDK.

##  <a name="gettypeinfocount"></a>IDispatchImpl:: gettypanfocount

Bestimmt, ob für die duale Schnittstelle Typinformationen verfügbar sind.

```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```

### <a name="remarks"></a>Hinweise

Weitere `IDispatch::GetTypeInfoCount` Informationen finden Sie in der Windows SDK.

##  <a name="idispatchimpl"></a>IDispatchImpl:: IDispatchImpl

Der Konstruktor. Ruft `AddRef` die geschützte Member-Variable auf, die die Typinformationen für die duale Schnittstelle verwaltet. Der Destruktor ruft `Release` auf.

```
IDispatchImpl();
```

##  <a name="invoke"></a>IDispatchImpl:: aufrufen

Bietet Zugriff auf die Methoden und Eigenschaften, die von der Dual-Schnittstelle verfügbar gemacht werden.

```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID riid,
    LCID lcid,
    WORD wFlags,
    DISPPARAMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* pexcepinfo,
    UINT* puArgErr);
```

### <a name="remarks"></a>Hinweise

Siehe [IDispatch:: Aufrufen](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)
