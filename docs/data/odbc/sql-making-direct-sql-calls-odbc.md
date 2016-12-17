---
title: "SQL: Durchf&#252;hren direkter SQL-Aufrufe (ODBC)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Direkte SQL-Aufrufe aus ODBC"
  - "ODBC, SQL-Aufrufe"
  - "SQL-Aufrufe"
  - "SQL, Aufrufen direkt aus ODBC"
  - "SQL, Direkte Aufrufe aus ODBC"
ms.assetid: 091988d2-f5a5-4c2d-aa09-8779a9fb9607
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# SQL: Durchf&#252;hren direkter SQL-Aufrufe (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird Folgendes erläutert:  
  
-   Wann Sie direkte SQL\-Aufrufe verwenden sollten.  
  
-   [Wie Sie direkte SQL\-Aufrufe für die Datenquelle durchführen](#_core_making_direct_sql_function_calls).  
  
> [!NOTE]
>  Diese Informationen beziehen sich auf die MFC\-ODBC\-Klassen.  Wenn Sie mit den MFC\-DAO\-Klassen arbeiten, lesen Sie in der DAO\-Hilfe das Thema "Vergleich von Microsoft Jet Database Engine\-SQL und ANSI\-SQL".  
  
##  <a name="_core_when_to_call_sql_directly"></a> Wann Sie direkte SQL\-Aufrufe verwenden sollten  
 Wenn Sie Tabellen anlegen, löschen oder ändern bzw. Indizes anlegen oder sonstige SQL\-Funktionen aufrufen möchten, die das Schema der [Datenquelle \(ODBC\)](../../data/odbc/data-source-odbc.md) verändern, muss hierzu unter Verwendung von DDL \(Database Definition Language\) eine SQL\-Anweisung direkt an die Datenquelle übergeben werden.  Wenn Sie zur Entwurfszeit einen Assistenten für die Erstellung eines Recordsets verwenden, können Sie auswählen, welche Tabellenspalten im Recordset repräsentiert werden sollen.  Hierbei sind Spalten ausgeschlossen, die Sie oder andere Benutzer der Datenquelle der Tabelle erst hinzufügen, nachdem das Programm kompiliert wurde.  Die Datenbankklassen unterstützen DDL nicht direkt, Sie können aber trotzdem Code erstellen, um neue Spalten während der Laufzeit dynamisch an das Recordset zu binden.  Weitere Informationen zu diesem Bindungsvorgang finden Sie unter [Recordset: Dynamisches Binden von Datenspalten \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
 Sie können das Schema mit DBMS oder einem anderen Tool verändern, mit dem DDL\-Funktionen ausgeführt werden können.  Sie können SQL\-Anweisungen auch mit ODBC\-Funktionsaufrufen verschicken, z. B. durch Aufruf einer vordefinierten Abfrage \(gespeicherte Prozedur\), die keine Datensätze zurückliefert.  
  
##  <a name="_core_making_direct_sql_function_calls"></a> Direkter Aufruf von SQL\-Funktionen  
 Mit einem [CDatabase Class](../../mfc/reference/cdatabase-class.md)\-Objekt können Sie einen direkten SQL\-Aufruf durchführen.  Stellen Sie die SQL\-Anweisungszeichenfolge \(gewöhnlich in `CString`\) zusammen, und übergeben Sie diese an die [CDatabase::ExecuteSQL](../Topic/CDatabase::ExecuteSQL.md)\-Memberfunktion des `CDatabase`\-Objekts.  Falls Sie eine SQL\-Anweisung, die normalerweise Datensätze zurückliefert, mit ODBC\-Funktionsaufrufen senden, werden die Datensätze ignoriert.  
  
## Siehe auch  
 [SQL](../../data/odbc/sql.md)