---
title: "Was sind DAO und ODBC?"
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
  - "DAO (Datenzugriffsobjekte), und ODBC"
  - "ODBC, Informationen über ODBC"
ms.assetid: 22cc2f75-7ff6-47bc-ac56-56a40591104c
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Was sind DAO und ODBC?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sowohl Data Access Objects \(DAOs\) als auch Open Database Connectivity \(ODBC\) sind Anwendungsprogrammierschnittstellen \(APIs\), die es Ihnen ermöglichen, Anwendungen unabhängig von einem bestimmten Datenbank\-Managementsystem \(DBMS\) zu entwickeln.  
  
 Datenbankprogrammierer, die mit Microsoft Access Basic oder Microsoft Visual Basic arbeiten, kennen DAO bereits.  Mithilfe des Microsoft Jet\-Datenbankmoduls stellt DAO eine Reihe von Datenzugriffsobjekten bereit: Datenbankobjekte, **tabledef**\- und **querydef**\-Objekte, Recordset\-Objekte u. a.  Am besten funktioniert DAO mit MDB\-Dateien, wie sie z. B. von Microsoft Access erstellt werden. DAO und das Microsoft Jet\-Datenbankmodul ermöglichen jedoch auch den Zugriff auf ODBC\-Datenquellen.  
  
 ODBC bietet eine API, die verschiedene Datenbankanbieter in Form von ODBC\-Treibern implementieren. Die Treiber sind jeweils für bestimmte Datenbank\-Managementsysteme \(DBMS\) geeignet.  Das Programm ruft über diese API den ODBC\-Treiber\-Manager auf, der die Aufrufe an den geeigneten Treiber übergibt.  Der Treiber kommuniziert wiederum via SQL mit dem DBMS.  
  
> [!NOTE]
>  ODBC ist ein Hauptbestandteil der Microsoft Windows Open Standards Architecture \(WOSA\).  DAO ist zwar für das Microsoft Jet\-Datenbankmodul optimiert, ermöglicht jedoch auch den Zugriff auf ODBC und andere externe Datenquellen mit diesem Modul. Auch die spezielle ODBC\-API und die darauf basierenden MFC\-Klassen sind weiterhin verfügbar und spielen weiter eine wichtige Rolle bei der Auswahl der richtigen Datenbanktools.  
  
## Siehe auch  
 [FAQ \(Häufig gestellte Fragen\) zum Datenzugriff](../data/data-access-frequently-asked-questions-mfc-data-access.md)