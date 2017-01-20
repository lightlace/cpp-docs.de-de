---
title: "Werden DDL und DML unterst&#252;tzt?"
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
  - "Datenbearbeitungssprache (Data Manipulation Language) in MFC ODBC [C++]"
  - "Datenbanken [C++], Zugreifen über DAO"
  - "Datenbanken [C++], DDL-Zugriff"
  - "Datenbanken [C++], DML-Zugriff"
  - "DDLs [C++], MFC-Unterstützung"
  - "DML [C++]"
  - "DML [C++], MFC-ODBC"
ms.assetid: 07f96d81-78d4-4bec-9138-b15d68fd5ce0
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Werden DDL und DML unterst&#252;tzt?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die MFC\-DAO\-Klassen unterstützen zwei Zugriffsarten für Datenbanken:  
  
-   **Datendefinitionssprache \(DDL\)** Sie können Datenbanken sowie Tabellen erstellen und löschen, Tabellenfelder und Indizes definieren sowie andere Aktionen ausführen, die die Struktur der Datenbank verändern.  
  
-   **Datenbearbeitungssprache \(DML\)** Sie können Abfragen ausführen, Datensätze hinzufügen, löschen und ändern sowie den Inhalt der Datenbank auf andere Weise bearbeiten.  
  
 Die MFC\-ODBC\-Klassen unterstützen lediglich DML. Sie können ODBC\-API\-Funktionen jedoch auch direkt aufrufen, um DDL\-Aufgaben auszuführen.  
  
## Siehe auch  
 [FAQ \(Häufig gestellte Fragen\) zum Datenzugriff](../data/data-access-frequently-asked-questions-mfc-data-access.md)