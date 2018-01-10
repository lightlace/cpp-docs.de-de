---
title: SQL | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- database classes [C++], SQL statements
- SQL [C++]
- SQL [C++], ODBC
- ODBC [C++], SQL implementation
ms.assetid: e3923bc4-b317-4e0b-afd8-3cd403eb0faf
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0c4283e73b800ac0fd4d448d5137372807f893d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="sql"></a>SQL
SQL (Structured Query Language) ist eine Möglichkeit zum Kommunizieren mit einer relationalen Datenbank, mit dem Sie Abfrage definieren, ändern und steuern, welche Daten. SQL-Syntax können Sie eine Anweisung erstellen, die Datensätze gemäß den Kriterien extrahiert, die Sie angeben.  
  
> [!NOTE]
>  Diese Informationen gelten für die MFC-ODBC-Klassen. Wenn Sie mit den MFC-DAO-Klassen arbeiten, finden Sie unter dem Thema Vergleich von Microsoft Jet-Datenbank-Engine-SQL und ANSI SQL DAO-Hilfe.  
  
 SQL-Anweisungen beginnen mit einem Schlüsselwort Verb wie z. B. **erstellen** oder **wählen**. SQL ist eine sehr leistungsfähige Sprache. eine einzelne Anweisung kann es sich um eine gesamte Tabelle auswirken.  
  
 Viele Versionen von SQL Server vorhanden ist, wird jede für ein bestimmtes DBMS Bedenken entwickelt. MFC-Datenbankklassen erkennt einen Satz von SQL-Anweisungen, die nach dem X / Open-entspricht und SQL Zugriff Gruppe allgemeine Anwendungen Umgebung (CAE) SQL-Spezifikationsentwurf (1991). Informationen zur Syntax dieser Anweisungen finden Sie unter Anhang C in die *ODBC SDK* *Programmer's Reference* auf der MSDN Library-CD.  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Die Beziehung zwischen ODBC und SQL](#_core_open_database_connectivity_.28.odbc.29).  
  
-   [Die am häufigsten verwendeten SQL-Schlüsselwörter, die von den Datenbankklassen verwendeten](#_core_the_database_classes).  
  
-   [Verwendung von die Datenbankklassen SQL](#_core_how_the_database_classes_use_sql).  
  
##  <a name="_core_open_database_connectivity_.28.odbc.29"></a>Open Sie Database Connectivity (ODBC)  
 Die Datenbankklassen sind bei ODBC implementiert, die SQL in SQL-Befehle in den Code einbetten, statt einer Call-Level-Interface verwendet. ODBC verwendet SQL für die Kommunikation mit einem [Datenquelle](../../data/odbc/data-source-odbc.md) über ODBC-Treiber. Diese Treiber interpretieren und SQL übersetzen, falls erforderlich, für die Verwendung mit einem bestimmten Datenbankformat, z. B. Microsoft Access. Weitere Informationen darüber, wie ODBC SQL verwendet, finden Sie unter [ODBC](../../data/odbc/odbc-basics.md) und dem ODBC-SDK *Programmer's Reference* auf der MSDN Library-CD.  
  
##  <a name="_core_the_database_classes"></a>Datenbankklassen  
 Die Datenbankklassen dienen, mit dem Bearbeiten und Aktualisieren von Daten in einer vorhandenen [Datenquelle](../../data/odbc/data-source-odbc.md). Die [MFC-Anwendung-Assistent](../../mfc/reference/database-support-mfc-application-wizard.md), [MFC-ODBC-Consumer-Assistent](../../mfc/reference/adding-an-mfc-odbc-consumer.md) (Zugriff erfolgt über **Klasse hinzufügen**), und die Datenbankklassen die meisten SQL-Anweisungen für Sie erstellen.  
  
 Datenbankklassen verwendet einen Teil des SQL als Data Manipulation Language (DML) bezeichnet. Diese Befehle können Sie ganz oder teilweise von der Datenquelle arbeiten, neue Datensätze hinzufügen, Bearbeiten von Datensätzen und Löschen von Datensätzen. Die folgende Tabelle enthält die am häufigsten verwendeten SQL-Schlüsselwörter und die Möglichkeiten Datenbankklassen verwendet werden.  
  
### <a name="some-common-sql-keywords"></a>Einige SQL-Schlüsselwörter  
  
|SQL-Schlüsselwort|Die Assistenten und die Datenbankklassen verwenden|  
|-----------------|---------------------------------------------|  
|**SELECT**|Identifizieren, welche Tabellen und Spalten in der Datenquelle verwendet werden sollen.|  
|**WHERE**|Um einen Filter anzuwenden, der die Auswahl eingeschränkt wird.|  
|**ORDER BY**|Eine Sortierreihenfolge für das Recordset anwenden.|  
|**EINFÜGEN**|Beim Hinzufügen neuer Einträge zu einem Recordset.|  
|**LÖSCHEN**|Zum Löschen von Datensätzen aus einem Recordset.|  
|**UPDATE**|So ändern Sie die Felder eines Datensatzes.|  
  
 Darüber hinaus erkennt die Datenbankklassen ODBC **Aufrufen** Anweisungen, die Sie verwenden können, für einige Datenquellen eine vordefinierte Abfrage (oder eine gespeicherte Prozedur) aufgerufen. Der ODBC-Datenbanktreiber interpretiert diese Anweisungen und ersetzt den Befehl für jede DBMS geeignet.  
  
> [!NOTE]
>  Nicht alle DBMS-Unterstützung **Aufrufen** Anweisungen.  
  
 Wenn die Klassen in eine benutzerdefinierte-Anweisung nicht erkennen `CRecordset::Open`, wird er als Tabellenname interpretiert.  
  
 Eine Erläuterung, wie das Framework für SQL-Anweisungen erstellt, finden Sie unter [Recordset: wie Recordsets auswählen von Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) und [SQL: Anpassen eines Recordsets SQL-Anweisung (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).  
  
 SQL-Datenbanken verwenden Datentypen, die ähnlich wie in C und C++. Eine Erläuterung der diese ähnlichkeiten, finden Sie unter [SQL: SQL- und C++-Daten-Datentypen (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md).  
  
 Sie finden weitere Informationen zu SQL, z. B. eine Liste der unterstützten SQL-Anweisungen, Datentypen, Core-SQL-Grammatik und eine Liste Lesen der empfohlenen Veröffentlichungen zu "SQL" oder der *ODBC SDK* *Programmer's Reference*  auf der MSDN Library-CD.  
  
##  <a name="_core_how_the_database_classes_use_sql"></a>Wie die Datenbankklassen SQL verwenden  
 Die Recordsets, die Sie von den Datenbankklassen ableiten Verwenden von ODBC zur Kommunikation mit einer Datenquelle, und ODBC ruft Datensätze aus der Datenquelle ab, indem Sie die SQL-Anweisungen zu senden. In diesem Thema wird erläutert, die Beziehung zwischen den Datenbankklassen und SQL.  
  
 Ein Recordset erstellt eine SQL-Anweisung durch das Einrichten der Teile einer SQL-Anweisung in einem `CString`. Die Zeichenfolge wird als erstellt eine **wählen** -Anweisung, die eine Gruppe von Datensätzen zurückgibt.  
  
 Wenn das Recordset ODBC, senden eine SQL-Anweisung mit der Datenquelle aufgerufen wird, wird der ODBC-Treiber-Manager übergibt die Anweisung an den ODBC-Treiber und der Treiber sendet sie an das zugrunde liegende DBMS. Das DBMS gibt ein Resultset von Datensätzen zurück, und der ODBC-Treiber die Datensätze an die Anwendung zurückgegeben. Die Datenbankklassen können das Programm auf zugreifen, die das Resultset in eine typsichere Klasse abgeleitet `CRecordset`.  
  
 Die folgenden Themen enthalten weitere Informationen darüber, wie die Datenbankklassen SQL verwenden:  
  
-   [SQL: Anpassen der SQL-Anweisung eines Recordsets (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)  
  
-   [SQL: SQL- und C++-Datentypen (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)  
  
-   [SQL: Durchführen direkter SQL-Aufrufe (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Open Sie Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)   
 [Grundlagen zu ODBC](../../data/odbc/odbc-basics.md)