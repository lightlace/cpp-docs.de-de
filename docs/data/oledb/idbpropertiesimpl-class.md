---
title: IDBPropertiesImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IDBPropertiesImpl
- ATL.IDBPropertiesImpl
- ATL.IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl
- IDBPropertiesImpl::GetProperties
- IDBPropertiesImpl.GetProperties
- GetProperties
- IDBPropertiesImpl::GetPropertyInfo
- IDBPropertiesImpl.GetPropertyInfo
- GetPropertyInfo
- IDBPropertiesImpl.SetProperties
- SetProperties
- IDBPropertiesImpl::SetProperties
helpviewer_keywords:
- IDBPropertiesImpl class
- GetProperties method
- GetPropertyInfo method
- SetProperties method
ms.assetid: a7f15a8b-95b2-4316-b944-d5d03f8d74ab
ms.openlocfilehash: 13c41b97190ff13b87361b6e8344b8f17798708a
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413341"
---
# <a name="idbpropertiesimpl-class"></a>IDBPropertiesImpl-Klasse

Stellt eine Implementierung für die `IDBProperties` Schnittstelle.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
class ATL_NO_VTABLE IDBPropertiesImpl
   : public IDBProperties, public CUtlProps<T>
```

### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `IDBPropertiesImpl`.

## <a name="requirements"></a>Anforderungen

**Header:** „atldb.h“

## <a name="members"></a>Member

### <a name="interface-methods"></a>Schnittstellenmethoden

|||
|-|-|
|[GetProperties](#getproperties)|Gibt die Werte der Eigenschaften in der Datenquelle, die Informationen der Datenquelle und die Initialisierung Eigenschaftengruppen, die momentan festgelegt sind, auf das Objekt oder die Werte der Eigenschaften in der Gruppe der Initialisierungseigenschaften, die derzeit für festgelegt werden die Enumerator.|
|[GetPropertyInfo](#getpropertyinfo)|Gibt Informationen zu allen Eigenschaften, die vom Anbieter unterstützt werden.|
|[SetProperties](#setproperties)|Legt Eigenschaften in der Datenquelle und Initialisierung Eigenschaftengruppen, für Datenquellenobjekte, oder der Gruppe der Initialisierungseigenschaften, für Enumeratoren fest.|

## <a name="remarks"></a>Hinweise

[IDBProperties](/previous-versions/windows/desktop/ms719607(v=vs.85)) ist eine erforderliche Schnittstelle für Datenquellenobjekte und eine optionale Schnittstelle für Enumeratoren. Aber wenn Sie einen Enumerator verfügbar macht [IDBInitialize](/previous-versions/windows/desktop/ms713706(v=vs.85)), verfügbar machen `IDBProperties`. `IDBPropertiesImpl` implementiert `IDBProperties` mithilfe einer statischen Funktion durch definiert [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

## <a name="getproperties"></a> IDBPropertiesImpl::GetProperties

Gibt die Werte der Eigenschaften in der Datenquelle, die Informationen der Datenquelle und die Initialisierung Eigenschaftengruppen, die momentan festgelegt sind, auf das Objekt oder die Werte der Eigenschaften in der Gruppe der Initialisierungseigenschaften, die derzeit für festgelegt werden die Enumerator.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(GetProperties)(ULONG cPropertySets,
   const DBPROPIDSET rgPropertySets[],
   ULONG * pcProperties,
   DBPROPSET ** prgProperties);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IDBProperties:: GetProperties](/previous-versions/windows/desktop/ms714344(v=vs.85)) in die *OLE DB-Programmierreferenz*.

Einige Parameter entsprechen den *OLE DB-Programmierreferenz* Parameter mit unterschiedlichen Namen, die in beschriebenen `IDBProperties::GetProperties`:

|OLE DB-Vorlagenparameter|*OLE DB-Programmierreferenz* Parameter|
|--------------------------------|------------------------------------------------|
|*cPropertySets*|*cPropertyIDSets*|
|*rgPropertySets*|*rgPropertyIDSets*|
|*pcProperties*|*pcPropertySets*|
|*prgProperties*|*prgPropertySets*|

### <a name="remarks"></a>Hinweise

Wenn der Anbieter initialisiert wird, gibt diese Methode die Werte der Eigenschaften, in der DBPROPSET_DATASOURCE, DBPROPSET_DATASOURCEINFO, DBPROPSET_DBINIT-Eigenschaftengruppen, die derzeit auf das Objekt festgelegt werden. Wenn der Anbieter nicht initialisiert ist, wird nur Gruppeneigenschaften DBPROPSET_DBINIT zurückgegeben.

## <a name="getpropertyinfo"></a> IDBPropertiesImpl::GetPropertyInfo

Gibt Eigenschafteninformationen, die von der Datenquelle unterstützt.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(GetPropertyInfo)(ULONG cPropertySets,
   const DBPROPIDSET rgPropertySets[],
   ULONG * pcPropertyInfoSets,
   DBPROPINFOSET ** prgPropertyInfoSets,
   OLECHAR ** ppDescBuffer);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IDBProperties](/previous-versions/windows/desktop/ms718175(v=vs.85)) in die *OLE DB-Programmierreferenz*.

Einige Parameter entsprechen den *OLE DB-Programmierreferenz* Parameter mit unterschiedlichen Namen, die in beschriebenen `IDBProperties::GetPropertyInfo`:

|OLE DB-Vorlagenparameter|*OLE DB-Programmierreferenz* Parameter|
|--------------------------------|------------------------------------------------|
|*cPropertySets*|*cPropertyIDSets*|
|*rgPropertySets*|*rgPropertyIDSets*|

### <a name="remarks"></a>Hinweise

Verwendet [idbinitializeimpl:: M_pcutlpropinfo](../../data/oledb/idbinitializeimpl-m-pcutlpropinfo.md) zur Implementierung dieser Funktionalität.

## <a name="setproperties"></a> IDBPropertiesImpl::SetProperties

Legt Eigenschaften in der Datenquelle und Initialisierung Eigenschaftengruppen, für Datenquellenobjekte, oder der Gruppe der Initialisierungseigenschaften, für Enumeratoren fest.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,
   DBPROPSET rgPropertySets[]);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IDBProperties:: SetProperties](/previous-versions/windows/desktop/ms723049(v=vs.85)) in die *OLE DB-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Wenn der Anbieter initialisiert wird, diese Methode legt die Werte der Eigenschaften im der DBPROPSET_DATASOURCE, DBPROPSET_DATASOURCEINFO, DBPROPSET_DBINIT-Eigenschaftengruppen für das Datenquellenobjekt. Wenn der Anbieter nicht initialisiert ist, wird nur DBPROPSET_DBINIT-Gruppeneigenschaften.

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)