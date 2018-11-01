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
ms.openlocfilehash: 5ce4db130f4e8569b666047ca7a5c2bc4e0e6cb1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50593192"
---
# <a name="irowsetidentityimpl-class"></a>IRowsetIdentityImpl-Klasse

Implementiert die OLE DB [IRowsetIdentity](/previous-versions/windows/desktop/ms715913) -Schnittstelle, die Tests für die Zeilenidentität.

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

Finden Sie unter [IRowsetIdentity::IsSameRow](/previous-versions/windows/desktop/ms719629) in die *OLE DB-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Um Zeilenhandles zu vergleichen, die diese Methode wandelt die `HROW` Fensterhandles zu `RowClass` Member und ruft `memcmp` für den Zeiger.

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)