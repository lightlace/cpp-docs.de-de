---
title: IDBCreateCommandImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- ATL::IDBCreateCommandImpl
- IDBCreateCommandImpl
- ATL.IDBCreateCommandImpl
- IDBCreateCommandImpl.CreateCommand
- CreateCommand
- IDBCreateCommandImpl::CreateCommand
helpviewer_keywords:
- IDBCreateCommandImpl class
- CreateCommand method
ms.assetid: eac4755e-1668-42e1-958e-a35620c385ae
ms.openlocfilehash: 4b8c713bcf00cd68f9621b8c112d4d6fd27aec01
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556400"
---
# <a name="idbcreatecommandimpl-class"></a>IDBCreateCommandImpl-Klasse

Stellt eine Implementierung der [IDBCreateCommand](https://docs.microsoft.com/previous-versions/windows/desktop/ms711625(v=vs.85)) Schnittstelle.

## <a name="syntax"></a>Syntax

```cpp
template <class T, class CommandClass >
class ATL_NO_VTABLE IDBCreateCommandImpl
   : public IDBCreateCommand
```

### <a name="parameters"></a>Parameter

*T*<br/>
Das Sitzungsobjekt abgeleitet `IDBCreateCommandImpl`.

*CommandClass*<br/>
Command-Klasse.

## <a name="requirements"></a>Anforderungen

**Header:** „atldb.h“

## <a name="members"></a>Member

### <a name="interface-methods"></a>Schnittstellenmethoden

|||
|-|-|
|[CreateCommand](#createcommand)|Erstellt einen neuen Befehl.|

## <a name="remarks"></a>Hinweise

Eine optionale Schnittstelle für das Sitzungsobjekt, um einen neuen Befehl zu erhalten.

## <a name="createcommand"></a> Idbcreatecommandimpl:: CreateCommand

Erstellt einen neuen Befehl ein, und gibt die angeforderte Schnittstelle zurück.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(CreateCommand)(IUnknown * pUnkOuter,
   REFIID riid,
   IUnknown ** ppvCommand);
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [IDBCreateCommand:: CreateCommand](https://docs.microsoft.com/previous-versions/windows/desktop/ms709772(v=vs.85)) in die *OLE DB-Programmierreferenz*.

Einige Parameter entsprechen den *OLE DB-Programmierreferenz* Parameter mit unterschiedlichen Namen, die in beschriebenen `IDBCreateCommand::CreateCommand`:

|OLE DB-Vorlagenparameter|*OLE DB-Programmierreferenz* Parameter|
|--------------------------------|------------------------------------------------|
|*ppvCommand*|*ppCommand*|

## <a name="see-also"></a>Siehe auch

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)