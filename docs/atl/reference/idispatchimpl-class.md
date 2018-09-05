---
title: IDispatchImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IDispatchImpl
- ATLCOM/ATL::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::GetIDsOfNames
- ATLCOM/ATL::IDispatchImpl::GetTypeInfo
- ATLCOM/ATL::IDispatchImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispatchImpl::Invoke
dev_langs:
- C++
helpviewer_keywords:
- dual interfaces, classes
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 8108eb36-1228-4127-a203-3ab5ba488892
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 878fa1f530a73a9d872a1b094d0ea0ee1b822971
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43756362"
---
# <a name="idispatchimpl-class"></a>IDispatchImpl-Klasse

Stellt eine Standardimplementierung für die `IDispatch` eine duale Schnittstelle Teil.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

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

[in] *T*  
Eine duale Schnittstelle.

[in] *Piid*  
Ein Zeiger auf die IID der *T*.

[in] *Plibid*  
Ein Zeiger auf die LIBID der Typbibliothek, die Informationen über die Schnittstelle enthält. Standardmäßig wird die Bibliothek auf Serverebene übergeben.

[in] *wMajor*  
Die Hauptversion der Typbibliothek Standardmäßig ist der Wert 1.

[in] *wMinor*  
Die Nebenversion der Typbibliothek Standardmäßig ist der Wert 0.

[in] *Tihclass*  
Die Klasse, die zum Verwalten von Informationen für den *T*. In der Standardeinstellung ist der Wert `CComTypeInfoHolder`.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[IDispatchImpl::IDispatchImpl](#idispatchimpl)|Der Konstruktor. Aufrufe `AddRef` für die geschützten Member-Variable, die die Typinformationen für die duale Schnittstelle verwaltet. Der Destruktor ruft `Release` auf.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IDispatchImpl::GetIDsOfNames](#getidsofnames)|Ordnet eine Reihe von Namen einer entsprechenden Reihe von Dispatchbezeichnern zu.|
|[IDispatchImpl::GetTypeInfo](#gettypeinfo)|Ruft die Typinformationen für die duale Schnittstelle ab.|
|[IDispatchImpl::GetTypeInfoCount](#gettypeinfocount)|Bestimmt, ob Typinformationen für die duale Schnittstelle verfügbar ist.|
|[IDispatchImpl::Invoke](#invoke)|Bietet Zugriff auf die Methoden und Eigenschaften, die von der duale Schnittstelle verfügbar gemacht werden.|

## <a name="remarks"></a>Hinweise

`IDispatchImpl` Stellt eine Standardimplementierung für die `IDispatch` Teil einer dualen Schnittstelle für ein Objekt. Eine duale Schnittstelle leitet sich von `IDispatch` und werden nur Automation-kompatiblen Typen verwendet. Wie eine Disp-Schnittstelle unterstützt eine duale Schnittstelle frühen und späten Bindung. eine duale Schnittstelle unterstützt jedoch auch Vtable-Bindung.

Das folgende Beispiel zeigt eine typische Implementierung der `IDispatchImpl`.

[!code-cpp[NVC_ATL_COM#47](../../atl/codesnippet/cpp/idispatchimpl-class_1.h)]

In der Standardeinstellung die `IDispatchImpl` Klasse sucht die Typinformationen für *T* in der Registrierung. Um eine nicht registrierte Schnittstelle zu implementieren, können Sie die `IDispatchImpl` Klasse ohne Zugriff auf die Registrierung mit einer vordefinierten Versionsnummer. Bei der Erstellung einer `IDispatchImpl` Objekt mit 0xFFFF als Wert für *wMajor* und 0xFFFF als Wert für *wMinor*, `IDispatchImpl` Klasse ruft die Typbibliothek aus der DLL-Datei anstelle von der die Registrierung.

`IDispatchImpl` enthält einen statischen Member des Typs `CComTypeInfoHolder` , der die Typinformationen für die duale Schnittstelle verwaltet. Wenn Sie mehrere Objekte verfügen, die die gleiche duale implementieren Schnittstelle ist, wird nur eine Instanz des `CComTypeInfoHolder` verwendet wird.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`T`

`IDispatchImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="getidsofnames"></a>  IDispatchImpl::GetIDsOfNames

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

Finden Sie unter [GetIDsOfNames](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-getidsofnames) in das Windows SDK.

##  <a name="gettypeinfo"></a>  IDispatchImpl::GetTypeInfo

Ruft die Typinformationen für die duale Schnittstelle ab.

```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IDispatch:: GetTypeInfo](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-gettypeinfo) in das Windows SDK.

##  <a name="gettypeinfocount"></a>  IDispatchImpl::GetTypeInfoCount

Bestimmt, ob Typinformationen für die duale Schnittstelle verfügbar ist.

```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter `IDispatch::GetTypeInfoCount` in das Windows SDK.

##  <a name="idispatchimpl"></a>  IDispatchImpl::IDispatchImpl

Der Konstruktor. Aufrufe `AddRef` für die geschützten Member-Variable, die die Typinformationen für die duale Schnittstelle verwaltet. Der Destruktor ruft `Release` auf.

```
IDispatchImpl();
```

##  <a name="invoke"></a>  IDispatchImpl::Invoke

Bietet Zugriff auf die Methoden und Eigenschaften, die von der duale Schnittstelle verfügbar gemacht werden.

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

Finden Sie unter [IDispatch:: Invoke](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke) in das Windows SDK.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
