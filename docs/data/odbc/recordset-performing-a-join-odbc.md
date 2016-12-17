---
title: "Recordset: Ausf&#252;hren einer Verkn&#252;pfung (ODBC)"
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
  - "Datenbindung [C++], Spalten in Recordsets"
  - "Datenbindung [C++], Recordsetspalten"
  - "Filter [C++], Verknüpfen der Bedingungen für Recordsets"
  - "Verknüpfungen [C++], In Recordsets"
  - "ODBC-Recordsets [C++], Joins"
  - "Recordsets [C++], Binden von Daten"
  - "Recordsets [C++], Verknüpfen von Tabellen"
ms.assetid: ca720900-a156-4780-bf01-4293633bea64
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset: Ausf&#252;hren einer Verkn&#252;pfung (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
## Joins  
 Mithilfe einer Joinoperation können Sie in einem einzigen Recordset\-Objekt mit Daten arbeiten, die aus mehreren verschiedenen Tabellen stammen. Joins werden in Datenzugriffsanwendungen häufig verwendet.  Das Verknüpfen von zwei oder mehr Tabellen führt zu einem Recordset, das Spalten aus jeder dieser Tabellen enthalten kann, für die Anwendung aber trotzdem wie eine einzige Tabelle aussieht.  Manchmal verwendet der Join alle Spalten sämtlicher Tabellen, häufig wählt die SQL\-**SELECT**\-Klausel in einem Join aber auch nur bestimmte Spalten jeder Tabelle aus.  Die Datenbankklassen unterstützen schreibgeschützte Joins, aber keine aktualisierbaren Joins.  
  
 Um Datensätze auswählen zu können, die Spalten aus verknüpften Tabellen enthalten, benötigen Sie:  
  
-   eine Liste der Tabellen mit den Namen aller verknüpften Tabellen;  
  
-   eine Spaltenliste mit den Namen aller beteiligten Spalten.  Spalten, die den gleichen Namen haben, aber aus unterschiedlichen Tabellen stammen, werden mit dem Tabellennamen gekennzeichnet;  
  
-   ein Filter \(SQL\-**WHERE**\-Klausel\), der die Spalten angibt, über die die Tabellen verknüpft sind.  Dieser Filter hat die Form "Table1.KeyCol \= Table2.KeyCol" und führt den eigentlichen Join aus.  
  
 Sie können in derselben Weise auch mehr als zwei Tabellen verknüpfen, indem Sie mehrere Spaltenpaare angeben und diese Paare mit dem SQL\-Schlüsselwort **AND** verknüpfen.  
  
## Siehe auch  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Deklarieren einer Klasse für eine vordefinierte Abfrage \(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)   
 [Recordset: Deklarieren einer Klasse für eine Tabelle \(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [Recordset: Erneutes Abfragen eines Recordsets \(ODBC\)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)