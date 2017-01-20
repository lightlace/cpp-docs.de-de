---
title: "Sollte DAO oder ODBC verwendet werden?"
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
  - "DAO [C++], und ODBC (Vergleich)"
  - "Datenbankklassen [C++], DAO"
  - "Datenbankklassen [C++], ODBC"
  - "ODBC [C++], und DAO (Vergleich)"
ms.assetid: 9f67613f-0056-4ece-8c3a-9872e9563d57
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Sollte DAO oder ODBC verwendet werden?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Ab Visual C\+\+ .NET wird DAO von der Visual C\+\+\-Umgebung und den Assistenten nicht mehr unterstützt. \(Die DAO\-Klassen sind allerdings weiterhin enthalten und können verwendet werden.\)  Microsoft empfiehlt für neue Projekte die Verwendung von OLEDB\-Vorlagen oder ODBC.  DAO sollte lediglich zur Verwaltung bereits bestehender Anwendungen eingesetzt werden.  
  
 Welche MFC\-Klassentypen sollten verwendet werden?  Dies hängt von Ihren Anforderungen ab:  
  
-   ODBC\-Klassen sind empfehlenswert, wenn Sie ausschließlich mit ODBC\-Datenquellen arbeiten, und zwar insbesondere in Client\/Server\-Konfigurationen, in denen die MFC\-ODBC\-Klassen eine bessere Leistung bieten.  
  
-   DAO\-Klassen sind ratsam, wenn Sie hauptsächlich mit Microsoft Jet\-Datenbanken \(.mdb\) oder anderen Datenbankformaten arbeiten, die direkt vom Microsoft Jet\-Datenbankmodul gelesen werden können.  Eine Liste dieser Formate finden Sie unter [Auf welche Datenquellen kann mit DAO und ODBC zugegriffen werden?](../data/what-data-sources-can-i-access-with-dao-and-odbc-q.md)  
  
-   Wenn Sie die Geschwindigkeit des Microsoft Jet\-Datenbankmoduls mit der zusätzlichen Funktionalität von DAO\-Klassen kombinieren möchten, sollte der Zugriff auf ODBC\-Datenquellen über die DAO\-Klassen erfolgen.  
  
    > [!NOTE]
    >  DAO erfordert zusätzlichen Speicherplatz auf der Festplatte.  
  
 DAO\-Klassen haben folgende Vorteile:  
  
-   In einigen Fällen höhere Leistung, besonders wenn Microsoft Jet\-Datenbanken \(.mdb\) verwendet werden.  
  
-   Kompatibilität mit den ODBC\-Klassen sowie mit Microsoft Access Basic und Microsoft Visual Basic.  
  
-   Zugriff auf Validierungsregeln.  
  
-   Die Möglichkeit, Beziehungen zwischen Tabellen festzulegen.  
  
-   Ein leistungsfähigeres Datenzugriffsmodell mit Unterstützung der Datendefinitionssprache \(DDL, Data Definition Language\) und Datenbearbeitungssprache \(DML, Data Manipulation Language\).  Weitere Informationen finden Sie unter [Datenbankdefinition und \-bearbeitung](../data/are-ddl-and-dml-supported-q.md).  
  
 In der folgenden Tabelle sind die Hauptunterschiede zusammengefasst.  
  
### Entscheidung zwischen MFC\-DAO\- und MFC\-ODBC\-Klassen  
  
|Feature|Mit DAO\-Klassen?|Mit ODBC\-Klassen?|  
|-------------|-----------------------|------------------------|  
|Zugriff auf MDB\-Dateien|ja|ja|  
|Zugriff auf ODBC\-Datenquellen|ja|ja|  
|Für 16 Bit verfügbar|nein|ja|  
|Für 32 Bit verfügbar|ja|ja|  
|Für 64 Bit verfügbar|nein|ja|  
|Datenbankkomprimierung|ja|nein|  
|Unterstützung von Datenbankmodulen|Microsoft Jet\-Datenbankmodul|Ziel\-DBMS|  
|DDL\-Unterstützung|ja|Nur über direkte ODBC\-Aufrufe|  
|DML\-Unterstützung|ja|ja|  
|Art der MFC\-Implementierung|"Wrapper" für DAO\-Kernfunktionen|Vereinfachte Abstraktion statt eines "Wrappers" für die ODBC\-API|  
|Optimal geeignet für|MDB\-Dateien \(Microsoft Access\)|Jedes DBMS, für das Treiber verfügbar sind; insbesondere Client\/Server\-Konfigurationen|  
|Transaktionsunterstützung|Pro Projekt oder bei ODBC\-Daten pro Datenbank|Pro Datenbank|  
  
 Beachten Sie, dass die Fähigkeiten verschiedener ODBC\-Treiber variieren können.  Weitere Informationen finden Sie in der ODBC *Programmer's Reference* und in der Hilfedatei zum ODBC\-Treiber.  
  
## Siehe auch  
 [FAQ \(Häufig gestellte Fragen\) zum Datenzugriff](../data/data-access-frequently-asked-questions-mfc-data-access.md)