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
ms.openlocfilehash: 51f8d7e832476619ccec277c9d73791041d146a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390836"
---
# <a name="irowsetidentityimpl-class"></a>IRowsetIdentityImpl-Klasse

Implementiert die OLE DB [IRowsetIdentity](/previous-versions/windows/desktop/ms715913(v=vs.85)) -Schnittstelle, die Tests für die Zeilenidentität.

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

## <a name="issamerow"></a> IRowsetIdentityImpl::IsSameRow

Vergleicht zwei Zeilenhandles, um festzustellen, ob sie sich auf derselben Zeile beziehen.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(IsSameRow )(HROW hThisRow,
   HROW hThatRow);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IRowsetIdentity::IsSameRow](/previous-versions/windows/desktop/ms719629(v=vs.85)) in die *OLE DB-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Um Zeilenhandles zu vergleichen, die diese Methode wandelt die `HROW` Fensterhandles zu `RowClass` Member und ruft `memcmp` für den Zeiger.

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)