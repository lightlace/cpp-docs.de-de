---
title: "SQL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Datenbankklassen [C++], SQL-Anweisungen"
  - "ODBC [C++], SQL-Implementierung"
  - "SQL [C++]"
  - "SQL [C++], ODBC"
ms.assetid: e3923bc4-b317-4e0b-afd8-3cd403eb0faf
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# SQL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

SQL \(Structured Query Language\) ist eine Methode, die Kommunikation mit einer relationalen Datenbank, die Sie definieren können, die Daten abfragen, ändern und steuern.  Mit der SQL\-Syntax können Sie eine Anweisung erstellen, die Datensätze anhand der von Ihnen spezifizierten Kriterien extrahiert.  
  
> [!NOTE]
>  Diese Informationen beziehen sich auf die MFC\-ODBC\-Klassen.  Falls Sie mit den MFC\-DAO\-Klassen arbeiten, lesen Sie das Thema "Vergleich von Microsoft Jet Database Engine\-SQL und ANSI\-SQL" in der DAO\-Hilfe.  
  
 SQL\-Anweisungen beginnen mit einem Verb\-Schlüsselwort, z. B. **CREATE** oder **SELECT**.  SQL ist eine äußerst leistungsfähige Sprache, bei der eine einzige Anweisung Auswirkungen auf eine gesamte Tabelle haben kann.  
  
 SQL ist in vielen Versionen vorhanden und jede wurde für ein bestimmtes DBMS entwickelt.  Die MFC\-Datenbankklassen erkennen eine Reihe von SQL\-Anweisungen, die "X\/Open and SQL Access Group Common Applications Environment \(CAE\) SQL Draft Specification \(1991\)" entsprechen.  Informationen zur Syntax dieser Anweisungen finden Sie im Anhang C von *ODBC SDK* *Programmer's Reference* auf der MSDN Library\-CD.  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Die Beziehung zwischen ODBC und SQL](#_core_open_database_connectivity_.28.odbc.29).  
  
-   [Die wichtigsten der von den Datenbankklassen verwendeten SQL\-Schlüsselwörter](#_core_the_database_classes).  
  
-   [Wie die Datenbankklassen SQL verwenden](#_core_how_the_database_classes_use_sql).  
  
##  <a name="_core_open_database_connectivity_.28.odbc.29"></a> Open Database Connectivity \(ODBC\)  
 Die Datenbankklassen werden mit ODBC implementiert. Mit ODBC werden SQL\-Anweisungen nicht in den Code integriert, sondern über ein Call\-Level\-Interface aufgerufen.  ODBC verwendet SQL, um über ODBC\-Treiber mit einer [Datenquelle](../../data/odbc/data-source-odbc.md) zu kommunizieren.  Diese Treiber interpretieren und, falls erforderlich, übersetzen SQL zur Verwendung mit einem bestimmten Datenbankformat, z. B. Microsoft Access.  Weitere Informationen darüber, wie ODBC von SQL Gebrauch macht, finden Sie unter [ODBC](../../data/odbc/odbc-basics.md) und in der *ODBC SDK Programmer's Reference* auf der MSDN Library\-CD.  
  
##  <a name="_core_the_database_classes"></a> Datenbankklassen  
 Datenbankklassen wurden zur Bearbeitung und Aktualisierung einer bestehenden [Datenquelle](../../data/odbc/data-source-odbc.md) entworfen.  Der [MFC\-Anwendungs\-Assistent](../../mfc/reference/database-support-mfc-application-wizard.md), der [MFC\-ODBC\-Consumer\-Assistent](../../mfc/reference/adding-an-mfc-odbc-consumer.md) \(auf den mit **Klasse hinzufügen** zugegriffen wird\) und die Datenbankklassen erstellen einen Großteil der SQL\-Anweisungen für Sie.  
  
 Die Datenbankklassen verwenden einen Teil von SQL, der als Datenmanipulationssprache \(Data Manipulation Language, DML\) bezeichnet wird.  Mithilfe dieser Befehle können Sie mit der gesamten Datenquelle oder einer Teilmenge davon arbeiten, neue Datensätze hinzufügen, Datensätze verändern und Datensätze löschen.  Die folgende Tabelle führt die wichtigsten SQL\-Schlüsselwörter auf und die Art, in der die Datenbankklassen diese Schlüsselwörter verwenden.  
  
### Wichtige SQL\-Schlüsselwörter  
  
|SQL\-Schlüsselwort|Verwendung durch Assistenten und Datenbankklassen|  
|------------------------|-------------------------------------------------------|  
|**SELECT**|Identifizieren der zu verwendenden Tabellen und Spalten in der Datenquelle.|  
|**WHERE**|Anwenden eines Filters, der die Auswahl einschränkt.|  
|**ORDER BY**|Anwenden einer Sortierreihenfolge für das Recordset.|  
|**EINFG**|Hinzufügen neuer Datensätze zu einem Recordset.|  
|**ENTF**|Löschen von Datensätzen aus einem Recordset.|  
|**UPDATE**|Ändern der Felder eines Datensatzes.|  
  
 Außerdem erkennen die Datenbankklassen ODBC\-**CALL**\-Anweisungen, mit denen Sie eine vordefinierte Abfrage \(oder gespeicherte Prozedur\) für bestimmte Datenquellen aufrufen können.  Der ODBC\-Datenbanktreiber interpretiert diese Anweisungen und ersetzt sie durch die für das jeweilige DBMS passenden Befehle.  
  
> [!NOTE]
>  Nicht alle Datenbank\-Management\-Systeme unterstützen **CALL**\-Anweisungen.  
  
 Falls die Klassen eine vom Benutzer in `CRecordset::Open` angegebene Anweisung nicht erkennen, wird sie als Tabellenname interpretiert.  
  
 Informationen dazu, wie das Framework SQL\-Anweisungen erstellt, finden Sie unter [Recordset: Datensatzauswahl durch Recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) und [SQL: Anpassen der SQL\-Anweisung eines Recordsets \(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md).  
  
 SQL\-Datenbanken verwenden Datentypen, die denen von C und C\+\+ ähneln.  Eine Erläuterung dieser Ähnlichkeiten finden Sie unter [SQL: SQL\- und C\+\+\-Datentypen \(ODBC\)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md).  
  
 Verwandte Informationen über SQL finden Sie in *ODBC SDK* *Programmer's Reference* auf der MSDN Library\-CD, darunter eine Liste der unterstützten SQL\-Anweisungen, Datentypen, die SQL\-Kernstruktur und eine Liste mit Literaturhinweisen zum Thema SQL.  
  
##  <a name="_core_how_the_database_classes_use_sql"></a> Wie die Datenbankklassen SQL verwenden  
 Die Recordsets, die Sie von den Datenbankklassen ableiten, kommunizieren via ODBC mit einer Datenquelle. ODBC ruft Datensätze mithilfe von SQL\-Anweisungen aus der Datenquelle ab.  In diesem Thema wird die Beziehung zwischen den Datenbankklassen und SQL erläutert.  
  
 Ein Recordset generiert eine SQL\-Anweisung, indem es die Teilstücke einer SQL\-Anweisung in einem `CString` zusammensetzt.  Die Zeichenfolge wird als **SELECT**\-Anweisung erstellt, die eine Gruppe von Datensätzen zurückgibt.  
  
 Wenn das Recordset ODBC aufruft, um eine SQL\-Anweisung an die Datenquelle zu senden, gibt der ODBC\-Treiber\-Manager die Anweisung an den ODBC\-Treiber weiter, der sie anschließend an das zugrunde liegende DBMS sendet.  Das DBMS gibt ein Resultset von Datensätzen zurück, die der ODBC\-Treiber an die Anwendung überträgt.  Mithilfe der Datenbankklassen kann das Programm mit einer typsicheren C\+\+\-Klasse, die von `CRecordset` abgeleitet ist, auf das Resultset zugreifen.  
  
 Die folgenden Themen enthalten weitere Informationen darüber, wie die Datenbankklassen SQL verwenden:  
  
-   [SQL: Anpassen der SQL\-Anweisung eines Recordsets \(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md)  
  
-   [SQL: SQL\- und C\+\+\-Datentypen \(ODBC\)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)  
  
-   [SQL: Durchführen direkter SQL\-Aufrufe \(ODBC\)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)  
  
## Siehe auch  
 [Open Database Connectivity \(ODBC\)](../../data/odbc/open-database-connectivity-odbc.md)   
 [Grundlagen zu ODBC](../../data/odbc/odbc-basics.md)