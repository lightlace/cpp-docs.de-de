---
title: "Auf welche Datenquellen kann mit DAO und ODBC zugegriffen werden?"
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
  - "DAO [C++], Datenquellentpyen"
  - "Daten [C++], DAO"
  - "Daten [C++], ODBC"
  - "Datenzugriff [C++], DAO"
  - "Datenquellen [C++], Zugriff über DAO und ODBC"
  - "Datenbanken [C++], Zugreifen über DAO"
  - "FAQs [C++], Zugängliche Datenbanken"
  - "ODBC [C++], Zugängliche Datenquellen"
  - "ODBC-Datenquellen [C++], Zugänglich"
ms.assetid: c88abb45-526a-467a-a01b-d9396bd63236
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Auf welche Datenquellen kann mit DAO und ODBC zugegriffen werden?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beide Gruppen von MFC\-Klassen unterstützen den Zugriff auf eine Vielzahl von Datenquellen sowie die Programmierung von Anwendungen, die von der Datenquelle unabhängig sind.  
  
##  <a name="_core_databases_you_can_access_with_dao"></a> Datenbanken, die den Zugriff über DAO unterstützen  
 Mit DAO und den MFC\-DAO\-Klassen kann auf folgende Datenquellen zugegriffen werden:  
  
-   Datenbanken, die das Microsoft Jet\-Datenbankmodul verwenden und mit Microsoft Access oder Microsoft Visual Basic \(Version 1.x, 2.x oder 3.0\) des Datenbankmoduls angelegt wurden.  
  
-   Installierbare ISAM\-Datenbanken, einschließlich:  
  
    -   dBASE III, dBASE IV und dBASE 5.0  
  
    -   Paradox, Versionen 3.x, 4.x und 5.x  
  
-   ODBC\-Datenbanken \(Open Database Connectivity\), darunter Microsoft SQL Server, SYBASE SQL Server und ORACLE Server.  Um auf eine ODBC\-Datenbank zugreifen zu können, benötigen Sie einen geeigneten ODBC\-Treiber für die jeweilige Datenbank.  Eine Liste der in dieser Version von Visual C\+\+ mitgelieferten ODBC\-Treiber sowie Informationen über den Erwerb zusätzlicher Treiber finden Sie unter [Liste der ODBC\-Treiber](../data/odbc/odbc-driver-list.md).  
  
-   Microsoft Excel\-Kalkulationstabellen der Versionen 3.0, 4.0, 5.0 und 7.0  
  
-   Lotus WKS\-, WK1\-, WK3\- und WK4\-Arbeitsblätter  
  
-   Textdateien  
  
 DAO wird am besten mit Datenbanken verwendet, die das Microsoft Jet\-Datenbankmodul lesen kann. Dazu gehören alle oben genannten Datenbanken außer ODBC\-Datenquellen.  Optimale Leistung erzielen Sie mit Microsoft Jet\-Datenbanken \(MDB\).  Besonders bei externen Tabellen in ODBC\-Datenquellen ist es effizienter, sie mit einer MDB\-Datenbank zu verknüpfen, als die externe Datenbank ohne Verknüpfung direkt über die MFC\-DAO\-Klassen zu öffnen.  
  
##  <a name="_core_databases_you_can_access_with_odbc"></a> Datenbanken, die den Zugriff über ODBC unterstützen  
 Mit ODBC und den MFC\-ODBC\-Klassen können Sie auf jede lokale oder Remotedatenquelle zugreifen, für die der Benutzer Ihrer Anwendung einen ODBC\-Treiber besitzt. Es sind 16\-Bit\-, 32\-Bit\- und 64\-Bit\-ODBC\-Treiber für eine Vielzahl von Datenquellen verfügbar.  Beim Einsatz eines Microsoft Jet\-Datenbankmoduls \(MDB\) ist es effizienter, DAO\-Klassen anstelle des Microsoft Access\-ODBC\-Treibers zu verwenden.  
  
## Siehe auch  
 [FAQ \(Häufig gestellte Fragen\) zum Datenzugriff](../data/data-access-frequently-asked-questions-mfc-data-access.md)