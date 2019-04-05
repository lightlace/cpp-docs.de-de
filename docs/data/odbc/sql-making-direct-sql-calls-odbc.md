---
title: 'SQL: Durchführen direkter SQL-Aufrufe (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- SQL, direct calls from ODBC
- SQL, calling directly from ODBC
- ODBC, SQL calls
- SQL calls
- direct SQL calls from ODBC
ms.assetid: 091988d2-f5a5-4c2d-aa09-8779a9fb9607
ms.openlocfilehash: fd528e7abb713e4b3eb2bd5388a29958a1bb006c
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024980"
---
# <a name="sql-making-direct-sql-calls-odbc"></a>SQL: Durchführen direkter SQL-Aufrufe (ODBC)

In diesem Thema wird Folgendes erläutert:

- Verwenden direkten SQL aufruft.

- [Wie können Sie direkte SQL an die Datenquelle ruft](#_core_making_direct_sql_function_calls).

> [!NOTE]
>  Diese Informationen gelten für die MFC-ODBC-Klassen. Wenn Sie mit den MFC-DAO-Klassen arbeiten, finden Sie im "Vergleich von Microsoft Jet-Datenbank-Engine-SQL und ANSI-SQL" in-DAO-Hilfe.

##  <a name="_core_when_to_call_sql_directly"></a> Wenn SQL direkt aufrufen

Zum Erstellen neuer Tabellen löschen (Delete) Tabellen, Ändern von vorhandenen Tabellen, Indizes zu erstellen und andere SQL-Funktionen, die ändern, Ausführen der [Datenquelle (ODBC)](../../data/odbc/data-source-odbc.md) Schema müssen Sie eine SQL-Anweisung ausgeben, direkt an die Datenquelle, die mit der Datenbank Die Datendefinitionssprache (DDL). Wenn Sie einen Assistenten verwenden, um eine Datensatzgruppe für eine Tabelle (Entwurfszeit) zu erstellen, können Sie die Spalten der Tabelle zur Darstellung im Recordset auswählen. Dies lässt sich nicht für Spalten, die Sie oder ein anderer Benutzer der Datenquelle in die Tabelle später hinzufügen, nachdem das Programm kompiliert wurde. Die Datenbankklassen unterstützen keine DDL direkt, aber Sie können weiterhin Code, um eine neue Spalte zur Laufzeit dynamisch an das Recordset zu binden. Informationen dazu, wie Sie diese Bindung verwenden, finden Sie unter [Recordset: Dynamisches Binden von Datenspalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

Sie können die DBMS verwenden, zum Ändern des Schemas oder ein anderes Tool, das Sie DDL-Funktionen durchführen kann. Sie können auch die ODBC-Funktionsaufrufe verwenden, für das Senden von SQL-Anweisungen, wie z. B. der Aufruf einer vordefinierten Abfrage (gespeicherten Prozedur), die keine Datensätze zurückgibt.

##  <a name="_core_making_direct_sql_function_calls"></a> Erstellung direkter SQL-Funktionsaufrufe

Sie können direkt ausführen, einen SQL-Aufruf mithilfe einer [CDatabase-Klasse](../../mfc/reference/cdatabase-class.md) Objekt. Richten Sie Ihre SQL-Anweisung enthält (in der Regel eine `CString`) und übergeben es an der [CDatabase:: ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql) Memberfunktion Ihre `CDatabase` Objekt. Wenn Sie ODBC-Funktionsaufrufe verwenden, um eine SQL-Anweisung zu senden, die normalerweise Datensätze zurückgibt, werden die Einträge ignoriert.

## <a name="see-also"></a>Siehe auch

[SQL](../../data/odbc/sql.md)