---
title: "Zugreifen auf ODBC und SQL | Microsoft Docs"
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
  - "API-Aufrufe [C++], Aufrufen von DAO oder ODBC (direkt)"
  - "ODBC [C++], API-Funktionen"
  - "ODBC-API-Funktionen [C++]"
  - "ODBC-API-Funktionen [C++], Aufrufen aus MFC"
  - "SQL [C++], Aufrufen von ODBC-API-Funktionen"
  - "Windows-API [C++], Aufrufen aus MFC"
ms.assetid: 5613d7dc-00b7-4646-99ae-1116c05c52b4
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Zugreifen auf ODBC und SQL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC schließt viele Windows\-API\-Aufrufe ein, Sie können aber dennoch jede Windows\-API\-Funktion direkt aufrufen.  Die Datenbankklassen ermöglichen dieselbe Flexibilität in Bezug auf die ODBC\-API.  Die Datenbankklassen verbergen größtenteils die komplexeren ODBC\-Komponenten. Sie können ODBC\-API\-Funktionen jedoch überall im Programm direkt aufrufen.  
  
 Auf ähnliche Weise "bewahren" die Datenbankklassen Sie weitgehend vor der Verwendung von [SQL](../../data/odbc/sql.md), Sie können SQL aber trotzdem direkt verwenden.  Sie können Recordset\-Objekte anpassen, indem Sie ihnen beim Öffnen eine selbstdefinierte SQL\-Anweisung übergeben \(oder indem Sie Teile der Standardanweisung ändern\).  Sie können direkte SQL\-Aufrufe auch mit der [ExecuteSQL](../Topic/CDatabase::ExecuteSQL.md)\-Memberfunktion der [CDatabase](../../mfc/reference/cdatabase-class.md)\-Klasse durchführen.  
  
 Weitere Informationen hierzu finden Sie unter [ODBC: Direktes Aufrufen von ODBC\-API\-Funktionen](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) und [SQL: Durchführen direkter SQL\-Aufrufe \(ODBC\)](../../data/odbc/sql-making-direct-sql-calls-odbc.md).  
  
## Siehe auch  
 [ODBC und MFC](../../data/odbc/odbc-and-mfc.md)