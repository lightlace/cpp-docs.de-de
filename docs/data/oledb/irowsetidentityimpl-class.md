---
title: IRowsetIdentityImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- ATL::IRowsetIdentityImpl
- ATL.IRowsetIdentityImpl
- IRowsetIdentityImpl
- IsSameRow
- IRowsetIdentityImpl.IsSameRow
- ATL.IRowsetIdentityImpl.IsSameRow
- IRowsetIdentityImpl::IsSameRow
- ATL::IRowsetIdentityImpl::IsSameRow
helpviewer_keywords:
- IRowsetIdentityImpl class
- IsSameRow method
ms.assetid: 56821edf-e045-40c8-96bd-231552cd5799
ms.openlocfilehash: b70ebdaa44331d9fa545763f0dd19e6320dd652b
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556217"
---
# <a name="irowsetidentityimpl-class"></a>IRowsetIdentityImpl-Klasse

Implementiert die OLE DB [IRowsetIdentity](https://docs.microsoft.com/previous-versions/windows/desktop/ms715913(v=vs.85)) -Schnittstelle, die Tests für die Zeilenidentität.

## <a name="syntax"></a>Syntax

```cpp
template <class T, class RowClass = CSimpleRow>
class ATL_NO_VTABLE IRowsetIdentityImpl
   : public IRowsetIdentity
```

### <a name="parameters"></a>Parameter

*T*<br/>
Eine abgeleitete Klasse `IRowsetIdentityImpl`.

*RowClass*<br/>
Die Storage-Einheit für die `HROW`.

## <a name="requirements"></a>Anforderungen

**Header:** „atldb.h“

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[IsSameRow](#issamerow)|Vergleicht zwei Zeilenhandles, um festzustellen, ob sie sich auf derselben Zeile beziehen.|

## <a name="issamerow"></a> Irowsetidentityimpl:: Issamerow

Vergleicht zwei Zeilenhandles, um festzustellen, ob sie sich auf derselben Zeile beziehen.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(IsSameRow )(HROW hThisRow,
   HROW hThatRow);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IRowsetIdentity::IsSameRow](https://docs.microsoft.com/previous-versions/windows/desktop/ms719629(v=vs.85)) in die *OLE DB-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Um Zeilenhandles zu vergleichen, die diese Methode wandelt die `HROW` Fensterhandles zu `RowClass` Member und ruft `memcmp` für den Zeiger.

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)