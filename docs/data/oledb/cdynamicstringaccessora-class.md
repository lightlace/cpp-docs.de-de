---
title: CDynamicStringAccessorA-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicStringAccessorA
dev_langs:
- C++
helpviewer_keywords:
- CDynamicStringAccessorA class
ms.assetid: ed0d9821-a655-41f1-a902-43c3042ac49c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 612050c74cf33d128f108962fab54ef6c0e8e5d9
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43214564"
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
