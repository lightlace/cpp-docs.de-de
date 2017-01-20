---
title: "Weitervertrieb von ODBC-Komponenten an Kunden"
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
  - "Komponenten [C++]"
  - "Komponenten [C++], Verteilen"
  - "Komponenten [C++], Verteilen"
  - "ODBC-Administrator"
  - "ODBC-Komponenten, Verteilen"
  - "ODBC, Verteilen von Komponenten"
ms.assetid: 17b065b4-a307-4b89-99ac-d05831cfab87
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Weitervertrieb von ODBC-Komponenten an Kunden
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Falls Sie die Funktionalität der ODBC\-Administrationsprogramme in eine Anwendung integrieren, müssen Sie die zur Ausführung dieser Programme erforderlichen Dateien an die Benutzer weitergeben.  Diese ODBC\-Dateien sind im Verzeichnis "\\OS\\System" auf der Visual C\+\+\-CD gespeichert.  Die Datei Redistrb.wri und der Softwarelizenzvertrag im selben Verzeichnis enthalten eine Liste der ODBC\-Dateien, die Sie weitergeben dürfen.  
  
 Informieren Sie sich in der Dokumentation zu den ODBC\-Treibern, die Sie weitergeben möchten.  Sie müssen entscheiden, welche DLLs und sonstigen Dateien im Lieferumfang enthalten sein sollen.  
  
 Darüber hinaus sollten Sie sich unter [Installieren der Datenbankunterstützung](../../data/installing-database-support-mfc-atl.md) über ODBC\-Komponenten und \-Treiber sowie unter [Redistributing Controls](../../data/ado-rdo/redistributing-controls.md) \(nur auf Englisch verfügbar\) darüber informieren, wie ActiveX\-Steuerelemente weitervertrieben werden.  
  
 In den meisten Fällen müssen Sie eine weitere Datei mitliefern.  Die Datei Odbccr32.dll ist die ODBC\-Cursorbibliothek.  Diese Bibliothek verleiht Level 1\-Treibern die Fähigkeit zum Vorwärts\- und Rückwärtsscrollen.  Außerdem ergänzt sie die Unterstützung von Momentaufnahmen.  Weitere Informationen über die ODBC\-Cursorbibliothek finden Sie unter [ODBC: Die ODBC\-Cursorbibliothek](../../data/odbc/odbc-the-odbc-cursor-library.md).  
  
 Die folgenden Themen enthalten weitere Informationen zur Verwendung von ODBC mit den Datenbankklassen:  
  
-   [ODBC: Die ODBC\-Cursorbibliothek](../../data/odbc/odbc-the-odbc-cursor-library.md)  
  
-   [ODBC: Konfigurieren einer ODBC\-Datenquelle](../../data/odbc/odbc-configuring-an-odbc-data-source.md)  
  
-   [ODBC: Direktes Aufrufen von ODBC\-API\-Funktionen](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)  
  
## Siehe auch  
 [Grundlagen zu ODBC](../../data/odbc/odbc-basics.md)   
 [ODBC\-Administrator](../../data/odbc/odbc-administrator.md)