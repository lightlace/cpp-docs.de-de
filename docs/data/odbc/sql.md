---
title: SQL
ms.date: 11/04/2016
helpviewer_keywords:
- database classes [C++], SQL statements
- SQL [C++]
- SQL [C++], ODBC
- ODBC [C++], SQL implementation
ms.assetid: e3923bc4-b317-4e0b-afd8-3cd403eb0faf
ms.openlocfilehash: 8f93d97530068695359273b523e7d2ae46de01cb
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59037856"
---
# <a name="sql"></a>SQL

SQL (Structured Query Language) ist eine Möglichkeit für die Kommunikation mit einer relationalen Datenbank, mit dem Sie Abfrage definieren, ändern und Steuern der Daten. Mit SQL-Syntax, können Sie eine Anweisung erstellen, die Datensätze gemäß den Kriterien extrahiert, die Sie angeben.

> [!NOTE]
>  Diese Informationen gelten für die MFC-ODBC-Klassen. Wenn Sie mit den MFC-DAO-Klassen arbeiten, finden Sie unter den Vergleich von Microsoft Jet-Datenbank-Engine-SQL-Thema und ANSI-SQL in-DAO-Hilfe.

SQL-Anweisungen beginnen mit einem Schlüsselwort-Verb wie z. B. **erstellen** oder **wählen**. SQL ist eine sehr leistungsfähige Programmiersprache. eine einzelne Anweisung kann es sich um eine gesamte Tabelle auswirken.

Viele Versionen von SQL vorhanden ist, wird jeweils ein bestimmtes DBMS Bedenken entwickelt. Die MFC-Datenbankklassen erkennen einen Satz von SQL-Anweisungen, die entspricht, auf die X / Open "und" SQL Zugriff Gruppe häufig Anwendungen Umgebung CAE-SQL-Spezifikationsentwurf (1991). Informationen zur Syntax dieser Anweisungen finden Sie in Anhang C in die *ODBC SDK* *Programmer's Reference* auf der MSDN Library-CD.

In diesem Thema wird Folgendes erläutert:

- [Die Beziehung zwischen ODBC und SQL](#_core_open_database_connectivity_.28.odbc.29).

- [Die am häufigsten verwendeten SQL-Schlüsselwörter, die von den Datenbankklassen verwendeten](#_core_the_database_classes).

- [Verwendung von SQL in die Datenbankklassen](#_core_how_the_database_classes_use_sql).

##  <a name="_core_open_database_connectivity_.28.odbc.29"></a> Open Sie Database Connectivity (ODBC)

Die Datenbankklassen sind bei ODBC implementiert, die SQL-Code in SQL-Befehle in den Code einbetten, anstatt eine Call-Level-Interface verwendet. ODBC verwendet SQL für die Kommunikation mit einem [Datenquelle](../../data/odbc/data-source-odbc.md) über ODBC-Treiber. Diese Treiber interpretieren und SQL übersetzen, falls erforderlich, für die Verwendung mit einem bestimmten Datenbankformat, z. B. Microsoft Access. Weitere Informationen zur Verwendung des ODBC SQL finden Sie unter [ODBC](../../data/odbc/odbc-basics.md) und dem ODBC-SDK *Programmer's Reference* auf der MSDN Library-CD.

##  <a name="_core_the_database_classes"></a> Datenbankklassen

Die Datenbankklassen dienen, sodass Sie bearbeiten und Aktualisieren von Daten in einer vorhandenen [Datenquelle](../../data/odbc/data-source-odbc.md). Die [MFS-Anwendungsassistenten](../../mfc/reference/database-support-mfc-application-wizard.md), [MFC-ODBC-Consumer-Assistenten](../../mfc/reference/adding-an-mfc-odbc-consumer.md) (Zugriff erfolgt über **Klasse hinzufügen**), und die Datenbankklassen erstellen Sie die meisten der SQL-Anweisungen für Sie.

Datenbankklassen verwendet einen Teil von SQL bekannt als der Data Manipulation Language (DML). Mit diesen Befehlen können Sie arbeiten mit ganz oder teilweise von der Datenquelle neue Datensätze hinzufügen, Datensätze bearbeiten und Löschen von Datensätzen. Die folgende Tabelle enthält die am häufigsten verwendeten SQL-Schlüsselwörter und die Möglichkeiten Datenbankklassen verwendet werden.

### <a name="some-common-sql-keywords"></a>Einige gebräuchliche Schlüsselwörter aus SQL

|SQL-Schlüsselwort|Die Assistenten und die Datenbankklassen verwenden|
|-----------------|---------------------------------------------|
|**SELECT**|Um zu ermitteln, welche Tabellen und Spalten in der Datenquelle verwendet werden.|
|**WHERE**|Um einen Filter anzuwenden, der die Auswahl beschränkt.|
|**ORDER BY**|Das Recordset eine Sortierreihenfolge zuweisen.|
|**INSERT**|Neue Datensätze zu einem Recordset hinzufügen.|
|**LÖSCHEN**|Zum Löschen von Datensätzen aus einem Recordset.|
|**UPDATE**|So ändern Sie die Felder eines Datensatzes.|

Darüber hinaus erkennt die Datenbankklassen ODBC **Aufrufen** Anweisungen, die Sie verwenden können, für einige Datenquellen eine vordefinierte Abfrage (oder eine gespeicherte Prozedur) aufgerufen. Der ODBC-Datenbanktreiber interpretiert diese Anweisungen und ersetzt den Befehl entsprechend für jeden DBMS.

> [!NOTE]
>  Nicht alle DBMS-Unterstützung **Aufrufen** Anweisungen.

Wenn die Klassen in eine benutzerdefinierte-Anweisung nicht erkennen `CRecordset::Open`, wird er als Namen einer Tabelle interpretiert.

Eine Erklärung, wie das Framework für SQL-Anweisungen erstellt, finden Sie unter [Recordset: Datensatzauswahl durch Recordsets (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) und [SQL: Anpassen der SQL-Anweisung eines Recordsets (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).

SQL-Datenbanken verwenden Sie Datentypen, die ähnlich wie in C und C++. Eine Erläuterung der diese ähnlichkeiten, finden Sie unter [SQL: SQL- und C++-Datentypen (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md).

Sie finden weitere Informationen zu SQL, einschließlich einer Liste der unterstützten SQL-Anweisungen, Datentypen, Core-SQL-Grammatik und eine Lesen-Liste der empfohlenen Veröffentlichungen zu SQL, in der *ODBC SDK* *-Programmierreferenz*  auf der MSDN Library-CD.

##  <a name="_core_how_the_database_classes_use_sql"></a> Verwenden Sie die Datenbankklassen wie SQL

Die Recordsets, die von den Datenbankklassen abgeleitet ODBC zur Kommunikation mit einer Datenquelle verwenden, und ODBC ruft Datensätze aus der Datenquelle ab, durch Senden von SQL-Anweisungen. In diesem Thema wird die Beziehung zwischen den Datenbankklassen und SQL erläutert.

Ein Recordset generiert eine SQL-Anweisung, durch das Einrichten der Teile einer SQL­Anweisung in einem `CString`. Die Zeichenfolge wird als erstellt eine **wählen** -Anweisung, die eine Gruppe von Datensätzen zurückgibt.

Wenn das Recordset ODBC, senden eine SQL-Anweisung mit der Datenquelle aufgerufen wird, wird der ODBC-Treiber-Manager übergibt die Anweisung an den ODBC-Treiber und der Treiber sendet es an das zugrunde liegende DBMS. Das DBMS gibt ein Resultset von Datensätzen zurück, und der ODBC-Treiber die Datensätze an die Anwendung zurück. Die Datenbankklassen können das Programm auf zugreifen, die das Resultset in eine typsichere C++-Klasse abgeleitet `CRecordset`.

Weitere Informationen darüber, wie die Datenbankklassen SQL verwenden Sie in den folgenden Themen:

- [SQL: Anpassen der SQL-Anweisung eines Recordsets (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)

- [SQL: SQL- und C++-Datentypen (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)

- [SQL: Durchführen direkter SQL-Aufrufe (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)

## <a name="see-also"></a>Siehe auch

[Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[Grundlagen zu ODBC](../../data/odbc/odbc-basics.md)