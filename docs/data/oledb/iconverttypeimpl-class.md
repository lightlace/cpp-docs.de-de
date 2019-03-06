---
title: IConvertTypeImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- ATL.IConvertTypeImpl<T>
- IConvertTypeImpl
- ATL.IConvertTypeImpl
- ATL::IConvertTypeImpl
- ATL::IConvertTypeImpl<T>
- IConvertTypeImpl.CanConvert
- CanConvert
- IConvertTypeImpl::CanConvert
helpviewer_keywords:
- IConvertTypeImpl class
- CanConvert method
ms.assetid: 7f81e79e-7d3f-4cbe-b93c-d632a94b15f6
ms.openlocfilehash: e1117cfb8e68cbdc5432355315213faad903ea35
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57424651"
---
# <a name="iconverttypeimpl-class"></a>IConvertTypeImpl-Klasse

Stellt eine Implementierung der [IConvertType](/previous-versions/windows/desktop/ms715926(v=vs.85)) Schnittstelle.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
class ATL_NO_VTABLE IConvertTypeImpl
   : public IConvertType, public CConvertHelper
```

### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `IConvertTypeImpl`.

## <a name="requirements"></a>Anforderungen

**Header:** „atldb.h“

## <a name="members"></a>Member

### <a name="interface-methods"></a>Schnittstellenmethoden

|||
|-|-|
|[CanConvert](#canconvert)|Erhalten Informationen über die Verfügbarkeit von typkonvertierungen für einen Befehl oder in einem Rowset.|

## <a name="remarks"></a>Hinweise

Diese Schnittstelle ist obligatorisch. Befehle, Rowsets und Indexes-Schemarowsets. `IConvertTypeImpl` implementiert die Schnittstelle durch delegieren, auf das Konvertierungsobjekt von OLE DB bereitgestellt.

## <a name="canconvert"></a> IConvertTypeImpl::CanConvert

Erhalten Informationen über die Verfügbarkeit von typkonvertierungen für einen Befehl oder in einem Rowset.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(CanConvert)(DBTYPE wFromType,
   DBTYPE wToType,
   DBCONVERTFLAGS dwConvertFlags);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IConvertType::CanConvert](/previous-versions/windows/desktop/ms711224(v=vs.85)) in die *OLE DB-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Verwendet OLE DB-Datenkonvertierung in `MSADC.DLL`.

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)