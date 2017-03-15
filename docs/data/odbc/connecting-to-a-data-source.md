---
title: "Aufbauen der Verbindung zu einer Datenquelle | Microsoft Docs"
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
  - "Verbindungen [C++], Datenquelle"
  - "Datenquellen [C++], Verbinden mit"
  - "Datenbankverbindungen [C++], MFC-ODBC-Klassen"
  - "Datenbankverbindungen [C++], ODBC"
  - "Datenbanken [C++], Verbinden mit"
  - "ODBC-Verbindungen [C++], Verwenden"
  - "ODBC-Datenquellen [C++], Verbindungen"
ms.assetid: ef6c8c98-5979-43a8-9fb5-5bb06fc59f36
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Aufbauen der Verbindung zu einer Datenquelle
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine ODBC\-Datenquelle setzt sich zusammen aus einem bestimmten Satz von Daten, den Informationen, die für das Zugreifen auf die Daten notwendig sind, und der Position der Datenquelle, die in Form eines Datenquellennamens beschrieben werden kann.  Aus Sicht eines Programms besteht die Datenquelle aus den Daten, dem DBMS, dem Netzwerk \(falls vorhanden\) und ODBC.  
  
 Um auf die von einer Datenquelle bereitgestellten Daten zugreifen zu können, muss das Programm zuerst eine Verbindung zu der Datenquelle aufbauen.  Alle Datenzugriffe werden über diese Verbindung getätigt.  
  
 Datenquellenverbindungen sind in die [CDatabase](../../mfc/reference/cdatabase-class.md)\-Klasse eingeschlossen.  Wenn ein `CDatabase`\-Objekt mit einer Datenquelle verbunden ist, können Sie:  
  
-   [Recordsets](../../mfc/reference/crecordset-class.md) erstellen, die Datensätze aus Tabellen oder Abfragen auswählen.  
  
-   [Transaktionen](../../data/odbc/transaction-odbc.md) verwalten, d. h., Aktualisierungen in Form einer Batchverarbeitung speichern, sodass für sämtliche Aktualisierungen in der Datenquelle gleichzeitig ein Commit ausgeführt werden kann, sofern die Datenquelle die erforderliche Transaktionsebene unterstützt \(andernfalls wird für die gesamte Transaktion ein Rollback ausgeführt, sodass die Daten unverändert bleiben\).  
  
-   Führen Sie direkt unter [SQL](../../data/odbc/sql.md)\-Anweisungen aus.  
  
 Sobald die Arbeit mit einer Datenquellenverbindung beendet ist, schließen Sie das `CDatabase`\-Objekt, zerstören es oder verwenden es erneut für eine neue Verbindung.  Weitere Informationen über Datenquellenverbindungen finden unter [Datenquelle \(ODBC\)](../../data/odbc/data-source-odbc.md).  
  
## Siehe auch  
 [ODBC und MFC](../../data/odbc/odbc-and-mfc.md)