---
title: Zugreifen auf ODBC und SQL | Microsoft Docs
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
ms.openlocfilehash: 4fb5daa988614e7e9cb058fce183c6af5b50dd30
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="access-to-odbc-and-sql"></a>Zugreifen auf ODBC und SQL
Die Microsoft Foundation Class-Bibliothek kapselt viele Windows-API-Aufrufe und weiterhin Windows-API-Funktion nicht direkt aufrufen können. Die Datenbankklassen bieten Ihnen dieselbe Flexibilität im Hinblick auf die ODBC-API. Während die Sie von den Großteil der Komplexität der ODBC-Datenbankklassen, können Sie ODBC-API-Funktionen aufrufen, von überall in Ihrem Programm.  
  
 Auf ähnliche Weise die Datenbankklassen Sie weitgehend mit [SQL](../../data/odbc/sql.md), aber Sie können SQL direkt verwenden, wenn Sie möchten. Sie können Recordset-Objekte anpassen, indem Sie eine benutzerdefinierte SQL­Anweisung (oder Einstellung Teile der Default-Anweisung) übergeben beim Öffnen des Recordsets. Sie können auch direkt mit der SQL-Aufrufe, die [ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql) Memberfunktion der Klasse [CDatabase](../../mfc/reference/cdatabase-class.md).  
  
 Weitere Informationen finden Sie unter [ODBC: Direktes Aufrufen von ODBC-API-Funktionen](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) und [SQL: durchführen direkter SQL-Aufrufe (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [ODBC und MFC](../../data/odbc/odbc-and-mfc.md)