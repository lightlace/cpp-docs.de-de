---
title: IAccessorImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IAccessorImpl
- ATL.IAccessorImpl.IAccessorImpl
- ATL::IAccessorImpl::IAccessorImpl
- IAccessorImpl::IAccessorImpl
- IAccessorImpl.IAccessorImpl
- IAccessorImpl
- ATL::IAccessorImpl::AddRefAccessor
- AddRefAccessor
- IAccessorImpl::AddRefAccessor
- IAccessorImpl.AddRefAccessor
- ATL.IAccessorImpl.AddRefAccessor
- IAccessorImpl::CreateAccessor
- CreateAccessor
- ATL::IAccessorImpl::CreateAccessor
- IAccessorImpl.CreateAccessor
- ATL.IAccessorImpl.CreateAccessor
- IAccessorImpl.GetBindings
- ATL::IAccessorImpl::GetBindings
- IAccessorImpl::GetBindings
- GetBindings
- ATL.IAccessorImpl.GetBindings
- ReleaseAccessor
- IAccessorImpl::ReleaseAccessor
- ATL.IAccessorImpl.ReleaseAccessor
- ATL::IAccessorImpl::ReleaseAccessor
- IAccessorImpl.ReleaseAccessor
helpviewer_keywords:
- IAccessorImpl class
- IAccessorImpl class, constructor
- IAccessorImpl constructor
- AddRefAccessor method
- CreateAccessor method
- GetBindings method
- ReleaseAccessor method
ms.assetid: 768606da-8b71-417c-a62c-88069ce7730d
ms.openlocfilehash: a01a090d4302983f7d53e051cf4d8a72bd739b4a
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556737"
---
# <a name="iaccessorimpl-class"></a>IAccessorImpl-Klasse

Stellt eine Implementierung der [IAccessor](https://docs.microsoft.com/previous-versions/windows/desktop/ms719672(v=vs.85)) Schnittstelle.

## <a name="syntax"></a>Syntax

```cpp
template <class T,
   class BindType = ATLBINDINGS,
   class BindingVector = CAtlMap <HACCESSOR hAccessor, BindType* pBindingsStructure>>
class ATL_NO_VTABLE IAccessorImpl : public IAccessorImplBase<BindType>
```

### <a name="parameters"></a>Parameter

*T*<br/>
Ihre Rowset oder Object-Klasse.

*BindType*<br/>
Storage-Einheit für die Bindungsinformationen. Der Standardwert ist die `ATLBINDINGS` Struktur (finden Sie unter "atldb.h").

*BindingVector*<br/>
Storage-Einheit für die Spalteninformationen. Der Standardwert ist [CAtlMap](../../atl/reference/catlmap-class.md) , in denen das Schlüsselelement ist ein HACCESSOR-Wert und die Value-Element ist ein Zeiger auf eine `BindType` Struktur.

## <a name="requirements"></a>Anforderungen

**Header:** „atldb.h“

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[IAccessorImpl](#iaccessorimpl)|Der Konstruktor.|

### <a name="interface-methods"></a>Schnittstellenmethoden

|||
|-|-|
|[AddRefAccessor](#addrefaccessor)|Fügt einem vorhandenen Accessor einen Verweiszähler hinzu.|
|[CreateAccessor](#createaccessor)|Erstellt einen Accessor aus einem Satz von Bindungen.|
|[GetBindings](#getbindings)|Gibt die Bindungen in einem Accessor zurück.|
|[ReleaseAccessor](#releaseaccessor)|Gibt einen Accessor frei.|

## <a name="remarks"></a>Hinweise

Dies ist erforderlich für Rowsets und Befehle. OLE DB verlangt von Anbietern zum Implementieren einer HACCESSOR, dies ist ein Tag auf ein Array von [DBBINDING](https://docs.microsoft.com/previous-versions/windows/desktop/ms716845(v=vs.85)) Strukturen. Von bereitgestellten HACCESSORs `IAccessorImpl` Adressen sind die `BindType` Strukturen. In der Standardeinstellung `BindType` ist definiert als eine `ATLBINDINGS` in `IAccessorImpl`der Vorlagendefinition. `BindType` Stellt einen Mechanismus, der von verwendeten `IAccessorImpl` zum Nachverfolgen der Anzahl der Elemente in der `DBBINDING` array sowie einen Verweis Count "und"-Accessor-Flags.

## <a name="iaccessorimpl"></a> IAccessorImpl:: IAccessorImpl

Der Konstruktor.

### <a name="syntax"></a>Syntax

```cpp
IAccessorImpl();
```

## <a name="addrefaccessor"></a> IAccessorImpl:: Addrefaccessor

Fügt einem vorhandenen Accessor einen Verweiszähler hinzu.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(AddRefAccessor)(HACCESSOR hAccessor,
   DBREFCOUNT* pcRefCount);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IAccessor::AddRefAccessor](https://docs.microsoft.com/previous-versions/windows/desktop/ms714978(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="createaccessor"></a> IAccessorImpl:: CreateAccessor

Erstellt einen Accessor aus einem Satz von Bindungen.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(CreateAccessor)(DBACCESSORFLAGS dwAccessorFlags,
   DBCOUNTITEM cBindings,
   const DBBINDING rgBindings[],
   DBLENGTH cbRowSize,
   HACCESSOR* phAccessor,
   DBBINDSTATUS rgStatus[]);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IAccessor:: CreateAccessor](https://docs.microsoft.com/previous-versions/windows/desktop/ms720969(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="getbindings"></a> IAccessorImpl:: Getbindings

Gibt die grundlegenden Spalten Bindungen aus der Consumer in einem Accessor zurück.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(GetBindings)(HACCESSOR hAccessor,
   DBACCESSORFLAGS* pdwAccessorFlags,
   DBCOUNTITEM* pcBindings,
   DBBINDING** prgBindings);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IAccessor::GetBindings](https://docs.microsoft.com/previous-versions/windows/desktop/ms721253(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="releaseaccessor"></a> IAccessorImpl:: ReleaseAccessor

Gibt einen Accessor frei.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(ReleaseAccessor)(HACCESSOR hAccessor,
   DBREFCOUNT* pcRefCount);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [ReleaseAccessor](https://docs.microsoft.com/previous-versions/windows/desktop/ms719717(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)