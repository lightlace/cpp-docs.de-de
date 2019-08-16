---
title: Ipersiststorageimpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IPersistStorageImpl
- ATLCOM/ATL::IPersistStorageImpl
- ATLCOM/ATL::IPersistStorageImpl::GetClassID
- ATLCOM/ATL::IPersistStorageImpl::HandsOffStorage
- ATLCOM/ATL::IPersistStorageImpl::InitNew
- ATLCOM/ATL::IPersistStorageImpl::IsDirty
- ATLCOM/ATL::IPersistStorageImpl::Load
- ATLCOM/ATL::IPersistStorageImpl::Save
- ATLCOM/ATL::IPersistStorageImpl::SaveCompleted
helpviewer_keywords:
- storage, ATL
- IPersistStorageImpl class
ms.assetid: d652f02c-239c-47c7-9a50-3e9fc3014fff
ms.openlocfilehash: a5b5dd4e5be43d01f00687ed9b96a3f27abcad0f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495689"
---
# <a name="ipersiststorageimpl-class"></a>Ipersiststorageimpl-Klasse

Diese Klasse implementiert die [IPersistStorage](/windows/win32/api/objidl/nn-objidl-ipersiststorage) -Schnittstelle.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template <class T>
class ATL_NO_VTABLE IPersistStorageImpl : public IPersistStorage
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die von `IPersistStorageImpl`abgeleitete Klasse.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IPersistStorageImpl::GetClassID](#getclassid)|Ruft die CLSID des Objekts ab.|
|[Ipersiststorageimpl:: HandsOffStorage](#handsoffstorage)|Weist das-Objekt an, alle Speicher Objekte freizugeben und in den handsoff-Modus zu wechseln. Die ATL-Implementierung gibt S_OK zurück.|
|[Ipersiststorageimpl:: InitNew](#initnew)|Initialisiert einen neuen Speicher.|
|[IPersistStorageImpl::IsDirty](#isdirty)|Überprüft, ob die Daten des Objekts seit dem letzten Speichern geändert wurden.|
|[Ipersiststorageimpl:: Load](#load)|Lädt die Eigenschaften des Objekts aus dem angegebenen Speicher.|
|[Ipersiststorageimpl:: Save](#save)|Speichert die Eigenschaften des Objekts im angegebenen Speicher.|
|[Ipersiststorageimpl:: saveabgeschlossen](#savecompleted)|Benachrichtigt ein-Objekt, dass es in den normalen Modus zurückkehren kann, um in sein Speicher Objekt zu schreiben. Die ATL-Implementierung gibt S_OK zurück.|

## <a name="remarks"></a>Hinweise

`IPersistStorageImpl`implementiert die [IPersistStorage](/windows/win32/api/objidl/nn-objidl-ipersiststorage) -Schnittstelle, die es einem Client ermöglicht, das Laden und Speichern der persistenten Daten mithilfe eines Speichers durch einen Client anzufordern.

Die Implementierung dieser Klasse erfordert, dass `T` die-Klasse eine Implementierung `IPersistStreamInit` der-Schnittstelle `QueryInterface`über bereitstellt. In der Regel bedeutet dies `T` , dass die Klasse von [ipersiststreaminitimpl](../../atl/reference/ipersiststreaminitimpl-class.md)abgeleitet werden muss `IPersistStreamInit` , einen Eintrag für in der [com](com-map-macros.md)-Zuordnung bereitstellen und eine [Eigenschaften](property-map-macros.md) Zuordnung verwenden, um die persistenten Daten der Klasse zu beschreiben.

**Verwandte Artikel** [ATL-Tutorial](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IPersistStorage`

`IPersistStorageImpl`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="getclassid"></a>Ipersiststorageimpl:: GetClassID

Ruft die CLSID des Objekts ab.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>Hinweise

Siehe [ipersistent:: GetClassID](/windows/win32/api/objidl/nf-objidl-ipersist-getclassid) in der Windows SDK.

##  <a name="handsoffstorage"></a>Ipersiststorageimpl:: HandsOffStorage

Weist das-Objekt an, alle Speicher Objekte freizugeben und in den handsoff-Modus zu wechseln.

```
STDMETHOD(HandsOffStorage)(void);
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IPersistStorage:: HandsOffStorage](/windows/win32/api/objidl/nf-objidl-ipersiststorage-handsoffstorage) in der Windows SDK.

##  <a name="initnew"></a>Ipersiststorageimpl:: InitNew

Initialisiert einen neuen Speicher.

```
STDMETHOD(InitNew)(IStorage*);
```

### <a name="remarks"></a>Hinweise

Die ATL-Implementierung delegiert an die [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) -Schnittstelle.

Weitere Informationen finden Sie unter [IPersistStorage: InitNew](/windows/win32/api/objidl/nf-objidl-ipersiststorage-initnew) in der Windows SDK.

##  <a name="isdirty"></a>Ipersiststorageimpl:: IsDirty

Überprüft, ob die Daten des Objekts seit dem letzten Speichern geändert wurden.

```
STDMETHOD(IsDirty)(void);
```

### <a name="remarks"></a>Hinweise

Die ATL-Implementierung delegiert an die [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) -Schnittstelle.

Weitere Informationen finden Sie unter [IPersistStorage: IsDirty](/windows/win32/api/objidl/nf-objidl-ipersiststorage-isdirty) in der Windows SDK.

##  <a name="load"></a>Ipersiststorageimpl:: Load

Lädt die Eigenschaften des Objekts aus dem angegebenen Speicher.

```
STDMETHOD(Load)(IStorage* pStorage);
```

### <a name="remarks"></a>Hinweise

Die ATL-Implementierung delegiert an die [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) -Schnittstelle. `Load`verwendet einen Stream mit dem Namen "Content", um die Daten des Objekts abzurufen. Die [Save](#save) -Methode erstellt diesen Stream ursprünglich.

Weitere Informationen finden Sie unter [IPersistStorage: Load](/windows/win32/api/objidl/nf-objidl-ipersiststorage-load) in the Windows SDK.

##  <a name="save"></a>Ipersiststorageimpl:: Save

Speichert die Eigenschaften des Objekts im angegebenen Speicher.

```
STDMETHOD(Save)(IStorage* pStorage, BOOL fSameAsLoad);
```

### <a name="remarks"></a>Hinweise

Die ATL-Implementierung delegiert an die [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) -Schnittstelle. Wenn `Save` zum ersten Mal aufgerufen wird, wird ein Stream mit dem Namen "Content" im angegebenen Speicher erstellt. Dieser Stream wird dann in späteren Aufrufen von `Save` und in [Laden](#load)Aufrufen verwendet.

Weitere Informationen finden Sie unter [IPersistStorage: Speichern](/windows/win32/api/objidl/nf-objidl-ipersiststorage-save) in der Windows SDK.

##  <a name="savecompleted"></a>Ipersiststorageimpl:: saveabgeschlossen

Benachrichtigt ein-Objekt, dass es in den normalen Modus zurückkehren kann, um in sein Speicher Objekt zu schreiben.

```
STDMETHOD(SaveCompleted)(IStorage*);
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Siehe [IPersistStorage: saveabgeschlossene](/windows/win32/api/objidl/nf-objidl-ipersiststorage-savecompleted) in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[Storages und Streams](/windows/win32/Stg/storages-and-streams)<br/>
[IPersistStreamInitImpl-Klasse](../../atl/reference/ipersiststreaminitimpl-class.md)<br/>
[IPersistPropertyBagImpl-Klasse](../../atl/reference/ipersistpropertybagimpl-class.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
