---
title: CDynamicStringAccessorA-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDynamicStringAccessorA
helpviewer_keywords:
- CDynamicStringAccessorA class
ms.assetid: ed0d9821-a655-41f1-a902-43c3042ac49c
ms.openlocfilehash: bfe4cf2d6aa107c21ed0d8b226616ebaa8488102
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537435"
---
# <a name="cdynamicstringaccessora-class"></a>CDynamicStringAccessorA-Klasse

Können Sie eine Datenquelle zugreifen, wenn Sie keine Kenntnisse über das Datenbankschema (zugrunde liegende Struktur) verfügen.

## <a name="syntax"></a>Syntax

```cpp
typedef CDynamicStringAccessorT<CHAR, DBTYPE_STR> CDynamicStringAccessorA;
```

## <a name="remarks"></a>Hinweise

Beide anfordern, dass der Anbieter alle Daten aus dem Datenspeicher Daten, die Zeichenfolge abruft, aber `CDynamicStringAccessor` Anforderungen ANSI-Zeichenfolgendaten.

`CDynamicStringAccessorA` erbt `GetString` und `SetString` aus `CDynamicStringAccessor`. Bei Verwendung dieser Methoden in einer `CDynamicStringAccessorA` Objekt `BaseType` ist **CHAR**.

## <a name="requirements"></a>Anforderungen

**Header**: atldbcli.h

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor-Klasse](../../data/oledb/caccessor-class.md)<br/>
[CDynamicParameterAccessor-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[CManualAccessor-Klasse](../../data/oledb/cmanualaccessor-class.md)<br/>
[CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicStringAccessor-Klasse](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
