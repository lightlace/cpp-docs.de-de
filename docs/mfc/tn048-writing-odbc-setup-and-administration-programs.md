---
title: "TN048: Schreiben von ODBC-Einrichtungs- und Verwaltungsprogrammen f&#252;r MFC-Datenbankanwendungen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.odbc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Installieren von ODBC"
  - "MFC, Datenbankanwendungen"
  - "ODBC, und MFC"
  - "ODBC, Installieren"
  - "Einrichtung, ODBC-Setupprogramme"
  - "TN048"
ms.assetid: d456cdd4-0513-4a51-80c0-9132b66115ce
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# TN048: Schreiben von ODBC-Einrichtungs- und Verwaltungsprogrammen f&#252;r MFC-Datenbankanwendungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Anwendungen mithilfe MFC\-Datenbankklassen benötigen ein Setupprogramm ODBC\-Komponenten, das installiert.  Sie benötigen auch ein ODBC\-Verwaltungsprogramm, das Informationen über die verfügbaren Treiber, um anzugeben Standardtreibern abruft und Datenquellen konfigurieren.  Dieser Hinweis beschreibt die Verwendung der ODBC\-Installationsprogramm API, diese Programme zu schreiben.  
  
##  <a name="_mfcnotes_writing_an_odbc_setup_program"></a> Schreiben eines ODBC\-Setupprogramms  
 Eine MFC\-Datenbankanwendung erfordert den ODBC\-Treiber\-Manager \(ODBC.DLL\) und die ODBC\-Treiber, um, Datenquellen zu erreichen.  Viele ODBC\-Treiber benötigen auch zusätzliche Netzwerk und Kommunikation DLLs.  Die meisten ODBC\-Treiber\-Schiff mit dem Setupprogramm, das die erforderlichen ODBC\-Komponenten installiert.  Die Anwendungsentwickler, die MFC\-Datenbankklassen können:  
  
-   Erstellen Sie auf den treiberspezifischen Setupprogramme zum Installieren von ODBC\-Komponenten.  Dazu ist keine weitere Bearbeitung zum teil\- Entwickler können Sie das Setupprogramm des Treibers gerade verteilen.  
  
-   Alternativ können Sie ein eigenes Setupprogramm schreiben, das den Treibermanager und Treiber installiert.  
  
 Die ODBC\-Installationsprogramm API kann verwendet werden, um eine anwendungsspezifische Setupprogramme zu schreiben.  Die Funktionen in der Installer API werden durch die ODBC\-Installationsprogramm DLL \- ODBCINST.DLL auf \-\-Windows 16\-Bit\- und ODBCCP32.DLL auf Win32 implementiert.  Eine Anwendung kann **SQLInstallODBC** in der Installer DLL aufrufen, die den ODBC\-Treiber\-Manager, die ODBC\-Treiber und alle erforderlichen Übersetzer installiert.  Sie zeichnet dann die installierten Treiber und die Übersetzer in der ODBCINST.INI\-Datei auf \(oder in der Registrierung, auf NT\).  **SQLInstallODBC** erfordert den vollständigen Pfad zur ODBC.INF\-Datei, die die Liste der zu installierenden enthält Treiber und die Dateien beschrieben, die jeden Treiber enthalten.  Es enthält auch ähnliche Informationen über den Treibermanager und \-übersetzer.  ODBC.INF\-Dateien werden in der Regel von den Treiberentwicklern angegeben.  
  
 Ein Programm kann einzelne ODBC\-Komponenten installieren.  So den Treiber\-Manager installieren, zuerst **SQLInstallDriverManager** eines Programms im Installationsprogramm der DLL, um das Zielverzeichnis für den Treiber\-Manager abzurufen.  Dies ist normalerweise das Verzeichnis, in dem DLL\-Dateien befinden.  Das Programm verwendet dann die Informationen im Abschnitt \[ODBC\-Treiber\-Manager\] der ODBC.INF\-Datei, um den Treiber\-Manager und verwandte Dateien vom Installationsdatenträger zu diesem Verzeichnis zu kopieren.  Wenn Sie einen einzelnen Treiber installieren, zuerst **SQLInstallDriver** eines Programms im Installationsprogramm der DLL, um der Treiberspezifikation der ODBCINST.INI\-Datei \(oder der Registrierung, auf NT\) hinzuzufügen.  **SQLInstallDriver** gibt dem Zielverzeichnis des Treibers \- normalerweise dem Verzeichnis zurück, in dem DLL\-Dateien befinden.  Das Programm verwendet dann die Informationen im Abschnitt des Treibers der ODBC.INF\-Datei, um die Treiber DLL und verwandte Dateien vom Installationsdatenträger zu diesem Verzeichnis zu kopieren.  
  
 Weitere Informationen über ODBC.INF, finden ODBCINST.INI und der API Installationsprogramm, ODBC SDK Programmer's Reference *,* Chapter 19 und installieren ODBC\-Software.  
  
##  <a name="_mfcnotes_writing_an_odbc_administrator"></a> Schreiben eines ODBC\-Administrators  
 Eine MFC\-Datenbankanwendung kann ODBC\-Datenquellen in zwei Arten installieren und konfigurieren, wie folgt:  
  
-   Verwenden Sie den ODBC\-Administrator \(verfügbar als Programm oder als Systemsteuerungselement\).  
  
-   Erstellen Sie ein eigenes Programm, um Datenquellen konfigurieren.  
  
 Ein Programm, das konfiguriert Datenquellen, macht Funktionsaufrufe Installationsprogramm der DLL.  Die Installationsprogramm DLL ruft eine Setup DLL auf, um eine Datenquelle zu konfigurieren.  Es gibt eine DLL für jeden Treiber installiert; ggf. die Treiber DLL selbst oder eine separate DLL.  Die DLL Setup fordert den Benutzer zu Informationen, die der Treiber an die Datenquelle und den Standardübersetzer herstellen müssen, falls unterstützt werden.  Sie ruft dann die Installationsprogramm DLL und Windows\-APIs auf, um diese Informationen in der ODBC.INI\-Datei \(oder in der Registrierung\) aufzuzeichnen.  
  
 So zeigen Sie ein Dialogfeld an, mit dem ein Benutzer hinzufügen kann, Datenquellen, Aufrufe **SQLManageDataSources** ändern und löschen eines Programms im Installationsprogramm der DLL.  Diese Funktion wird aufgerufen, wenn die DLL Installationsprogramm von der Systemsteuerung aufgerufen wird.  So fügen, eine Datenquelle, **SQLManageDataSources** zu ändern oder zu löschen ruft **ConfigDSN** in Setup der DLL für Treiber auf, der mit der Datenquelle zugeordnet ist.  Um direkt Datenquellen hinzufügen, ändern oder löschen, ruft ein Programm **SQLConfigDataSource** Installationsprogramm in der DLL auf.  Das Programm wird den Namen der Datenquelle und der Option, die die Aktion bezeichnen.  **SQLConfigDataSource** ruft **ConfigDSN** in Setup der DLL auf und übergibt ihn die Argumente von **SQLConfigDataSource**.  
  
 Weitere Informationen finden Sie in ODBC SDK Programmer's Reference *,* Kapitel 23, Setup DLL Funktionsaufruf und Kapitel 24, Installationsprogramm DLL Funktionsaufruf.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)