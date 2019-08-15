---
title: Ipersiststreaminitimpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl::GetClassID
- ATLCOM/ATL::IPersistStreamInitImpl::GetSizeMax
- ATLCOM/ATL::IPersistStreamInitImpl::InitNew
- ATLCOM/ATL::IPersistStreamInitImpl::IsDirty
- ATLCOM/ATL::IPersistStreamInitImpl::Load
- ATLCOM/ATL::IPersistStreamInitImpl::Save
helpviewer_keywords:
- IPersistStreamInit ATL implementation
- IPersistStreamInitImpl class
- streams, ATL
ms.assetid: ef217c3c-020f-4cf8-871e-ef68e57865b8
ms.openlocfilehash: 7a350a4349cb825795a18dd860a2482952b04dcb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496152"
---
# <a name="ipersiststreaminitimpl-class"></a>Ipersiststreaminitimpl-Klasse

Diese Klasse implementiert `IUnknown` und stellt eine Standard Implementierung der [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) -Schnittstelle bereit.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class ATL_NO_VTABLE IPersistStreamInitImpl
   : public IPersistStreamInit
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die von `IPersistStreamInitImpl`abgeleitete Klasse.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IPersistStreamInitImpl::GetClassID](#getclassid)|Ruft die CLSID des Objekts ab.|
|[IPersistStreamInitImpl::GetSizeMax](#getsizemax)|Ruft die Größe des Streams ab, der zum Speichern der Daten des Objekts benötigt wird. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[Ipersiststreaminitimpl:: InitNew](#initnew)|Initialisiert ein neu erstelltes-Objekt.|
|[IPersistStreamInitImpl::IsDirty](#isdirty)|Überprüft, ob die Daten des Objekts seit dem letzten Speichern geändert wurden.|
|[IPersistStreamInitImpl::Load](#load)|Lädt die Eigenschaften des Objekts aus dem angegebenen Stream.|
|[Ipersiststreaminitimpl:: Save](#save)|Speichert die Eigenschaften des Objekts in den angegebenen Stream.|

## <a name="remarks"></a>Hinweise

Mithilfe der [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) -Schnittstelle kann ein Client anfordern, dass das Objekt seine persistenten Daten lädt und in einem einzigen Stream speichert. Die `IPersistStreamInitImpl` -Klasse stellt eine Standard Implementierung dieser Schnittstelle `IUnknown` bereit und implementiert durch das Senden von Informationen an das dumpgerät in Debugbuilds.

**Verwandte Artikel** [ATL-Tutorial](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IPersistStreamInit`

`IPersistStreamInitImpl`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="getclassid"></a>Ipersiststreaminitimpl:: GetClassID

Ruft die CLSID des Objekts ab.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>Hinweise

Siehe [ipersistent:: GetClassID](/windows/win32/api/objidl/nf-objidl-ipersist-getclassid) in der Windows SDK.

##  <a name="getsizemax"></a>Ipersiststreaminitimpl:: GetSizeMax

Ruft die Größe des Streams ab, der zum Speichern der Daten des Objekts benötigt wird.

```
STDMETHOD(GetSizeMax)(ULARGE_INTEGER FAR* pcbSize);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie im Windows SDK unter [IPersistStreamInit:: GetSizeMax](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-getsizemax) .

##  <a name="initnew"></a>Ipersiststreaminitimpl:: InitNew

Initialisiert ein neu erstelltes-Objekt.

```
STDMETHOD(InitNew)();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IPersistStreamInit:: InitNew](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-initnew) in der Windows SDK.

##  <a name="isdirty"></a>Ipersiststreaminitimpl:: IsDirty

Überprüft, ob die Daten des Objekts seit dem letzten Speichern geändert wurden.

```
STDMETHOD(IsDirty)();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IPersistStreamInit:: IsDirty](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-isdirty) in der Windows SDK.

##  <a name="load"></a>Ipersiststreaminitimpl:: Load

Lädt die Eigenschaften des Objekts aus dem angegebenen Stream.

```
STDMETHOD(Load)(LPSTREAM pStm);
```

### <a name="remarks"></a>Hinweise

ATL verwendet die Eigenschaften Zuordnung des Objekts, um diese Informationen abzurufen.

Weitere Informationen finden Sie unter [IPersistStreamInit:: Load](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-load) in der Windows SDK.

##  <a name="save"></a>Ipersiststreaminitimpl:: Save

Speichert die Eigenschaften des Objekts in den angegebenen Stream.

```
STDMETHOD(Save)(LPSTREAM pStm, BOOL fClearDirty);
```

### <a name="remarks"></a>Hinweise

ATL verwendet die Eigenschaften Zuordnung des Objekts, um diese Informationen zu speichern.

Weitere Informationen finden Sie unter [IPersistStreamInit:: Save](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-save) in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[Storages und Streams](/windows/win32/Stg/storages-and-streams)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
