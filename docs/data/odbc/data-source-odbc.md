---
title: "Datenquelle (ODBC) | Microsoft Docs"
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
  - "CDatabase-Klasse, Datenquellenverbindungen"
  - "Konfigurieren von ODBC-Datenquellen"
  - "ODBC-Datenquellen"
  - "ODBC-Datenquellen, Konfigurieren"
  - "ODBC-Datenquellen, Dargestellt von CDatabase"
ms.assetid: b246721f-b9e1-49bd-a6c7-f348b8c3d537
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Datenquelle (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
 In Datenbankterminologie ausgedrückt setzt sich eine Datenquelle aus einem bestimmten Satz von Daten zusammen, den Informationen, die für den Zugriff auf die Daten notwendig sind, und der Position der Datenquelle, die in Form eines Datenquellennamens beschrieben werden kann.  Zur Verwendung der [CDatabase](../../mfc/reference/cdatabase-class.md)\-Klasse muss die Datenquelle mit dem ODBC \(Open Database Connectivity\)\-Administrator konfiguriert sein.  Beispiele für Datenquellen sind etwa eine Remotedatenbank, die unter Microsoft SQL Server in einem Netzwerk ausgeführt wird, oder eine Microsoft Access\-Datei in einem lokalen Verzeichnis.  Sie können von der Anwendung aus auf jede Datenquelle zugreifen, für die Sie einen ODBC\-Treiber besitzen.  
  
 In der Anwendung können eine oder mehrere Datenquellen gleichzeitig aktiv sein. Dabei wird jede von einem `CDatabase`\-Objekt repräsentiert.  Es können auch gleichzeitig mehrere Verbindungen zu einer Datenquelle bestehen.  Sie können eine Verbindung zu Remote\- oder zu lokalen Datenquellen aufbauen, je nachdem, welche Treiber installiert wurden und welche Funktionen diese ODBC\-Treiber unterstützen.  Weitere Informationen über Datenquellen und ODBC\-Administrator finden Sie unter [ODBC](../../data/odbc/odbc-basics.md) und [ODBC\-Administrator](../../data/odbc/odbc-administrator.md).  
  
 Die folgenden Themen enthalten weitere Informationen zu Datenquellen:  
  
-   [Datenquelle: Verwalten von Verbindungen \(ODBC\)](../../data/odbc/data-source-managing-connections-odbc.md)  
  
-   [Datenquelle: Bestimmen des Schemas der Datenquelle \(ODBC\)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)  
  
## Siehe auch  
 [Open Database Connectivity \(ODBC\)](../../data/odbc/open-database-connectivity-odbc.md)