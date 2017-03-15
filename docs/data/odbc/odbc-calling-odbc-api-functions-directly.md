---
title: "ODBC: Direktes Aufrufen von ODBC-API-Funktionen | Microsoft Docs"
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
  - "APIs [C++], Aufrufen"
  - "Katalogfunktionen (ODBC)"
  - "Katalogfunktionen (ODBC), Aufrufen"
  - "Direkte ODBC API-Aufrufe"
  - "ODBC [C++], API-Funktionen"
  - "ODBC [C++], Katalogfunktionen"
  - "ODBC-API-Funktionen [C++]"
  - "ODBC-API-Funktionen [C++], Aufrufen"
  - "ODBC-Klassen [C++], Im Vergleich zu ODBC API"
ms.assetid: 4295f1d9-4528-4d2e-bd6a-c7569953c7fa
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ODBC: Direktes Aufrufen von ODBC-API-Funktionen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Datenbankklassen stellen eine einfachere Schnittstelle zu einer [Datenquelle](../../data/odbc/data-source-odbc.md) zur Verfügung, als ODBC sie anbietet.  Folglich schließen die Klassen nicht die komplette ODBC\-API ein.  Um Funktionalität zu nutzen, die außerhalb der Fähigkeiten der Klassen liegt, müssen Sie ODBC\-API\-Funktionen direkt aufrufen.  Die ODBC\-Katalogfunktionen \(**::SQLColumns**, **::SQLProcedures**, **::SQLTables** usw.\) müssen Sie z. B. direkt aufrufen.  
  
> [!NOTE]
>  Auf ODBC\-Datenquellen können Sie über die MFC\-ODBC\-Klassen zugreifen, wie in diesem Thema beschrieben, oder über die MFC\-Datenzugriffsobjekt\-Klassen \(DAO\-Klassen\).  
  
 Um eine ODBC\-API\-Funktion direkt aufrufen zu können, müssen Sie dieselben Schritte ausführen wie für ein Aufrufen ohne Verwendung des Frameworks.  Die Schritte sind:  
  
-   Reservieren Sie Speicher für die beim Aufrufen zurückgelieferten Ergebnisse.  
  
-   Übergeben Sie ein ODBC\-Handle vom Typ **HDBC** oder vom Typ **HSTMT**, abhängig von der Parametersignatur der Funktion.  Verwenden Sie das [AFXGetHENV](../Topic/AfxGetHENV.md)\-Makro, um das ODBC\-Handle abzurufen.  
  
     Es stehen die **CDatabase::m\_hdbc\-**Membervariable und die **CRecordset::m\_hstmt\-**Membervariable zur Verfügung, sodass Sie die Handles nicht selbst reservieren und initialisieren müssen.  
  
-   Rufen Sie bei Bedarf zusätzliche ODBC\-Funktionen auf, um den Hauptaufruf vorzubereiten oder abzuschließen.  
  
-   Geben Sie danach reservierten Speicher wieder frei.  
  
 Weitere Informationen über diese Schritte finden Sie im [Open Database Connectivity \(ODBC\)](https://msdn.microsoft.com/en-us/library/ms710252.aspx)\-SDK in der MSDN\-Dokumentation.  
  
 Zusätzlich zu diesen Schritten sollten Sie die Rückgabewerte der Funktion überprüfen, sicherstellen, dass das Programm nicht auf die Beendigung eines asynchronen Aufrufs wartet, usw.  Diese letzten Schritte können Sie vereinfachen, wenn Sie das Makro `AFX_SQL_ASYNC` und das Makro `AFX_SQL_SYNC` verwenden.  Weitere Informationen finden Sie in der *MFC\-Referenz* unter [Macros and Globals](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md) \(nur auf Englisch verfügbar\).  
  
## Siehe auch  
 [Grundlagen zu ODBC](../../data/odbc/odbc-basics.md)