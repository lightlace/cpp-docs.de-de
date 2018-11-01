---
title: IGetDataSourceImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IGetDataSourceImpl
- ATL.IGetDataSourceImpl<T>
- ATL.IGetDataSourceImpl
- ATL::IGetDataSourceImpl
- ATL::IGetDataSourceImpl<T>
- GetDataSource
- IGetDataSourceImpl.GetDataSource
- IGetDataSourceImpl::GetDataSource
helpviewer_keywords:
- IGetDataSourceImpl class
- GetDataSource method
ms.assetid: d63f3178-d663-4f01-8c09-8aab2dd6805a
ms.openlocfilehash: 75b95f871023d7bfdea198a69377b1f360ab115f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637839"
---
# <a name="igetdatasourceimpl-class"></a>IGetDataSourceImpl-Klasse

Stellt eine Implementierung der [IGetDataSource](/previous-versions/windows/desktop/ms709721) Objekt.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
class ATL_NO_VTABLE IGetDataSourceImpl : public IGetDataSource
```

### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `IGetDataSourceImpl`.

## <a name="requirements"></a>Anforderungen

**Header:** „atldb.h“

## <a name="members"></a>Member

### <a name="interface-methods"></a>Schnittstellenmethoden

|||
|-|-|
|[GetDataSource](#getdatasource)|Gibt einen Schnittstellenzeiger auf das Datenquellenobjekt, das die Sitzung erstellt haben.|

## <a name="remarks"></a>Hinweise

Dies ist eine erforderliche Schnittstelle für die Sitzung erhalten Sie einen Schnittstellenzeiger auf das Datenquellenobjekt.

## <a name="getdatasource"></a> Igetdatasourceimpl:: GetDatasource

Gibt einen Schnittstellenzeiger auf das Datenquellenobjekt, das die Sitzung erstellt haben.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(GetDataSource)(REFIID riid, 
   IUnknown ** ppDataSource);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IGetDataSource::GetDataSource](/previous-versions/windows/desktop/ms725443) in die *OLE DB-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Nützlich, wenn Sie auf Eigenschaften in das neue Datenquellenobjekt zugreifen müssen.

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)