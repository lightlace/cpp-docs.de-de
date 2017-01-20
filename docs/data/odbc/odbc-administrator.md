---
title: "ODBC-Administrator"
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
  - "Verwaltung mit dem ODBC-Administrator"
  - "Administrator für ODBC"
  - "Treiber [C++], ODBC"
  - "Installieren von ODBC"
  - "ODBC [C++], ODBC-Administrator"
  - "ODBC-Administrator [C++]"
  - "ODBC-Datenquellen [C++], ODBC-Administrator"
  - "ODBC-Treiber [C++], Installieren"
ms.assetid: b8652790-3437-4e7d-bc83-6ea6981f008b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# ODBC-Administrator
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der ODBC\-Administrator registriert und konfiguriert die [Datenquellen](../../data/odbc/data-source-odbc.md), die entweder lokal oder im Netzwerk zur Verfügung stehen.  Die Assistenten erstellen mithilfe der vom ODBC\-Administrator bereitgestellten Informationen Code in Anwendungen, der Verbindungen zu Datenquellen für den Benutzer aufbaut.  
  
 Zur Einrichtung einer ODBC\-Datenquelle zur Verwendung mit MFC\-ODBC\-Datenbankklassen oder DAO\-Klassen muss die Datenquelle zunächst registriert und konfiguriert werden.  Zum Hinzufügen und Entfernen von Datenquellen verwenden Sie den ODBC\-Administrator.  Je nach ODBC\-Treiber können Sie auch neue Datenquellen erstellen.  
  
 Der ODBC\-Administrator wird beim Setup installiert.  Wenn Sie die **benutzerdefinierte Installation** und im Dialogfeld für **Datenbankoptionen** keine ODBC\-Treiber auswählen, müssen Sie Setup erneut ausführen, um die erforderlichen Dateien zu installieren.  
  
 Wählen Sie beim Setup die ODBC\-Treiber aus, die Sie installieren möchten.  Später können Sie mit Setup für Visual C\+\+ zusätzliche Treiber installieren, die in Visual C\+\+ mitgeliefert werden.  
  
 Wenn Sie ODBC\-Treiber installieren möchten, die nicht in Visual C\+\+ mitgeliefert werden, müssen Sie das Setup ausführen, das mit dem Treiber geliefert wurde.  
  
#### So installieren Sie ODBC\-Treiber, die in Visual C\+\+ mitgeliefert werden  
  
1.  Starten Sie von der Visual C\+\+\-CD das Programm Setup.  
  
     Das Begrüßungsdialogfeld von Setup wird angezeigt.  
  
2.  Wählen Sie in jedem Dialogfeld **Weiter**, bis das Dialogfeld **Installationsoptionen** angezeigt wird.  Wählen Sie **Benutzerdefiniert**aus, und klicken Sie dann `Next`.  
  
3.  Deaktivieren Sie alle Kontrollkästchen im Dialogfeld **Microsoft Visual C\+\+ Setup** außer dem Kontrollkästchen **Datenbankoptionen**, und klicken Sie dann auf **Details**, um das Dialogfeld **Datenbankoptionen** zu öffnen.  
  
4.  Deaktivieren Sie das Kontrollkästchen **Microsoft Datenzugriffsobjekte**, wählen Sie das Kontrollkästchen **Microsoft ODBC\-Treiber** aus, und klicken Sie auf **Details**.  
  
     Das Dialogfeld **Microsoft ODBC\-Treiber** wird angezeigt.  
  
5.  Wählen Sie die Treiber aus, die Sie installieren möchten, und klicken Sie dann zweimal auf **OK**.  
  
6.  Wählen Sie in den übrigen Dialogfeldern **Weiter**, um die Installation zu starten.  Setup benachrichtigt Sie, wenn die Installation beendet ist.  
  
 Wenn die Treiber installiert sind, können Sie mit dem ODBC\-Administrator die Datenquelle konfigurieren.  In der Systemsteuerung finden Sie das ODBC\-Symbol.  
  
## Siehe auch  
 [Open Database Connectivity \(ODBC\)](../../data/odbc/open-database-connectivity-odbc.md)   
 [Datenquelle \(ODBC\)](../../data/odbc/data-source-odbc.md)