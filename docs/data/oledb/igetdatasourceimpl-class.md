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
ms.openlocfilehash: cd6b56f4281a2fdde77229ec54be6d6289a87148
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556568"
---
# <a name="igetdatasourceimpl-class"></a>IGetDataSourceImpl-Klasse

Stellt eine Implementierung der [IGetDataSource](https://docs.microsoft.com/previous-versions/windows/desktop/ms709721(v=vs.85)) Objekt.

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

Finden Sie unter [IGetDataSource::GetDataSource](https://docs.microsoft.com/previous-versions/windows/desktop/ms725443(v=vs.85)) in die *OLE DB-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Nützlich, wenn Sie auf Eigenschaften in das neue Datenquellenobjekt zugreifen müssen.

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)