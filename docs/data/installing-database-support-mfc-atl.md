---
title: "Installieren der Datenbankunterst&#252;tzung (MFC/ATL)"
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
  - "ATL [C++], Datenbankunterstützung"
  - "Datenzugriff [C++], Installieren der Datenbankunterstützung"
  - "Datenbanken [C++], Installieren der Datenbankunterstützung"
  - "Installieren der Datenbankunterstützung"
ms.assetid: 3820ba96-4fb8-4405-83dd-bb3bc5998667
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Installieren der Datenbankunterst&#252;tzung (MFC/ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beim Ausführen von Setup für Visual C\+\+ .NET werden die folgenden Datenbankkomponenten automatisch installiert:  
  
-   Alle notwendigen ATL\-OLE DB\-Komponenten.  Weitere Informationen finden Sie unter [Installieren der ATL\-Datenbankunterstützung](../data/installing-atl-database-support.md).  
  
-   Eine Reihe von ODBC\-Treibern mit dem ODBC\-Treiber\-Manager und dem ODBC\-Administratorprogramm.  Weitere Informationen finden Sie unter „Installierte ODBC\-Treiber“ und „Installierte ODBC SDK\-Komponenten“ in [Installieren der MFC\-Datenbankunterstützung](../data/installing-mfc-database-support.md).  
  
-   Notwendige Komponenten aus dem DAO Software Development Kit \(SDK\).  Dazu gehören auch Hilfedateien, die in dieser Dokumentation nicht enthalten sind.  Wenn Sie mit DAO arbeiten, müssen Sie jedoch eine Version von Jet installieren, die mit Ihrem Betriebssystem kompatibel ist.  Weitere Informationen finden Sie unter „Installierte DAO SDK\-Komponenten“ in [Installieren der MFC\-Datenbankunterstützung](../data/installing-mfc-database-support.md).  
  
 Als Teil der Basisinstallation installiert Setup auch Microsoft Data Access Components \(MDAC\), die zur Unterstützung der Datenzugriffsprogrammierung in Visual C\+\+ .NET erforderlich sind.  
  
 Visual C\+\+ .NET installiert das MDAC 2.7 SDK.  Suchen Sie auf der Microsoft Universal Data Access\-Website unter [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=121548](http://go.microsoft.com/fwlink/?LinkId=121548) nach Updates und Neuigkeiten zum MDAC SDK.  
  
 Wenn Sie Anwendungen für den Datenzugriff weitergeben, sollten Sie auch das MDAC 2.7\-Weitergabeprogramm haben.  Das MDAC 2.7 SDK wurde zur Verwendung mit dem MDAC 2.7\-Weitergabeprogramm \(Mdac\_typ.exe\) entwickelt, das im Verzeichnis MDAC auf der Visual Studio .NET\-CD\-ROM für erforderliche Komponenten verfügbar ist.  Sie können Mdac\_typ.exe auch über den oben genannten Link für das MDAC 2.7 SDK herunterladen.  Weitere Informationen über die Weitergabe von Komponenten finden Sie unter [Weiterverteilen von Steuerelementen](../data/ado-rdo/redistributing-controls.md).  
  
## Siehe auch  
 [Datenzugriff](../Topic/Data%20Access%20in%20Visual%20C++.md)