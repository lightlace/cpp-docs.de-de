---
title: IRowsetIdentityImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IRowsetIdentityImpl
- ATL.IRowsetIdentityImpl
- IRowsetIdentityImpl
- IsSameRow
- IRowsetIdentityImpl.IsSameRow
- ATL.IRowsetIdentityImpl.IsSameRow
- IRowsetIdentityImpl::IsSameRow
- ATL::IRowsetIdentityImpl::IsSameRow
dev_langs:
- C++
helpviewer_keywords:
- IRowsetIdentityImpl class
- IsSameRow method
ms.assetid: 56821edf-e045-40c8-96bd-231552cd5799
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1431fb9b35ab83f6cb0fc167eff4ba4508f2e301
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036188"
---
# <a name="irowsetidentityimpl-class"></a>IRowsetIdentityImpl-Klasse

Implementiert die OLE DB [IRowsetIdentity](/previous-versions/windows/desktop/ms715913\(v=vs.85\)) -Schnittstelle, die Tests für die Zeilenidentität.  
  
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

Finden Sie unter [IRowsetIdentity::IsSameRow](/previous-versions/windows/desktop/ms719629\(v=vs.85\)) in die *OLE DB-Programmierreferenz*.  
  
### <a name="remarks"></a>Hinweise  

Um Zeilenhandles zu vergleichen, die diese Methode wandelt die `HROW` Fensterhandles zu `RowClass` Member und ruft `memcmp` für den Zeiger.  
  
## <a name="see-also"></a>Siehe auch  

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)