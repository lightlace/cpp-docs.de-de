---
title: Zugreifen auf ODBC und SQL
ms.date: 11/04/2016
helpviewer_keywords:
- API calls [C++], calling DAO or ODBC directly
- Windows API [C++], calling from MFC
- ODBC API functions [C++]
- ODBC API functions [C++], calling from MFC
- SQL [C++], calling ODBC API functions
- ODBC [C++], API functions
ms.assetid: 5613d7dc-00b7-4646-99ae-1116c05c52b4
ms.openlocfilehash: 7a539d911bbf4f4d9582da0ebedaeffaa0d8fa7b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59030153"
---
# <a name="access-to-odbc-and-sql"></a>Zugreifen auf ODBC und SQL

Die Microsoft Foundation Class Library kapselt viele Windows-API-Aufrufe und weiterhin können Sie alle Windows-API-Funktion nicht direkt aufrufen. Die Datenbankklassen bieten Ihnen die gleiche Flexibilität im Hinblick auf die ODBC-API. Während der Großteil der Komplexität der ODBC-Datenbankklassen, können Sie die ODBC-API-Funktionen aufrufen, direkt von überall in Ihrem Programm.

Auf ähnliche Weise die Datenbankklassen Sie weitgehend mit [SQL](../../data/odbc/sql.md), aber Sie können SQL direkt verwenden, wenn Sie möchten. Sie können die Recordset-Objekte anpassen, indem Sie übergeben eine benutzerdefinierte SQL­Anweisung (oder Einstellung Teile der Default-Anweisung) beim Öffnen des Recordsets. Sie können auch direkt mit SQL-Aufrufe, die [ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql) Memberfunktion der Klasse [CDatabase](../../mfc/reference/cdatabase-class.md).

Weitere Informationen finden Sie unter [ODBC: Aufrufen von ODBC-API-Funktionen direkt](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) und [SQL: Durchführen direkter SQL-Aufrufe (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md).

## <a name="see-also"></a>Siehe auch

[ODBC und MFC](../../data/odbc/odbc-and-mfc.md)