---
title: Ipersistpropertybagimpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl::GetClassID
- ATLCOM/ATL::IPersistPropertyBagImpl::InitNew
- ATLCOM/ATL::IPersistPropertyBagImpl::Load
- ATLCOM/ATL::IPersistPropertyBagImpl::Save
helpviewer_keywords:
- IPersistPropertyBagImpl class
ms.assetid: 712af24d-99f8-40f2-9811-53b3ff6e5b19
ms.openlocfilehash: 15b9c9738d921c4c6f7837f9280c6dd6b09392d6
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495774"
---
# <a name="ipersistpropertybagimpl-class"></a>Ipersistpropertybagimpl-Klasse

Diese Klasse implementiert `IUnknown` und ermöglicht einem Objekt, seine Eigenschaften in einem vom Client bereitgestellten Eigenschaften Behälter zu speichern.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template <class T>
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die von `IPersistPropertyBagImpl`abgeleitete Klasse.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IPersistPropertyBagImpl::GetClassID](#getclassid)|Ruft die CLSID des Objekts ab.|
|[IPersistPropertyBagImpl::InitNew](#initnew)|Initialisiert ein neu erstelltes-Objekt. Die ATL-Implementierung gibt S_OK zurück.|
|[IPersistPropertyBagImpl::Load](#load)|Lädt die Eigenschaften des-Objekts aus einem vom Client bereitgestellten Eigenschaften Behälter.|
|[IPersistPropertyBagImpl::Save](#save)|Speichert die Eigenschaften des Objekts in einem vom Client bereitgestellten Eigenschaften Behälter.|

## <a name="remarks"></a>Hinweise

Die [IPersistPropertyBag](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768205\(v=vs.85\)) -Schnittstelle ermöglicht es einem Objekt, seine Eigenschaften in einem vom Client bereitgestellten Eigenschaften Behälter zu speichern. Die `IPersistPropertyBagImpl` -Klasse stellt eine Standard Implementierung dieser Schnittstelle `IUnknown` bereit und implementiert durch das Senden von Informationen an das dumpgerät in Debugbuilds.

`IPersistPropertyBag`funktioniert in Verbindung mit [IPropertyBag](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768196\(v=vs.85\)) und [IErrorLog](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768231\(v=vs.85\)). Diese beiden beiden Schnittstellen müssen vom Client implementiert werden. `IPropertyBag`Mithilfe von speichert und lädt der Client die einzelnen Eigenschaften des Objekts. Über `IErrorLog`können sowohl das-Objekt als auch der Client alle gefundenen Fehler melden.

**Verwandte Artikel** [ATL-Tutorial](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IPersistPropertyBag`

`IPersistPropertyBagImpl`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="getclassid"></a>Ipersistpropertybagimpl:: GetClassID

Ruft die CLSID des Objekts ab.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>Hinweise

Siehe [ipersistent:: GetClassID](/windows/win32/api/objidl/nf-objidl-ipersist-getclassid) in der Windows SDK.

##  <a name="initnew"></a>Ipersistpropertybagimpl:: InitNew

Initialisiert ein neu erstelltes-Objekt.

```
STDMETHOD(InitNew)();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IPersistPropertyBag:: InitNew](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768204\(v=vs.85\)) in der Windows SDK.

##  <a name="load"></a>Ipersistpropertybagimpl:: Load

Lädt die Eigenschaften des-Objekts aus einem vom Client bereitgestellten Eigenschaften Behälter.

```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```

### <a name="remarks"></a>Hinweise

ATL verwendet die Eigenschaften Zuordnung des Objekts, um diese Informationen abzurufen.

Weitere Informationen finden Sie unter [IPersistPropertyBag:: Load](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768206\(v=vs.85\)) in der Windows SDK.

##  <a name="save"></a>Ipersistpropertybagimpl:: Save

Speichert die Eigenschaften des Objekts in einem vom Client bereitgestellten Eigenschaften Behälter.

```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```

### <a name="remarks"></a>Hinweise

ATL verwendet die Eigenschaften Zuordnung des Objekts, um diese Informationen zu speichern. Standardmäßig speichert diese Methode alle Eigenschaften, unabhängig vom Wert von " *ssaveallproperties*".

Weitere Informationen finden Sie unter [IPersistPropertyBag:: Save](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768207\(v=vs.85\)) in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[BEGIN_PROP_MAP](property-map-macros.md#begin_prop_map)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
