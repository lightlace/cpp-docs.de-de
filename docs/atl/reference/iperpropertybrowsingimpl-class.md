---
title: IPerPropertyBrowsingImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetDisplayString
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedStrings
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedValue
- ATLCTL/ATL::IPerPropertyBrowsingImpl::MapPropertyToPage
dev_langs:
- C++
helpviewer_keywords:
- IPerPropertyBrowsingImpl class
- property pages, accessing information
- IPerPropertyBrowsing, ATL implementation
ms.assetid: 0b1a9be3-d242-4767-be69-663a21e4b728
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a8fc5cc44eeb06c5afec23b6a0a094c14987c599
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096092"
---
# <a name="iperpropertybrowsingimpl-class"></a>IPerPropertyBrowsingImpl-Klasse

Diese Klasse implementiert `IUnknown` und ermöglicht es einem Client auf die Informationen in den Eigenschaftenseiten eines Objekts zugreifen.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```

template <class T>
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :
    public IPerPropertyBrowsing
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `IPerPropertyBrowsingImpl`.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IPerPropertyBrowsingImpl::GetDisplayString](#getdisplaystring)|Ruft eine Zeichenfolge, die eine bestimmte Eigenschaft beschreibt.|
|[IPerPropertyBrowsingImpl::GetPredefinedStrings](#getpredefinedstrings)|Ruft ein Array von Zeichenfolgen, die für die Werte, die eine bestimmte Eigenschaft annehmen kann.|
|[IPerPropertyBrowsingImpl::GetPredefinedValue](#getpredefinedvalue)|Ruft ab eine Variante, die mit dem Wert einer Eigenschaft, die von einer angegebenen DISPID identifiziert. Die DISPID zugeordnet ist, mit dem Namen der Zeichenfolge entnommen `GetPredefinedStrings`. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IPerPropertyBrowsingImpl::MapPropertyToPage](#mappropertytopage)|Ruft die CLSID der Eigenschaftenseite auf eine bestimmte Eigenschaft zugeordnet.|

## <a name="remarks"></a>Hinweise

Die [IPerPropertyBrowsing](/windows/desktop/api/ocidl/nn-ocidl-iperpropertybrowsing) Schnittstelle ermöglicht es einen Client auf die Informationen in den Eigenschaftenseiten eines Objekts zugreifen. Klasse `IPerPropertyBrowsingImpl` stellt eine Standardimplementierung dieser Schnittstelle bereit und implementiert `IUnknown` durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus wird erstellt.

> [!NOTE]
>  Wenn Sie Microsoft Access als die Container-Anwendung verwenden, müssen Sie ableiten der Klasse aus `IPerPropertyBrowsingImpl`. Andernfalls wird Zugriff nicht das Steuerelement geladen.

**Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IPerPropertyBrowsing`

`IPerPropertyBrowsingImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="getdisplaystring"></a>  IPerPropertyBrowsingImpl::GetDisplayString

Ruft eine Zeichenfolge, die eine bestimmte Eigenschaft beschreibt.

```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IPerPropertyBrowsing::GetDisplayString](/windows/desktop/api/ocidl/nf-ocidl-iperpropertybrowsing-getdisplaystring) in das Windows SDK.

##  <a name="getpredefinedstrings"></a>  IPerPropertyBrowsingImpl::GetPredefinedStrings

Füllt jede Array mit 0 (null) Elemente.

```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```

### <a name="return-value"></a>Rückgabewert

Der ATL-Implementierung von [GetPredefinedValue](#getpredefinedvalue) gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IPerPropertyBrowsing::GetPredefinedStrings](/windows/desktop/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedstrings) in das Windows SDK.

##  <a name="getpredefinedvalue"></a>  IPerPropertyBrowsingImpl::GetPredefinedValue

Ruft ab eine Variante, die mit dem Wert einer Eigenschaft, die von einer angegebenen DISPID identifiziert. Die DISPID zugeordnet ist, mit dem Namen der Zeichenfolge entnommen `GetPredefinedStrings`.

```
STDMETHOD(GetPredefinedValue)(
    DISPID dispID,
    DWORD dwCookie,
    VARIANT* pVarOut);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Der ATL-Implementierung von [GetPredefinedStrings](#getpredefinedstrings) ruft keine entsprechenden Zeichenfolgen ab.

Finden Sie unter [IPerPropertyBrowsing::GetPredefinedValue](/windows/desktop/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedvalue) in das Windows SDK.

##  <a name="mappropertytopage"></a>  IPerPropertyBrowsingImpl::MapPropertyToPage

Ruft die CLSID der Eigenschaftenseite auf die angegebene Eigenschaft zugeordnet.

```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```

### <a name="remarks"></a>Hinweise

ATL verwendet eigenschaftenzuordnung des Objekts, um diese Informationen abzurufen.

Finden Sie unter [IPerPropertyBrowsing::MapPropertyToPage](/windows/desktop/api/ocidl/nf-ocidl-iperpropertybrowsing-mappropertytopage) in das Windows SDK.

## <a name="see-also"></a>Siehe auch

[IPropertyPageImpl-Klasse](../../atl/reference/ipropertypageimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl-Klasse](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
