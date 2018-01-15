---
title: "TN048: Schreiben von ODBC-Einrichtungs- und Verwaltungsprogrammen für MFC-Datenbankanwendungen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.odbc
dev_langs: C++
helpviewer_keywords:
- installing ODBC
- ODBC, installing
- setup, ODBC setup programs
- TN048
- ODBC, and MFC
- MFC, database applications
ms.assetid: d456cdd4-0513-4a51-80c0-9132b66115ce
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3ec19e3c03d88fa088622c7ed8a5b4efeed0014b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tn048-writing-odbc-setup-and-administration-programs-for-mfc-database-applications"></a>TN048: Schreiben von ODBC-Einrichtungs- und Verwaltungsprogrammen für MFC-Datenbankanwendungen
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Verwenden von MFC-Datenbankklassen Anwendungen benötigen ein Setupprogramm, das ODBC-Komponenten installiert. Sie können auch eine ODBC-Verwaltungsprogramms benötigen, die Informationen zu den verfügbaren Treiber, an Standardeinstellung Treiber und zum Konfigurieren von Datenquellen abgerufen werden. Dieser Hinweis beschreibt die Verwendung der ODBC-Installer-API, diese Programme zu schreiben.  
  
##  <a name="_mfcnotes_writing_an_odbc_setup_program"></a>Schreiben Sie eine ODBC-Setup-Programm  
 Eine MFC-datenbankanwendung erfordert der ODBC-Treiber-Manager (ODBC. (DLL) und ODBC-Treiber, um auf Datenquellen zugreifen zu können. Viele ODBC-Treiber erfordern ebenfalls zusätzlichen Netzwerkfehlern und Kommunikationsfehlern DLLs. Die meisten ODBC-Treiber sind im Lieferumfang ein Setupprogramm, das die erforderlichen ODBC-Komponenten installieren. Verwenden von MFC-Datenbankklassen Anwendungsentwickler können:  
  
-   Die treiberspezifische Setupprogramme, zum Installieren von ODBC-Komponenten abhängig sein. Dies erfordert, dass keine weitere Arbeit an den Entwickler – Sie können nur der Treiber-Setupprogramm verteilen.  
  
-   Alternativ können Sie Ihr eigenes Setup-Programm schreiben, das Dadurch wird der Treiber-Manager und der Treiber installiert.  
  
 Die ODBC-Installer-API kann anwendungsspezifische Setupprogramme schreiben verwendet werden. Die Funktionen in der API-Installationsprogramm werden vom ODBC-Installationsprogramm DLL implementiert – ODBCINST. Die DLL auf 16-Bit-Windows und ODBCCP32. Die DLL auf Win32. Eine Anwendung kann Aufrufen **SQLInstallODBC** im Installationsprogramm DLL, die den ODBC-Treiber-Manager, ODBC-Treiber und alle zu installierenden Konvertierer erforderlich. Anschließend zeichnet er der installierten Treiber und Übersetzer in die ODBCINST. INI-Datei (oder der Registrierung auf NT). **SQLInstallODBC** erfordert den vollständigen Pfad zu der ODBC. INF-Datei enthält die Liste der Treiber installiert werden, und beschreibt die Dateien, die jeden Treiber bilden. Es enthält auch ähnliche Informationen zu den Treiber-Manager und Übersetzer. ODBC. INF-Dateien werden normalerweise von Entwicklern Treiber bereitgestellt.  
  
 Ein Programm kann auch einzelne ODBC-Komponenten installieren. Zum Installieren der Treiber-Manager ruft ein Programm zuerst **SQLInstallDriverManager** im Installationsprogramm-DLL für das Zielverzeichnis der Treiber-Manager abzurufen. Dies ist normalerweise das Verzeichnis, in dem Windows-DLLs befinden. Das Programm verwendet dann die Informationen im Abschnitt [ODBC-Treiber-Manager] der ODBC. INF-Datei der Treiber-Manager und zugehörige Dateien aus der Installations-CD in dieses Verzeichnis kopiert. Zum Installieren von eines einzelnen Treibers Ruft ein Programm zuerst **SQLInstallDriver** im Installationsprogramm DLL-Datei der ODBCINST die Treiber-Spezifikation hinzugefügt. INI-Datei (oder der Registrierung auf NT). **SQLInstallDriver** gibt der Treiber Zielverzeichnis – in der Regel auf das Verzeichnis, in denen Windows-DLLs befinden. Das Programm verwendet dann die Informationen im Abschnitt der Treiber die ODBC. INF-Datei der Treiber-DLL und die zugehörigen Dateien aus der Installations-CD in dieses Verzeichnis kopiert.  
  
 Weitere Informationen zu ODBC. INF, ODBCINST. INI-Datei und mit dem Installer-API finden Sie unter ODBC SDK *Programmer's Reference* Kapitel 19, ODBC-Software installieren.  
  
##  <a name="_mfcnotes_writing_an_odbc_administrator"></a>Schreiben von ODBC-Administrator  
 Eine MFC-datenbankanwendung kann einrichten und Konfigurieren von ODBC-Datenquellen in einer von zwei Methoden, wie folgt:  
  
-   Verwenden Sie den ODBC-Administrator (verfügbar als ein Programm oder ein Element der Systemsteuerung).  
  
-   Erstellen Sie ein eigenes Programm zum Konfigurieren von Datenquellen.  
  
 Ein Programm, das Konfigurieren von Datenquellen Aufrufe der Funktion an das Installationsprogramm der DLL. Das Installationsprogramm DLL Ruft ein Setup-DLL für eine Datenquelle konfigurieren. Es gibt ein Setup-DLL für jeden Treiber. der Treiber-DLL selbst oder in einer separaten DLL möglicherweise. Der Setup-DLL fordert den Benutzer Informationen, die der Treiber mit der Datenquelle und das Standard-Konvertierungsprogramm herstellen, wenn unterstützt muss. Er ruft dann das Installationsprogramm, DLL und die Windows-APIs, um diese Informationen in der ODBC zu erfassen. INI-Datei (oder Registrierung).  
  
 Um ein Dialogfeld anzuzeigen, mit denen ein Benutzer kann hinzufügen, ändern und Löschen von Datenquellen, ein Programm aufruft **SQLManageDataSources** im DLL-Installer. Diese Funktion wird aufgerufen, wenn das Installationsprogramm die DLL über die Systemsteuerung aufgerufen wird. Hinzufügen, ändern oder Löschen einer Datenquelle **SQLManageDataSources** Aufrufe **ConfigDSN** in der Setup-DLL für den Treiber, die Datenquelle zugeordnet. Datenquellen direkt hinzufügen, ändern oder Löschen von Daten ist, werden Aufrufe von einem Programm **SQLConfigDataSource** im DLL-Installer. Die Anwendung übergibt den Namen der Datenquelle und eine Option aus, die die auszuführende Aktion angibt. **SQLConfigDataSource** Aufrufe **ConfigDSN** in der Setup-DLL und übergibt sie die Argumente vom **SQLConfigDataSource**.  
  
 Weitere Informationen finden Sie in ODBC SDK *Programmer's Reference* Kapitel 23 Setup DLL-Funktionsreferenz und Kapitel 24, Installer DLL-Funktionsreferenz.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

