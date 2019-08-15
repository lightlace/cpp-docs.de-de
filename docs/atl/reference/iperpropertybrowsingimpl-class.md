---
title: Iperpropertybrowsingimpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetDisplayString
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedStrings
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedValue
- ATLCTL/ATL::IPerPropertyBrowsingImpl::MapPropertyToPage
helpviewer_keywords:
- IPerPropertyBrowsingImpl class
- property pages, accessing information
- IPerPropertyBrowsing, ATL implementation
ms.assetid: 0b1a9be3-d242-4767-be69-663a21e4b728
ms.openlocfilehash: 263f6826ac921d864dee646ef063c8b456b00af1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495718"
---
# <a name="iperpropertybrowsingimpl-class"></a>Iperpropertybrowsingimpl-Klasse

Diese Klasse implementiert `IUnknown` und ermöglicht einem Client den Zugriff auf die Informationen auf den Eigenschaften Seiten eines Objekts.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```

template <class T>
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :
    public IPerPropertyBrowsing
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die von `IPerPropertyBrowsingImpl`abgeleitete Klasse.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IPerPropertyBrowsingImpl::GetDisplayString](#getdisplaystring)|Ruft eine Zeichenfolge ab, die eine bestimmte Eigenschaft beschreibt.|
|[IPerPropertyBrowsingImpl::GetPredefinedStrings](#getpredefinedstrings)|Ruft ein Array von Zeichen folgen ab, die den Werten entsprechen, die eine bestimmte Eigenschaft annehmen kann.|
|[IPerPropertyBrowsingImpl::GetPredefinedValue](#getpredefinedvalue)|Ruft einen Variant-Wert ab, der den Wert einer Eigenschaft enthält, die durch eine angegebene DISPID identifiziert wird. Die DISPID ist mit dem aus abgerufenen `GetPredefinedStrings`Zeichen folgen Namen verknüpft. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[Iperpropertybrowsingimpl:: mappropertytopage](#mappropertytopage)|Ruft die CLSID der Eigenschaften Seite ab, die einer angegebenen Eigenschaft zugeordnet ist.|

## <a name="remarks"></a>Hinweise

Die [IPerPropertyBrowsing](/windows/win32/api/ocidl/nn-ocidl-iperpropertybrowsing) -Schnittstelle ermöglicht einem Client den Zugriff auf die Informationen auf den Eigenschaften Seiten eines Objekts. Die `IPerPropertyBrowsingImpl` -Klasse stellt eine Standard Implementierung dieser Schnittstelle `IUnknown` bereit und implementiert durch das Senden von Informationen an das dumpgerät in Debugbuilds.

> [!NOTE]
>  Wenn Sie Microsoft Access als Containeranwendung verwenden, müssen Sie die Klasse von `IPerPropertyBrowsingImpl`ableiten. Andernfalls wird das Steuerelement nicht durch den Zugriff geladen.

**Verwandte Artikel** [ATL-Tutorial](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IPerPropertyBrowsing`

`IPerPropertyBrowsingImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="getdisplaystring"></a>Iperpropertybrowsingimpl:: GetDisplayString

Ruft eine Zeichenfolge ab, die eine bestimmte Eigenschaft beschreibt.

```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IPerPropertyBrowsing:: GetDisplayString](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getdisplaystring) im Windows SDK.

##  <a name="getpredefinedstrings"></a>Iperpropertybrowsingimpl:: getpredefinedstrings

Füllt jedes Array mit 0 (null) Elementen.

```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```

### <a name="return-value"></a>Rückgabewert

Die ATL-Implementierung von [getpredefinedvalue](#getpredefinedvalue) gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IPerPropertyBrowsing:: getpredefinedstrings](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedstrings) in der Windows SDK.

##  <a name="getpredefinedvalue"></a>Iperpropertybrowsingimpl:: getpredefinedvalue

Ruft einen Variant-Wert ab, der den Wert einer Eigenschaft enthält, die durch eine angegebene DISPID identifiziert wird. Die DISPID ist mit dem aus abgerufenen `GetPredefinedStrings`Zeichen folgen Namen verknüpft.

```
STDMETHOD(GetPredefinedValue)(
    DISPID dispID,
    DWORD dwCookie,
    VARIANT* pVarOut);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Die ATL-Implementierung von [getpredefinedstrings](#getpredefinedstrings) ruft keine entsprechenden Zeichen folgen ab.

Weitere Informationen finden Sie unter [IPerPropertyBrowsing:: getpredefinedvalue](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedvalue) in der Windows SDK.

##  <a name="mappropertytopage"></a>Iperpropertybrowsingimpl:: mappropertytopage

Ruft die CLSID der Eigenschaften Seite ab, die der angegebenen Eigenschaft zugeordnet ist.

```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```

### <a name="remarks"></a>Hinweise

ATL verwendet die Eigenschaften Zuordnung des Objekts, um diese Informationen zu erhalten.

Weitere Informationen finden Sie unter [IPerPropertyBrowsing:: mappropertytopage](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-mappropertytopage) in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[IPropertyPageImpl-Klasse](../../atl/reference/ipropertypageimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl-Klasse](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
