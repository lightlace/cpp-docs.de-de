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
ms.openlocfilehash: 41a0756250e749a07d48ad4f090c2f1c322aa558
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276041"
---
# <a name="iprovideclassinfo2impl-class"></a>IProvideClassInfo2Impl-Klasse

Diese Klasse stellt eine Standardimplementierung von der [IProvideClassInfo](/windows/desktop/api/ocidl/nn-ocidl-iprovideclassinfo) und [IProvideClassInfo2](/windows/desktop/api/ocidl/nn-ocidl-iprovideclassinfo2) Methoden.

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
Ein Zeiger auf den Bezeichner für die Co-Klasse.

*psrcid*<br/>
Ein Zeiger auf den Bezeichner für die Co-Klasse standardmäßige ausgehende Disp-Schnittstelle.

*plibid*<br/>
Ein Zeiger auf die LIBID der Typbibliothek, die Informationen über die Schnittstelle enthält. Standardmäßig wird die Bibliothek auf Serverebene übergeben.

*wMajor*<br/>
Die Hauptversion der Typbibliothek Der Standardwert ist 1.

*wMinor*<br/>
Die Nebenversion der Typbibliothek Der Standardwert ist 0.

*tihclass*<br/>
Die Klasse, die zum Verwalten von Typinformationen für die Co-Klasse verwendet wird. Der Standardwert ist `CComTypeInfoHolder`.

## <a name="members"></a>Member

### <a name="constructors"></a>Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](#iprovideclassinfo2impl)|Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IProvideClassInfo2Impl::GetClassInfo](#getclassinfo)|Ruft eine `ITypeInfo` Zeiger auf die Typinformationen für die Co-Klasse.|
|[IProvideClassInfo2Impl::GetGUID](#getguid)|Ruft die GUID für ausgehende Dispinterface des Objekts ab.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[IProvideClassInfo2Impl::_tih](#_tih)|Verwaltet die Typinformationen für die Co-Klasse.|

## <a name="remarks"></a>Hinweise

Die [IProvideClassInfo2](/windows/desktop/api/ocidl/nn-ocidl-iprovideclassinfo2) Schnittstelle erweitert [IProvideClassInfo](/windows/desktop/api/ocidl/nn-ocidl-iprovideclassinfo) durch Hinzufügen der `GetGUID` Methode. Diese Methode ermöglicht einen Client, ein Objekt des ausgehenden Schnittstellen-IID für die Standardereignissatz abzurufen. Klasse `IProvideClassInfo2Impl` stellt eine Standardimplementierung von der `IProvideClassInfo` und `IProvideClassInfo2` Methoden.

`IProvideClassInfo2Impl` enthält einen statischen Member des Typs `CComTypeInfoHolder` , verwaltet die Typinformationen für die Co-Klasse.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IProvideClassInfo2`

`IProvideClassInfo2Impl`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="getclassinfo"></a>  IProvideClassInfo2Impl::GetClassInfo

Ruft eine `ITypeInfo` Zeiger auf die Typinformationen für die Co-Klasse.

```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [Schnittstellenaufruf](/windows/desktop/api/ocidl/nf-ocidl-iprovideclassinfo-getclassinfo) in das Windows SDK.

##  <a name="getguid"></a>  IProvideClassInfo2Impl::GetGUID

Ruft die GUID für ausgehende Dispinterface des Objekts ab.

```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IProvideClassInfo2::GetGUID](/windows/desktop/api/ocidl/nf-ocidl-iprovideclassinfo2-getguid) in das Windows SDK.

##  <a name="iprovideclassinfo2impl"></a>  IProvideClassInfo2Impl::IProvideClassInfo2Impl

Der Konstruktor.

```
IProvideClassInfo2Impl();
```

### <a name="remarks"></a>Hinweise

Aufrufe `AddRef` auf die [_tih](#_tih) Member. Der Destruktor ruft `Release` auf.

##  <a name="_tih"></a>  IProvideClassInfo2Impl::_tih

Diese statischen Datenmember ist eine Instanz der Klassenvorlagenparameter *Tihclass*, d. h. `CComTypeInfoHolder`.

```
static  tihclass
    _tih;
```

### <a name="remarks"></a>Hinweise

`_tih` Verwaltet die Typinformationen für die Co-Klasse.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
