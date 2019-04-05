---
title: Aufbauen der Verbindung zu einer Datenquelle
ms.date: 11/04/2016
helpviewer_keywords:
- database connections [C++], ODBC
- ODBC connections [C++], using
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- ODBC data sources [C++], connections
- database connections [C++], MFC ODBC classes
ms.assetid: ef6c8c98-5979-43a8-9fb5-5bb06fc59f36
ms.openlocfilehash: 1740a34036798dac69ffc8b486e03bf6439845a5
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024556"
---
# <a name="connecting-to-a-data-source"></a>Aufbauen der Verbindung zu einer Datenquelle

Eine ODBC-Datenquelle handelt es sich um einen bestimmten Satz von Daten, die erforderlichen Informationen zum Zugriff auf die Daten und den Speicherort der Datenquelle, die Verwendung eines Namens für die Datenquelle beschrieben werden kann. Aus Sicht des Programms enthält die Datenquelle, die Daten, das DBMS, Netzwerk (sofern vorhanden) und ODBC.

Das Programm muss zunächst eine Verbindung mit der Datenquelle herstellen, um Zugriff auf die Daten, die von einer Datenquelle bereitgestellt. Alle Datenzugriff wird über diese Verbindung verwaltet.

Datenquellen-Verbindungen sind von Klasse gekapselte [CDatabase](../../mfc/reference/cdatabase-class.md). Wenn eine `CDatabase` Objekt mit einer Datenquelle verbunden ist, können Sie:

- Erstellen Sie [Recordsets](../../mfc/reference/crecordset-class.md), die Datensätze aus Tabellen oder Abfragen auswählen.

- Verwalten von [Transaktionen](../../data/odbc/transaction-odbc.md), Batchverarbeitung Updates, sodass alle auf einmal an die Datenquelle übergeben werden (oder die gesamte Transaktion zurückgesetzt wird, wieder, damit die Datenquelle nicht geändert wird) – Wenn die Datenquelle über das erforderliche Servicelevel Transaktionen unterstützt.

- Direktes Ausführen von [SQL](../../data/odbc/sql.md) Anweisungen.

Wenn Sie die Arbeit mit einer datenquellenverbindung abgeschlossen haben, schließen Sie die `CDatabase` -Objekt, und es zu zerstören oder für eine neue Verbindung wiederzuverwenden. Weitere Informationen zu Verbindungen mit Datenquellen, finden Sie unter [Datenquelle (ODBC)](../../data/odbc/data-source-odbc.md).

## <a name="see-also"></a>Siehe auch

[ODBC und MFC](../../data/odbc/odbc-and-mfc.md)