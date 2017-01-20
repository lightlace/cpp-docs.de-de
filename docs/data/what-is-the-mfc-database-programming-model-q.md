---
title: "Wie ist das MFC-Modell f&#252;r die Datenbankprogrammierung aufgebaut?"
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
  - "DAO [C++], MFC"
  - "Datenzugriff [C++], Technologien"
  - "Datenbanken [C++], MFC"
  - "MFC [C++], Datenbankanwendungen"
  - "ODBC [C++], MFC"
  - "ODBC-Klassen [C++], MFC-Datenbankklassen"
ms.assetid: f6f15bb8-4115-41f2-ad68-036e74a11bd9
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Wie ist das MFC-Modell f&#252;r die Datenbankprogrammierung aufgebaut?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obwohl DAO und ODBC recht unterschiedlich in MFC implementiert sind, haben sie doch ähnliche Schnittstellen, die das Portieren von Anwendungen zwischen diesen Standards, insbesondere von ODBC zu DAO, relativ einfach gestalten.  Informationen zum Portieren von ODBC zu DAO finden Sie unter dem [Technischen Hinweis 55](../mfc/tn055-migrating-mfc-odbc-database-class-applications-to-mfc-dao-classes.md).  Die DAO\- und die ODBC\-Schnittstellen in MFC ähneln außerdem den Schnittstellen in Visual Basic.  
  
 Das MFC\-Programmiermodell stellt für jede geöffnete Datenbank ein Datenbankobjekt bereit.  Das Datenbankobjekt stellt die Verbindung mit der Datenbank dar.  Abfragen und Aktualisierungen erfolgen über Recordset\-Objekte.  Die Arbeit mit Tabellenstrukturen, das Speichern von Abfragen zur Wiederverwendung usw. wird von DAO mit zusätzlichen Objekten unterstützt, wie weiter unten beschrieben.  MFC enthält für jedes dieser Objekte eigene Klassen: eine Gruppe für DAO und eine andere für ODBC.  
  
 Durch die Verwendung von MFC lässt sich der Datenzugriff vereinfachen.  Die DAO\- und ODBC\-Datenbankklassen bieten hohe Abstraktionsebenen, die den Verzicht auf die direkte Verwendung von DAO oder ODBC ermöglichen.  Die Programmierung dieser APIs ist wesentlich komplizierter als der Einsatz der MFC\-Klassen.  Das gilt besonders für kleine, relativ einfach strukturierte Anwendungen.  
  
 Durch die Datenbankklassen werden der MFC\-Klassenbibliothek folgende Komponenten hinzugefügt:  
  
-   C\+\+\-Datenbankklassen, die eine API mit hoher Abstraktionsebene für den Datenbankzugriff über DAO oder ODBC ermöglichen  
  
-   Erweiterungen im Anwendungs\-Assistenten und unter **Klasse hinzufügen** zum Erstellen anwendungsspezifischer Datenbankklassen  
  
-   Beispielprogramme, die die Verwendung der Klassen und Assistenten demonstrieren  
  
-   Onlinedokumentation mit Übersichten, Artikeln über Programmierung und Referenzmaterial zu Klassen  
  
 Informationen über diese Komponenten finden Sie unter [ODBC und MFC](../data/odbc/odbc-and-mfc.md).  
  
 Weitere Informationen finden Sie unter:  
  
-   [Sollte DAO oder ODBC verwendet werden?](../data/should-i-use-dao-or-odbc-q.md)  
  
-   [Werden DDL \(Database Definition Language\) und DML \(Database Manipulation Language\) von DAO und ODBC unterstützt?](../data/are-ddl-and-dml-supported-q.md)  
  
-   [Installieren der MFC\-Datenbankunterstützung](../data/installing-mfc-database-support.md)  
  
-   Die [ODBC](../data/odbc/odbc-and-mfc.md)\-Klassen in MFC  
  
-   [MFC\-Datenbankdokumentation](../data/mfc-database-documentation.md)  
  
-   [ODBC und MFC](../data/odbc/odbc-and-mfc.md)  
  
## Siehe auch  
 [FAQ \(Häufig gestellte Fragen\) zum Datenzugriff](../data/data-access-frequently-asked-questions-mfc-data-access.md)