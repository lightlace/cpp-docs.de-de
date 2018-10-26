---
title: 'Recordset: Hinzufügen von Datensätzen in einer Sammeloperation (ODBC) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets, adding records
- recordsets, adding records
- bulk record additions to recordsets
ms.assetid: 4685f656-14b9-4f10-a1c5-147b2b89a0b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 53daf818b0ba17848723e3cad233452146d1c891
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062573"
---
# <a name="recordset-adding-records-in-bulk-odbc"></a>Recordset: Hinzufügen von Datensätzen in einer Sammeloperation (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.

Die MFC-Bibliothek [CRecordset](../../mfc/reference/crecordset-class.md) -Klasse verfügt über eine neue Optimierung, die Effizienz verbessert werden, wenn Sie neue Datensätze in eine Tabelle in einer Massenoperation hinzufügen.

> [!NOTE]
> Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn Sie die gesammelte verwenden werden, finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Eine neue Option für die *DwOptions* Parameter, um die [CRecordset:: Open](../../mfc/reference/crecordset-class.md#open) Memberfunktion `optimizeBulkAdd`, verbessert die Leistung bei der Sie mehrere Datensätze ohne hintereinanderhinzufügen`Requery` oder `Close`. Nur die Felder, die vor dem ersten dirty `Update` Aufruf werden als modifizierte für nachfolgende `AddNew` / `Update` aufrufen.

Wenn Sie die Datenbankklassen verwendet werden, nutzen die `::SQLSetPos` ODBC-API-Funktion zum Hinzufügen, bearbeiten und Löschen von Datensätzen, ist diese Optimierung nicht erforderlich.

Wenn die ODBC-Cursorbibliothek geladen ist, oder der ODBC-Treiber unterstützt nicht das Hinzufügen, bearbeiten und Löschen von über `::SQLSetPos`, diese Optimierung sollten Bulk verbessern Leistung hinzufügen. Um diese Optimierung zu deaktivieren, setzen die *DwOptions* Parameter in der `Open` für Recordsets der folgenden aufrufen:

```
appendOnly | optimizeBulkAdd
```

## <a name="see-also"></a>Siehe auch

[Recordset (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Recordset: Hinzufügen, Aktualisieren und Löschen von Datensätzen (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)<br/>
[Recordset: Sperren von Datensätzen (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)