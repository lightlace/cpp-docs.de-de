---
title: CNoRowset-Klasse
ms.date: 11/04/2016
f1_keywords:
- ATL.CNoRowset
- ATL::CNoRowset<TAccessor>
- CNoRowset
- ATL.CNoRowset<TAccessor>
- ATL::CNoRowset
helpviewer_keywords:
- CNoRowset class
ms.assetid: 55c6c7a4-9e3a-4775-a2dd-c8b333012fa6
ms.openlocfilehash: 6193e2d461761c53fb05e5c16b3914c56d545173
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230476"
---
# <a name="cnorowset-class"></a>CNoRowset-Klasse

Kann als ein Vorlagenargument verwendet werden (`TRowset`) für [CCommand](../../data/oledb/ccommand-class.md) oder [CTable](../../data/oledb/ctable-class.md).

## <a name="syntax"></a>Syntax

```cpp
template <class TAccessor = CAccessorBase>
class CNoRowset
```

### <a name="parameters"></a>Parameter

*TAccessor*<br/>
Ein Accessor-Klasse. Die Standardeinstellung ist `CAccessorBase`.

## <a name="remarks"></a>Hinweise

Verwendung `CNoRowset` als ein Vorlagenargument, wenn der Befehl kein Rowset zurückgibt.

`CNoRowset` implementiert die folgenden Stubmethoden, von denen jedes anderen Klassenmethoden Accessor entsprechen:

- `BindFinished` -Gibt an, wenn die Bindung abgeschlossen ist (gibt `S_OK`).

- `Close` -Versionen der Zeilen und die aktuelle IRowset-Schnittstelle.

- `GetIID` -Ruft Sie die Schnittstellen-ID eines Verbindungspunkts ab.

- `GetInterface` -Ruft eine Schnittstelle ab.

- `GetInterfacePtr` -Ruft ab einen gekapselten Schnittstellenzeiger auf.

- `SetAccessor` – Legt fest, die dem Accessor einen Zeiger.

- `SetupOptionalRowsetInterfaces` – Legt fest, um optionale Schnittstellen für das Rowset.

## <a name="requirements"></a>Anforderungen

**Header:** atldbcli.h

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)