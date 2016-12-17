---
title: "Installieren der MFC-Datenbankunterst&#252;tzung"
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
  - "DAO [C++], Installieren von Komponenten"
  - "Datenbanken [C++], Installieren der Datenbankunterstützung"
  - "Datenbanken [C++], MFC"
  - "Installieren von DAO"
  - "Installieren von ODBC"
  - "ODBC-Komponenten [C++], Installieren"
  - "ODBC-Treiber [C++], Installieren"
ms.assetid: a6c2fc84-9e0e-4f39-a464-0bcbc415b946
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Installieren der MFC-Datenbankunterst&#252;tzung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

##  <a name="_core_odbc_drivers_installed"></a> Installierte ODBC\-Treiber  
 Setup installiert die folgenden ODBC\-Treiber:  
  
-   Microsoft Access\-Treiber  
  
-   Microsoft dBASE\-Treiber  
  
-   Microsoft Excel\-Treiber  
  
-   Microsoft FoxPro VFP\-Treiber  
  
-   Microsoft Visual FoxPro\-Treiber  
  
-   Microsoft ODBC für Oracle\-Treiber  
  
-   Microsoft Paradox\-Treiber  
  
-   Microsoft Text\-Treiber  
  
-   Microsoft SQL Server\-Treiber  
  
 Eine Liste der in dieser Version von Visual C\+\+ mitgelieferten ODBC\-Treiber sowie Informationen über den Erwerb zusätzlicher Treiber finden Sie unter [Liste der ODBC\-Treiber](../data/odbc/odbc-driver-list.md).  
  
##  <a name="_core_odbc_sdk_components_installed"></a> Installierte ODBC SDK\-Komponenten  
 Visual C\+\+ enthält zahlreiche wichtige ODBC\-Komponenten, darunter die erforderlichen Headerdateien, Bibliotheken, DLLs und Tools.  Dazu gehören auch die Systemsteuerungsanwendung ODBC\-Administrator, mit der Sie die ODBC\-Datenquellen konfigurieren, sowie der ODBC\-Treiber\-Manager.  Auch ODBC\-Treiber für die bekanntesten DBMS sind enthalten. Eine Liste dieser Treiber finden Sie unter [Installierte ODBC\-Treiber](#_core_odbc_drivers_installed).  
  
 Mit dem ODBC SDK stehen Ihnen zusätzliche Informationen und Tools zum Erstellen und Testen von ODBC\-Treibern zur Verfügung.  Beachten Sie, dass das ODBC SDK ab Visual C\+\+ .NET nicht mehr auf den Visual C\+\+ .NET\-Installationsmedien enthalten, sondern als Teil des mit den Visual Studio .NET \- Erforderliche Komponenten installierten [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)]s verfügbar ist.  
  
##  <a name="_core_dao_sdk_components_installed"></a> Installierte DAO SDK\-Komponenten  
  
> [!NOTE]
>  Microsoft empfiehlt für neue Projekte die Verwendung von OLE DB oder ODBC.  DAO sollte lediglich für die Verwaltung bereits vorhandener Anwendungen eingesetzt werden.  
  
 Folgende Komponenten des DAO SDK werden standardmäßig installiert:  
  
-   Microsoft Jet \(4.0 SP3\)  
  
-   Microsoft Jet \(3.x MDB\)  
  
-   Microsoft Jet \(1.x, 2.x\)  
  
-   Alle Datenbankformate, die unter [Auf welche Datenquellen kann mit DAO und ODBC zugegriffen werden?](../data/what-data-sources-can-i-access-with-dao-and-odbc-q.md) aufgelistet sind  
  
 In Visual C\+\+ .NET wird das DAO SDK mit den Visual Studio .NET \- Erforderlichen Komponenten installiert.  Führen Sie die Datei **\\Jet\\Jetsetup.exe** aus.  
  
> [!NOTE]
>  Microsoft empfiehlt die Verwendung von Jet 4.0 Service Pack 3 \(Version 2927.04\) oder höher.  Jet 4.0 Service Pack 3 ist im Lieferumfang von Windows 2000 und Windows ME enthalten.  Durch die Verwendung dieser Jet\-Version verringert sich die Anzahl der Jet\-Versionen, die mit Ihrer Anwendung getestet werden müssen.  Im Lieferumfang von Windows XP ist eventuell eine andere Version von Jet enthalten.  Siehe "Note on Redistributing DAO Components" unter [Redistributing Controls](../data/ado-rdo/redistributing-controls.md) \(nur auf Englisch verfügbar\).  
  
 Falls Sie andere DAO SDK\-Komponenten installieren möchten, z. B. DAO SDK\-C\+\+\-Klassen, Beispieldateien oder die Windows\-Hilfeversion der DAO\-Hilfedatei, installieren Sie das DAO SDK über die Visual C\+\+ 6.0\-CD\-ROM.  
  
 Für Updates und Neuigkeiten zu OLE DB, finden Sie die Datenzugriffs\-Website universelle an [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=121548](http://go.microsoft.com/fwlink/?LinkId=121548).  
  
## Siehe auch  
 [Datenzugriffsprogrammierung \(MFC\/ATL\)](../data/data-access-programming-mfc-atl.md)