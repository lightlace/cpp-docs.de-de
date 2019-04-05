---
title: ICommandPropertiesImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- ICommandPropertiesImpl
- ATL.ICommandPropertiesImpl
- ATL::ICommandPropertiesImpl
- ICommandPropertiesImpl::GetProperties
- ICommandPropertiesImpl.GetProperties
- GetProperties
- ICommandPropertiesImpl.SetProperties
- ICommandPropertiesImpl::SetProperties
- SetProperties
helpviewer_keywords:
- ICommandPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: b3cf6aea-527e-4f0d-96e0-669178b021a2
ms.openlocfilehash: 1250f1c5c5094a0ca8348f325260e6079afe2baa
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034101"
---
# <a name="icommandpropertiesimpl-class"></a>ICommandPropertiesImpl-Klasse

Stellt eine Implementierung der [ICommandProperties](/previous-versions/windows/desktop/ms723044(v=vs.85)) Schnittstelle.

## <a name="syntax"></a>Syntax

```cpp
template <class T, class PropClass = T>
class ATL_NO_VTABLE ICommandPropertiesImpl
   : public ICommandProperties, public CUtlProps<PropClass>
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Klasse abgeleitet

*PropClass*<br/>
Ihre Eigenschaftenklasse.

## <a name="requirements"></a>Anforderungen

**Header:** „atldb.h“

## <a name="members"></a>Member

### <a name="interface-methods"></a>Schnittstellenmethoden

|||
|-|-|
|[GetProperties](#getproperties)|Gibt die Liste der Eigenschaften in der Gruppe der Rowset-Eigenschaften, die derzeit für das Rowset angefordert werden.|
|[SetProperties](#setproperties)|Legt die Eigenschaften in der Gruppe der Rowset-Eigenschaften fest.|

## <a name="remarks"></a>Hinweise

Dies ist obligatorisch einschaltbefehle. Die Implementierung erfolgt durch eine statische Funktion, die definiert, die von der [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) Makro.

## <a name="getproperties"></a> ICommandPropertiesImpl::GetProperties

Gibt alle angeforderten Eigenschaftensätze, die mithilfe des Befehlsparameters eigenschaftenzuordnung zurück.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(GetProperties)(const ULONG cPropertyIDSets,
   const DBPROPIDSET rgPropertyIDSets[],
   ULONG * pcPropertySets,
   DBPROPSET ** prgPropertySets);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [ICommandProperties:: GetProperties](/previous-versions/windows/desktop/ms723119(v=vs.85)) in die *OLE DB-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Siehe [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

## <a name="setproperties"></a> ICommandPropertiesImpl::SetProperties

Stellt Eigenschaften für das Command-Objekt.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,
   DBPROPSET rgPropertySets[]);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [ICommandProperties:: SetProperties](/previous-versions/windows/desktop/ms711497(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)