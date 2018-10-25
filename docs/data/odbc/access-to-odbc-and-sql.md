---
title: Zugreifen auf ODBC und SQL | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- API calls [C++], calling DAO or ODBC directly
- Windows API [C++], calling from MFC
- ODBC API functions [C++]
- ODBC API functions [C++], calling from MFC
- SQL [C++], calling ODBC API functions
- ODBC [C++], API functions
ms.assetid: 5613d7dc-00b7-4646-99ae-1116c05c52b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4635d482a08c486c1cf3259ae642fd82eb4bae82
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055943"
---
# <a name="access-to-odbc-and-sql"></a>Zugreifen auf ODBC und SQL

Die Microsoft Foundation Class Library kapselt viele Windows-API-Aufrufe und weiterhin können Sie alle Windows-API-Funktion nicht direkt aufrufen. Die Datenbankklassen bieten Ihnen die gleiche Flexibilität im Hinblick auf die ODBC-API. Während der Großteil der Komplexität der ODBC-Datenbankklassen, können Sie die ODBC-API-Funktionen aufrufen, direkt von überall in Ihrem Programm.

Auf ähnliche Weise die Datenbankklassen Sie weitgehend mit [SQL](../../data/odbc/sql.md), aber Sie können SQL direkt verwenden, wenn Sie möchten. Sie können die Recordset-Objekte anpassen, indem Sie übergeben eine benutzerdefinierte SQL­Anweisung (oder Einstellung Teile der Default-Anweisung) beim Öffnen des Recordsets. Sie können auch direkt mit SQL-Aufrufe, die [ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql) Memberfunktion der Klasse [CDatabase](../../mfc/reference/cdatabase-class.md).

Weitere Informationen finden Sie unter [ODBC: Direktes Aufrufen von ODBC-API-Funktionen](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) und [SQL: durchführen direkter SQL-Aufrufe (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md).

## <a name="see-also"></a>Siehe auch

[ODBC und MFC](../../data/odbc/odbc-and-mfc.md)