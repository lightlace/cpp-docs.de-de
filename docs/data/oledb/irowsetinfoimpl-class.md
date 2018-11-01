---
title: IRowsetInfoImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- ATL.IRowsetInfoImpl
- IRowsetInfoImpl
- ATL::IRowsetInfoImpl
- ATL.IRowsetInfoImpl.GetProperties
- IRowsetInfoImpl.GetProperties
- ATL::IRowsetInfoImpl::GetProperties
- IRowsetInfoImpl::GetProperties
- GetProperties
- ATL::IRowsetInfoImpl::GetReferencedRowset
- GetReferencedRowset
- ATL.IRowsetInfoImpl.GetReferencedRowset
- IRowsetInfoImpl.GetReferencedRowset
- IRowsetInfoImpl::GetReferencedRowset
- IRowsetInfoImpl::GetSpecification
- ATL.IRowsetInfoImpl.GetSpecification
- IRowsetInfoImpl.GetSpecification
- GetSpecification
- ATL::IRowsetInfoImpl::GetSpecification
helpviewer_keywords:
- IRowsetInfoImpl class
- GetProperties method
- GetReferencedRowset method
- GetSpecification method
ms.assetid: 9c654155-7727-464e-bd31-143e68391a47
ms.openlocfilehash: 39c4f441e7b18fd93510620f1052677cdd0e881e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580283"
---
# <a name="irowsetinfoimpl-class"></a>IRowsetInfoImpl-Klasse

Stellt eine Implementierung für die [IRowsetInfo](/previous-versions/windows/desktop/ms724541) Schnittstelle.

## <a name="syntax"></a>Syntax

```cpp
template <class T, class PropClass = T>
class ATL_NO_VTABLE IRowsetInfoImpl :
   public IRowsetInfo,  
   public CUtlProps<PropClass>
```

### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `IRowsetInfoImpl`.

*PropClass*<br/>
Eine mit benutzerdefinierbaren-Eigenschaftsklasse, die standardmäßig *T*.

## <a name="requirements"></a>Anforderungen

**Header:** altdb.h

## <a name="members"></a>Member

### <a name="interface-methods"></a>Schnittstellenmethoden

|||
|-|-|
|[GetProperties](#getproperties)|Gibt die aktuellen Einstellungen aller vom Rowset unterstützten Eigenschaften zurück.|
|[GetReferencedRowset](#getreferencedrowset)|Gibt einen Schnittstellenzeiger auf das Rowset, für das ein Lesezeichen gilt, zurück.|
|[GetSpecification](#getspecification)|Gibt einen Schnittstellenzeiger zurück, für das Objekt (Befehl oder Sitzung), die dieses Rowset erstellt.|

## <a name="remarks"></a>Hinweise

Eine erforderliche Schnittstelle für Rowsets. Diese Klasse implementiert die Rowseteigenschaften mit dem [Satz eigenschaftenzuordnung](../../data/oledb/begin-propset-map.md) in Ihrer Klasse des Befehls definiert. Obwohl die Rowset-Klasse angezeigt wird, auf die Verwendung der Command-Klasse-Eigenschaft festlegt, wird das Rowset mit ihrer eigenen Kopie der Laufzeit-Eigenschaften, bereitgestellt, bei der Erstellung von einem Befehl oder Sitzung-Objekt.

## <a name="getproperties"></a> Irowsetinfoimpl:: GetProperties

Gibt die aktuellen Einstellungen für Eigenschaften in der `DBPROPSET_ROWSET` Gruppe.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD (GetProperties )(const ULONG cPropertyIDSets,
   const DBPROPIDSET rgPropertyIDSets[],
   ULONG* pcPropertySets,
   DBPROPSET** prgPropertySets);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IRowsetInfo:: GetProperties](/previous-versions/windows/desktop/ms719611) in die *OLE DB-Programmierreferenz*.

## <a name="getreferencedrowset"></a> Irowsetinfoimpl:: Getreferencedrowset

Gibt einen Schnittstellenzeiger auf das Rowset, für das ein Lesezeichen gilt, zurück.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD (GetReferencedRowset )(DBORDINAL iOrdinal,
   REFIID riid,
   IUnknown** ppReferencedRowset);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IRowsetInfo::GetReferencedRowset](/previous-versions/windows/desktop/ms721145) in die *OLE DB-Programmierreferenz*. Die *iOrdinal* -Parameter muss eine Lesezeichenspalte sein.

## <a name="getspecification"></a> Irowsetinfoimpl:: Getspecification

Gibt einen Schnittstellenzeiger zurück, für das Objekt (Befehl oder Sitzung), die dieses Rowset erstellt.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD (GetSpecification )(REFIID riid,
   IUnknown** ppSpecification);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IRowsetInfo::GetSpecification](/previous-versions/windows/desktop/ms716746) in die *OLE DB-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode mit [IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md) zum Abrufen von Eigenschaften aus dem Daten-Quellobjekt.

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)