---
title: CNoAccessor-Klasse
ms.date: 11/04/2016
f1_keywords:
- ATL::CNoAccessor
- CNoAccessor
- ATL.CNoAccessor
helpviewer_keywords:
- CNoAccessor class
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
ms.openlocfilehash: d6eb5aaa9a66f46335b0a364e6c6e79abc297d64
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647891"
---
# <a name="cnoaccessor-class"></a>CNoAccessor-Klasse

Kann als ein Vorlagenargument verwendet werden (`TAccessor`) für die Vorlagenklassen, z. B. `CCommand` und `CTable`, erfordern ein Argument der Accessor-Klasse.

## <a name="syntax"></a>Syntax

```cpp
class CNoAccessor
```

## <a name="remarks"></a>Hinweise

Verwendung `CNoAccessor` als ein Vorlagenargument, wenn Sie nicht die Klasse zum unterstützen Parameter oder Spalten ausgeben möchten.

`CNoAccessor` implementiert die folgenden Stubmethoden, von denen jedes anderen Klassenmethoden Accessor entsprechen:

- `BindColumns` -Bindet Spalten Accessoren.

- `BindParameters` – Binden die erstellte Parameter an Spalten.

- `Bind` -Bindungen erstellt.

- `Close` -Schließt die Zugriffsmethode.

- `ReleaseAccessors` -Gibt die Accessoren, die von der Klasse erstellt.

- `FreeRecordMemory` -Gibt frei, alle Spalten im aktuellen Datensatz, der freigegeben werden müssen.

- `GetColumnInfo` -Ruft Informationen aus dem Rowset geöffnet.

- `GetNumAccessors` -Ruft die Anzahl der Accessoren, die von der Klasse erstellt.

- `IsAutoAccessor` -Gibt "true" zurück, wenn die Daten automatisch für den Accessor während eines Verschiebevorgangs abgerufen werden.

- `GetHAccessor` -Ruft Sie Accessorhandles für einen angegebenen Accessor ab.

- `GetBuffer` -Ruft Sie den Zeiger auf den Lesezeichen Puffer ab.

- `NoBindOnNullRowset` – Verhindert eine Datenbindung für leere Rowsets.

## <a name="requirements"></a>Anforderungen

**Header:** atldbcli.h

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)