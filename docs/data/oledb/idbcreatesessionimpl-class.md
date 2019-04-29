---
title: IDBCreateSessionImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IDBCreateSessionImpl
- ATL.IDBCreateSessionImpl
- ATL::IDBCreateSessionImpl
- IDBCreateSessionImpl::CreateSession
- IDBCreateSessionImpl.CreateSession
- CreateSession
helpviewer_keywords:
- IDBCreateSessionImpl class
- CreateSession method
ms.assetid: 48c02c5c-8362-45ac-af8e-bb119cf8c5c7
ms.openlocfilehash: ae59abc542a4599d289c099801fc34d56b2b13d4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409160"
---
# <a name="idbcreatesessionimpl-class"></a>IDBCreateSessionImpl-Klasse

Stellt eine Implementierung für die [IDBCreateSession](/previous-versions/windows/desktop/ms724076(v=vs.85)) Schnittstelle.

## <a name="syntax"></a>Syntax

```cpp
template <class T, class SessionClass>
class ATL_NO_VTABLE IDBCreateSessionImpl
   : public IDBCreateSession
```

### <a name="parameters"></a>Parameter

*T*<br/>
DER KLASSE ABGELEITET

*SessionClass*<br/>
Der Session-Objekt.

## <a name="requirements"></a>Anforderungen

**Header:** „atldb.h“

## <a name="members"></a>Member

### <a name="interface-methods"></a>Schnittstellenmethoden

|||
|-|-|
|[CreateSession](#createsession)|Erstellt eine neue Sitzung über das Datenquellenobjekt, und gibt die angeforderte Schnittstelle zurück, auf die neu erstellte Sitzung.|

## <a name="remarks"></a>Hinweise

Eine erforderliche Schnittstelle für Datenquellenobjekte.

## <a name="createsession"></a> IDBCreateSessionImpl::CreateSession

Erstellt eine neue Sitzung über das Datenquellenobjekt, und gibt die angeforderte Schnittstelle zurück, auf die neu erstellte Sitzung.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(CreateSession)(IUnknown * pUnkOuter,
   REFIID riid,
   IUnknown ** ppDBSession);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IDBCreateSession:: CreateSession](/previous-versions/windows/desktop/ms714942(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)