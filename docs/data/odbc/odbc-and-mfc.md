---
title: "ODBC und MFC | Microsoft Docs"
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
  - "Verbindungen [C++], Datenbanken"
  - "Datenquellen [C++], Verbinden mit"
  - "Datenbankverbindungen [C++], MFC-ODBC-Klassen"
  - "Datenbanken [C++], Verbinden mit"
  - "MFC [C++], ODBC und"
  - "ODBC [C++], MFC"
ms.assetid: 98f02fd7-1235-437b-89a9-edfd0fc797f7
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ODBC und MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Wenn das mit den MFC\-Datenbankklassen geschriebene Programm auf einer Win32\-Plattform ausgeführt werden soll \(z. B. Windows NT\), müssen Sie den geeigneten ODBC\-Treiber für die Datenquelle zur Verfügung stellen.  Einige Treiber werden mit Visual C\+\+ geliefert. Von Microsoft und anderen Herstellern können Sie weitere Treiber beziehen.  Weitere Informationen finden Sie unter [Liste der ODBC\-Treiber](../../data/odbc/odbc-driver-list.md).  
  
 Dieses Thema enthält eine Einführung in die wichtigsten Konzepte der ODBC\-basierten Datenbankklassen von MFC \(Microsoft Foundation Classes\) und bietet eine Übersicht über das Zusammenwirken der Klassen.  Weitere Informationen über ODBC und MFC finden Sie unter den folgenden Themen:  
  
-   [Aufbauen der Verbindung zu einer Datenquelle](../../data/odbc/connecting-to-a-data-source.md)  
  
-   [Auswählen und Verändern von Datensätzen](../../data/odbc/selecting-and-manipulating-records.md)  
  
-   [Anzeigen und Verändern von Daten in einem Formular](../../data/odbc/displaying-and-manipulating-data-in-a-form.md)  
  
-   [Arbeiten mit Dokumenten und Ansichten](../../data/odbc/working-with-documents-and-views.md)  
  
-   [Zugreifen auf ODBC und SQL](../../data/odbc/access-to-odbc-and-sql.md)  
  
-   [Weiterführende Themen zu MFC\-ODBC\-Klassen](../../data/odbc/further-reading-about-the-mfc-odbc-classes.md)  
  
 Die ODBC\-basierten MFC\-Datenbankklassen bieten Zugriff auf jede Datenbank, für die ein ODBC\-Treiber zur Verfügung steht.  Da die Klassen ODBC verwenden, kann die Anwendung auf Daten in vielen verschiedenen Datenformaten und verschiedenen lokalen und Remotekonfigurationen zugreifen.  Sie müssen keinen speziellen Code für die Verwaltung bestimmter Datenbankmanagementsysteme \(DBMS\) schreiben.  Solange die Benutzer über einen geeigneten ODBC\-Treiber für die Daten verfügen, auf die sie zugreifen möchten, können sie die hier in Tabellen gespeicherten Daten mit einem Programm ändern.  
  
## Siehe auch  
 [Open Database Connectivity \(ODBC\)](../../data/odbc/open-database-connectivity-odbc.md)