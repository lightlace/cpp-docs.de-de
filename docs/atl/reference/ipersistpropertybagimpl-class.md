---
title: IPersistPropertyBagImpl-Klasse
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
ms.openlocfilehash: 800c38c15e4ec8028fba9188d75e49be7ca51146
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274892"
---
# <a name="ipersistpropertybagimpl-class"></a>IPersistPropertyBagImpl-Klasse

Diese Klasse implementiert `IUnknown` und ermöglicht einem Objekt, dessen Eigenschaften in einen vom Client bereitgestellter Eigenschaftenbehälter zu speichern.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <class T>
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `IPersistPropertyBagImpl`.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IPersistPropertyBagImpl::GetClassID](#getclassid)|Ruft die CLSID des Objekts ab.|
|[IPersistPropertyBagImpl::InitNew](#initnew)|Initialisiert ein neu erstelltes Objekt. Es gibt S_OK zurück, die ATL-Implementierung.|
|[IPersistPropertyBagImpl::Load](#load)|Lädt die Eigenschaften des Objekts aus einem Client bereitgestellte Eigenschaftenbehälter.|
|[IPersistPropertyBagImpl::Save](#save)|Speichert die Eigenschaften des Objekts in einen vom Client bereitgestellter Eigenschaftenbehälter.|

## <a name="remarks"></a>Hinweise

Die [IPersistPropertyBag](https://msdn.microsoft.com/library/aa768205.aspx) Schnittstelle ermöglicht einem Objekt, dessen Eigenschaften in einen vom Client bereitgestellter Eigenschaftenbehälter zu speichern. Klasse `IPersistPropertyBagImpl` stellt eine Standardimplementierung dieser Schnittstelle bereit und implementiert `IUnknown` durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus wird erstellt.

`IPersistPropertyBag` funktioniert in Verbindung mit [IPropertyBag](https://msdn.microsoft.com/library/aa768196.aspx) und [IErrorLog](https://msdn.microsoft.com/library/aa768231.aspx). Diese letzten beiden Schnittstellen müssen vom Client implementiert werden. Über `IPropertyBag`, der Client speichert und lädt Sie die einzelnen Eigenschaften des Objekts. Über `IErrorLog`, können das Objekt und der Client alle aufgetretenen Fehler melden.

**Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IPersistPropertyBag`

`IPersistPropertyBagImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="getclassid"></a>  IPersistPropertyBagImpl::GetClassID

Ruft die CLSID des Objekts ab.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [IPersist:: GetClassID](/windows/desktop/api/objidl/nf-objidl-ipersist-getclassid) in das Windows SDK.

##  <a name="initnew"></a>  IPersistPropertyBagImpl::InitNew

Initialisiert ein neu erstelltes Objekt.

```
STDMETHOD(InitNew)();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IPersistPropertyBag::InitNew](https://msdn.microsoft.com/library/aa768204.aspx) in das Windows SDK.

##  <a name="load"></a>  IPersistPropertyBagImpl::Load

Lädt die Eigenschaften des Objekts aus einem Client bereitgestellte Eigenschaftenbehälter.

```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```

### <a name="remarks"></a>Hinweise

ATL verwendet eigenschaftenzuordnung des Objekts, um diese Informationen abzurufen.

Finden Sie unter [IPersistPropertyBag::Load](https://msdn.microsoft.com/library/aa768206.aspx) in das Windows SDK.

##  <a name="save"></a>  IPersistPropertyBagImpl::Save

Speichert die Eigenschaften des Objekts in einen vom Client bereitgestellter Eigenschaftenbehälter.

```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```

### <a name="remarks"></a>Hinweise

ATL verwendet eigenschaftenzuordnung des Objekts, um diese Informationen speichern. Diese Methode speichert standardmäßig alle Eigenschaften, unabhängig vom Wert der *fSaveAllProperties*.

Finden Sie unter [IPersistPropertyBag::Save](https://msdn.microsoft.com/library/aa768207.aspx) in das Windows SDK.

## <a name="see-also"></a>Siehe auch

[BEGIN_PROP_MAP](property-map-macros.md#begin_prop_map)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
