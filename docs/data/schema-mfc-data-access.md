---
title: "Schema (MFC-Datenzugriff) | Microsoft Docs"
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
  - "Datenbankschema [C++]"
  - "Datenbankschema [C++], Informationen über Datenbankschemas"
  - "Datenbanken [C++], Schema"
  - "Schemas [C++], Datenbank"
  - "Strukturen [C++]"
  - "Strukturen [C++], Datenbank"
ms.assetid: 7d17e35f-1ccf-4853-b915-5b8c7a45b9ee
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Schema (MFC-Datenzugriff)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Datenbankschema beschreibt die aktuelle Struktur der Tabellen und Datenbankansichten in der Datenbank.  Vom Assistenten generierter Code geht im Allgemeinen davon aus, dass das Schema für die Tabelle bzw. Tabellen, auf die ein Recordset zugreift, sich nicht ändert, die Datenbankklassen können jedoch einige Schemaänderungen verarbeiten, wie das Hinzufügen, Neuanordnen oder Löschen ungebundener Spalten.  Wenn eine Tabelle geändert wird, müssen Sie das Recordset für die Tabelle manuell aktualisieren und die Anwendung anschließend neu kompilieren.  
  
 Sie können den vom Assistenten generierten Code auch ergänzen, um die Bearbeitung einer Datenbank zu ermöglichen, deren Schema zum Zeitpunkt der Kompilierung nicht vollständig bekannt ist.  Weitere Informationen finden Sie unter [Recordset: Dynamisches Binden von Datenspalten\(ODBC\)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
## Siehe auch  
 [Datenzugriffsprogrammierung \(MFC\/ATL\)](../data/data-access-programming-mfc-atl.md)   
 [SQL](../data/odbc/sql.md)   
 [Recordset \(ODBC\)](../data/odbc/recordset-odbc.md)