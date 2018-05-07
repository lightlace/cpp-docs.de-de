---
title: Herstellen einer Verbindung mit einer Datenquelle | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- database connections [C++], ODBC
- ODBC connections [C++], using
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- ODBC data sources [C++], connections
- database connections [C++], MFC ODBC classes
ms.assetid: ef6c8c98-5979-43a8-9fb5-5bb06fc59f36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2b6a33f1e2421c56f89184d26185903b4ec7859e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="connecting-to-a-data-source"></a>Aufbauen der Verbindung zu einer Datenquelle
Eine ODBC-Datenquelle handelt es sich um einen bestimmten Satz von Daten, die erforderlichen Informationen zum Zugriff auf diese Daten und den Speicherort der Datenquelle, die mithilfe einer Datenquellennamens beschrieben werden kann. Aus Sicht des Programms enthält die Datenquelle die Daten, das DBMS die Netzwerk (sofern vorhanden) und ODBC.  
  
 Für den Zugriff auf Daten, die von einer Datenquelle bereitgestellt, muss das Programm zuerst eine Verbindung mit der Datenquelle herstellen. Alle der Datenzugriff wird über diese Verbindung verwaltet.  
  
 Datenquellen-Verbindungen sind von Klasse gekapselte [CDatabase](../../mfc/reference/cdatabase-class.md). Wenn ein `CDatabase` Objekt mit einer Datenquelle verbunden ist, können Sie:  
  
-   Erstellen Sie [Recordsets](../../mfc/reference/crecordset-class.md), die Datensätze aus Tabellen oder Abfragen auswählen.  
  
-   Verwalten von [Transaktionen](../../data/odbc/transaction-odbc.md), Batchverarbeitung Updates, d. h. alle auf einmal an die Datenquelle übergeben werden (oder die gesamte Transaktion zurückgesetzt wird, zurück, damit die Datenquelle nicht geändert wurden) – Wenn die Datenquelle über das erforderliche Servicelevel Transaktionen unterstützt.  
  
-   Direktes Ausführen von [SQL](../../data/odbc/sql.md) Anweisungen.  
  
 Wenn Sie die Arbeit mit einer Datenquelle Verbindung abgeschlossen haben, schließen Sie die `CDatabase` Objekt und zerstören, oder es für eine neue Verbindung wiederverwenden. Weitere Informationen zu den Datenquellen-Verbindungen finden Sie unter [Datenquelle (ODBC)](../../data/odbc/data-source-odbc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [ODBC und MFC](../../data/odbc/odbc-and-mfc.md)