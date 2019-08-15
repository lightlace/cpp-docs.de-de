---
title: IProvideClassInfo2Impl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::GetClassInfo
- ATLCOM/ATL::IProvideClassInfo2Impl::GetGUID
- ATLCOM/ATL::IProvideClassInfo2Impl::_tih
helpviewer_keywords:
- IProvideClassInfo2Impl class
- IProvideClassInfo2 ATL implementation
- class information, ATL
ms.assetid: d74956e8-9c69-4cba-b99d-ca1ac031bb9d
ms.openlocfilehash: f0ff3607002d32b4e21f7fc2199cc5da3662af8b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495540"
---
# <a name="iprovideclassinfo2impl-class"></a>IProvideClassInfo2Impl-Klasse

Diese Klasse stellt eine Standard Implementierung der [IProvideClassInfo](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo) -Methode und der [IProvideClassInfo2](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo2) -Methode bereit.

## <a name="syntax"></a>Syntax

```
template <const CLSID* pcoclsid,
    const IID* psrcid,
    const GUID* plibid = &CAtlModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, class tihclass = CComTypeInfoHolder>
class ATL_NO_VTABLE IProvideClassInfo2Impl : public IProvideClassInfo2
```

#### <a name="parameters"></a>Parameter

*pcoclsid*<br/>
Ein Zeiger auf den Bezeichner der Co-Klasse.

*psrcid*<br/>
Ein Zeiger auf den Bezeichner für die standardmäßige ausgehende dispinterface der Co-Klasse.

*plibid*<br/>
Ein Zeiger auf die LIBID der Typbibliothek, die Informationen über die Schnittstelle enthält. Standardmäßig wird die Typbibliothek auf Serverebene übermittelt.

*wMajor*<br/>
Die Hauptversion der Typbibliothek Der Standardwert ist 1.

*wMinor*<br/>
Die Nebenversion der Typbibliothek Der Standardwert ist 0.

*tihclass*<br/>
Die Klasse, die verwendet wird, um die Typinformationen der Co-Klasse zu verwalten. Der Standardwert ist `CComTypeInfoHolder`.

## <a name="members"></a>Member

### <a name="constructors"></a>Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](#iprovideclassinfo2impl)|Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IProvideClassInfo2Impl::GetClassInfo](#getclassinfo)|Ruft einen `ITypeInfo` Zeiger auf die Typinformationen der Co-Klasse ab.|
|[IProvideClassInfo2Impl::GetGUID](#getguid)|Ruft die GUID für die ausgehende dispinterface des Objekts ab.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[IProvideClassInfo2Impl::_tih](#_tih)|Verwaltet die Typinformationen für die Co-Klasse.|

## <a name="remarks"></a>Hinweise

Die [IProvideClassInfo2](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo2) -Schnittstelle erweitert [IProvideClassInfo](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo) durch `GetGUID` hinzufügen der-Methode. Diese Methode ermöglicht es einem Client, die IID für die ausgehende Schnittstelle eines Objekts für den Standard Ereignis Satz abzurufen. `IProvideClassInfo` - `IProvideClassInfo2Impl` Klasse stellt eine Standard Implementierung der- `IProvideClassInfo2` Methode und der-Methode bereit.

`IProvideClassInfo2Impl`enthält einen statischen Member vom Typ `CComTypeInfoHolder` , der die Typinformationen für die Co-Klasse verwaltet.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IProvideClassInfo2`

`IProvideClassInfo2Impl`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="getclassinfo"></a>IProvideClassInfo2Impl:: GetClassInfo

Ruft einen `ITypeInfo` Zeiger auf die Typinformationen der Co-Klasse ab.

```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IProvideClassInfo:: GetClassInfo](/windows/win32/api/ocidl/nf-ocidl-iprovideclassinfo-getclassinfo) im Windows SDK.

##  <a name="getguid"></a>IProvideClassInfo2Impl:: GetGuid

Ruft die GUID für die ausgehende dispinterface des Objekts ab.

```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IProvideClassInfo2:: GetGuid](/windows/win32/api/ocidl/nf-ocidl-iprovideclassinfo2-getguid) im Windows SDK.

##  <a name="iprovideclassinfo2impl"></a>IProvideClassInfo2Impl::IProvideClassInfo2Impl

Der Konstruktor.

```
IProvideClassInfo2Impl();
```

### <a name="remarks"></a>Hinweise

Ruft `AddRef` den [_tih](#_tih) -Member auf. Der Destruktor ruft `Release` auf.

##  <a name="_tih"></a>IProvideClassInfo2Impl::_tih

Dieser statische Datenmember ist eine Instanz des Klassen Vorlagen Parameters *tihclass*, der standardmäßig ist `CComTypeInfoHolder`.

```
static  tihclass
    _tih;
```

### <a name="remarks"></a>Hinweise

`_tih`verwaltet die Typinformationen für die Co-Klasse.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)
