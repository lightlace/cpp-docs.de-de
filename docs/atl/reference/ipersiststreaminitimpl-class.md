---
title: IPersistStreamInitImpl-Klasse
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
ms.openlocfilehash: b5ab433ed08b150e6c344d65657a910542856e77
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62197618"
---
# <a name="ipersiststreaminitimpl-class"></a>IPersistStreamInitImpl-Klasse

Diese Klasse implementiert `IUnknown` und stellt eine Standardimplementierung von der [IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit) Schnittstelle.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class ATL_NO_VTABLE IPersistStreamInitImpl
   : public IPersistStreamInit
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `IPersistStreamInitImpl`.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IPersistStreamInitImpl::GetClassID](#getclassid)|Ruft die CLSID des Objekts ab.|
|[IPersistStreamInitImpl::GetSizeMax](#getsizemax)|Ruft die Größe des Streams, der zum Speichern von Daten des Objekts ab. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IPersistStreamInitImpl::InitNew](#initnew)|Initialisiert ein neu erstelltes Objekt.|
|[IPersistStreamInitImpl::IsDirty](#isdirty)|Überprüft, ob die Daten des Objekts geändert hat, seit es zuletzt gespeichert wurde.|
|[IPersistStreamInitImpl::Load](#load)|Lädt die Eigenschaften des Objekts aus dem angegebenen Stream.|
|[IPersistStreamInitImpl::Save](#save)|Speichert die Eigenschaften des Objekts im angegebenen Stream.|

## <a name="remarks"></a>Hinweise

Die [IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit) Schnittstelle kann ein Client anfordern, dass das Objekt lädt und ihre permanenten Daten in einem einzelnen Stream speichert. Klasse `IPersistStreamInitImpl` stellt eine Standardimplementierung dieser Schnittstelle bereit und implementiert `IUnknown` durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus wird erstellt.

**Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IPersistStreamInit`

`IPersistStreamInitImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="getclassid"></a>  IPersistStreamInitImpl::GetClassID

Ruft die CLSID des Objekts ab.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IPersist:: GetClassID](/windows/desktop/api/objidl/nf-objidl-ipersist-getclassid) in das Windows SDK.

##  <a name="getsizemax"></a>  IPersistStreamInitImpl::GetSizeMax

Ruft die Größe des Streams, der zum Speichern von Daten des Objekts ab.

```
STDMETHOD(GetSizeMax)(ULARGE_INTEGER FAR* pcbSize);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IPersistStreamInit::GetSizeMax](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-getsizemax) in das Windows SDK.

##  <a name="initnew"></a>  IPersistStreamInitImpl::InitNew

Initialisiert ein neu erstelltes Objekt.

```
STDMETHOD(InitNew)();
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IPersistStreamInit:: InitNew](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-initnew) in das Windows SDK.

##  <a name="isdirty"></a>  IPersistStreamInitImpl::IsDirty

Überprüft, ob die Daten des Objekts geändert hat, seit es zuletzt gespeichert wurde.

```
STDMETHOD(IsDirty)();
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IPersistStreamInit::IsDirty](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-isdirty) in das Windows SDK.

##  <a name="load"></a>  IPersistStreamInitImpl::Load

Lädt die Eigenschaften des Objekts aus dem angegebenen Stream.

```
STDMETHOD(Load)(LPSTREAM pStm);
```

### <a name="remarks"></a>Hinweise

ATL verwendet eigenschaftenzuordnung des Objekts, um diese Informationen abzurufen.

Finden Sie unter [IPersistStreamInit::Load](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-load) in das Windows SDK.

##  <a name="save"></a>  IPersistStreamInitImpl::Save

Speichert die Eigenschaften des Objekts im angegebenen Stream.

```
STDMETHOD(Save)(LPSTREAM pStm, BOOL fClearDirty);
```

### <a name="remarks"></a>Hinweise

ATL verwendet eigenschaftenzuordnung des Objekts, um diese Informationen speichern.

Finden Sie unter [IPersistStreamInit::Save](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-save) in das Windows SDK.

## <a name="see-also"></a>Siehe auch

[Speicher und Streams](/windows/desktop/Stg/storages-and-streams)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
