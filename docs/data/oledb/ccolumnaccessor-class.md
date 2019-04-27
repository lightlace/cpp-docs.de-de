---
title: CColumnAccessor-Klasse
ms.date: 11/04/2016
f1_keywords:
- CColumnAccessor
- ATL::CColumnAccessor
- ATL.CColumnAccessor
helpviewer_keywords:
- CColumnAccessor class
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
ms.openlocfilehash: 2d65fb047e758f449ed76c954bb4ac0c3623f6dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209294"
---
# <a name="ccolumnaccessor-class"></a>CColumnAccessor-Klasse

Generiert Consumercode für eingefügte.

## <a name="syntax"></a>Syntax

```cpp
class CColumnAccessor : public CAccessorBase
```

## <a name="remarks"></a>Hinweise

In den injizierten Code verwenden wird jede Spalte als einen separaten Accessor gebunden. Sie sollten bedenken, dass diese Klasse in den injizierten Code verwendet wird (z. B. stoßen sollten sie beim Debuggen), aber Sie in der Regel nie direkt sie oder ihre Methoden zu verwenden.

`CColumnAccessor` implementiert die folgenden Stubmethoden, von denen jede an der Funktionalität und der andere Accessor-Klassenmethoden entsprechen:

- `CColumnAccessor` Der Konstruktor; instanziiert und initialisiert die `CColumnAccessor` Objekt.

- `CreateAccessor` Belegt Speicher für die Spalte bindungsstrukturen aus, und der Spaltenelemente für die Daten initialisiert.

- `BindColumns` Bindet Spalten Accessoren.

- `SetParameterBuffer` Ordnet Puffer für Parameter.

- `AddParameter` Die Parameter-Eintrag-Strukturen wird ein Parametereintrag hinzugefügt.

- `HasOutputColumns` Bestimmt, ob der Accessor Spalten ausgegeben hat

- `HasParameters` Bestimmt, ob der Accessor über Parameter verfügt.

- `BindParameters` Wird die erstellte Parameter an Spalten gebunden.

## <a name="requirements"></a>Anforderungen

**Header:** atldbcli.h

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)