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
ms.openlocfilehash: ecc06bf5e3514ea87c86de17dbafd59b9da9f8b6
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556421"
---
# <a name="idbcreatesessionimpl-class"></a>IDBCreateSessionImpl-Klasse

Stellt eine Implementierung für die [IDBCreateSession](https://docs.microsoft.com/previous-versions/windows/desktop/ms724076(v=vs.85)) Schnittstelle.

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

## <a name="createsession"></a> Idbcreatesessionimpl:: CreateSession

Erstellt eine neue Sitzung über das Datenquellenobjekt, und gibt die angeforderte Schnittstelle zurück, auf die neu erstellte Sitzung.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(CreateSession)(IUnknown * pUnkOuter,
   REFIID riid,
   IUnknown ** ppDBSession);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IDBCreateSession:: CreateSession](https://docs.microsoft.com/previous-versions/windows/desktop/ms714942(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)