---
title: "Exemplarische Vorgehensweise: Bereitstellen des Programms (C++)"
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
  - "Bereitstellen von Anwendungen [C++], Exemplarische Vorgehensweisen"
  - "Setup-Projekte [C++]"
  - "Programmbereitstellungen [C++]"
  - "Projekte [C++], Setup"
  - "Projekte [C++], Bereitstellen von Programmen"
  - "Anwendungsbereitstellung [C++], Exemplarische Vorgehensweisen"
ms.assetid: 79e6cc4e-dced-419d-aaf7-d62d1367603f
caps.latest.revision: 17
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Bereitstellen des Programms (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Nachdem Sie die Anwendung erstellt haben, indem Sie die früheren exemplarischen Vorgehensweisen dazu vorgenommen haben, die in [Verwenden der Visual Studio\-IDE für C\+\+\-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md) aufgeführt sind, besteht der letzte Schritt in der Erstellung eines Installationsprogramms, damit andere Benutzer das Programm auf ihren Computern installieren können.  Dazu fügen Sie der vorhandenen Projektmappe ein neues Projekt hinzu.  Die Ausgabe dieses neuen Projekts ist eine setup.exe\-Datei , mit der die Anwendung auf einem anderen Computer installiert wird.  
  
 In dieser exemplarischen Vorgehensweise wird der Windows Installer zum Bereitstellen der Anwendung verwendet.  Sie können auch ClickOnce verwenden, um eine Anwendung bereitzustellen.  Weitere Informationen finden Sie unter [ClickOnce\-Bereitstellung für Visual C\+\+\-Anwendungen](../ide/clickonce-deployment-for-visual-cpp-applications.md).  Weitere allgemeine Informationen zur Bereitstellung finden Sie unter [Bereitstellen von Anwendungen, Diensten und Komponenten](../Topic/Deploying%20Applications,%20Services,%20and%20Components.md).  
  
## Vorbereitungsmaßnahmen  
  
-   In dieser exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie die Grundlagen der Programmiersprache C\+\+ beherrschen.  
  
-   Es wird ebenfalls davon ausgegangen, dass Sie die früheren exemplarischen Vorgehensweisen dazu abgeschlossen haben, die in [Verwenden der Visual Studio\-IDE für C\+\+\-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md) aufgeführt sind.  
  
-   Diese exemplarische Vorgehensweise kann nicht in den Express\-Editionen von Visual Studio ausgeführt werden.  
  
-   Wenn bisher noch nicht geschehen, laden Sie "InstallShield Limited Edition \(ISLE\)", wie in den Schritten weiter unten in diesem Artikel beschrieben, herunter.  ISLE ist für Visual Studio\-Entwickler kostenlos und ersetzt die Funktionen der Projektvorlagen für Setup und Bereitstellung in früheren Versionen von Visual Studio.  
  
### So installieren Sie die Setup\- und Bereitstellungsprojektvorlage von ISLE  
  
1.  Wenn eine Internetverbindung besteht, wählen Sie auf der Menüleiste **Datei**, **Neu**, **Projekt**, um das Dialogfeld **Neues Projekt** zu öffnen.  
  
2.  Erweitern Sie im linken Bereich des Dialogfelds die Knoten **Installiert**, **Vorlagen** und **Andere Projekttypen**, und wählen Sie dann **Setup und Bereitstellung** aus.  Wählen Sie im mittleren Bereich die Option **InstallShield Limited Edition aktivieren** und dann die Schaltfläche **OK** aus.  
  
3.  Befolgen Sie die Anweisungen zur Installation von "InstallShield Limited Edition für Visual Studio \(ISLE\)".  
  
4.  Nachdem Sie ISLE heruntergeladen, installiert und aktiviert haben, schließen Sie Visual Studio und öffnen Sie das Programm erneut.  
  
5.  Wählen Sie auf der Menüleiste die Optionen **Datei** und **Zuletzt geöffnete Projekte und Projektmappen** aus, und wählen Sie dann die Projektmappe **Spiel** aus, um sie erneut zu öffnen.  
  
### So erstellen Sie ein Setupprojekt und installieren das Programm  
  
1.  Ändern Sie die aktive Lösungskonfiguration in Release.  Wählen Sie auf der Menüleiste die Option **Erstellen** und dann **Konfigurations\-Manager** aus.  Wählen Sie in der Dropdownliste **Konfiguration der aktuellen Projektmappe** im Dialogfeld **Konfigurations\-Manager** die Option **Release** aus.  Wählen Sie zum Speichern der Konfiguration die Schaltfläche **Schließen** aus.  
  
2.  Wählen Sie zum Öffnen des Dialogfelds im **Neues Projekt** auf der Menüleiste die Optionen **Datei**, **Neu** und **Projekt** aus.  
  
3.  Erweitern Sie im linken Bereich des Dialogfelds die Knoten **Installiert**, **Vorlagen** und **Andere Projekttypen**, und wählen Sie dann **Setup und Bereitstellung** aus.  Wählen Sie im mittleren Bereich **Projekt InstallShield Limited Edition** aus.  
  
4.  Geben Sie im Feld **Name** einen Namen für das Datenbankmodell ein.  Geben Sie für dieses Beispiel "Game Installer" ein.  Wählen Sie in der Dropdownliste **Projektmappe** die Option **Zu Projektmappe hinzufügen** aus.  Wählen Sie die Schaltfläche **OK**, um das Setup\-Projekt zu erstellen.  Eine Registerkarte **Projekt\-Assistent \(Game Installer\)** wird im Editorfenster geöffnet.  
  
5.  Wählen Sie am unteren Rand der Registerkarte **Projekt\-Assistent \(Game Installer\)** den Link **Anwendungsinformationen** aus.  
  
6.  Geben Sie auf der Seite **Anwendungsinformationen** Ihren Firmennamen so an, wie er im Installer angezeigt werden soll.  Sie können den eigenen Firmennamen oder "Contoso" für dieses Beispiel verwenden.  Geben Sie den Anwendungsnamen an. In diesem Beispiel geben Sie "Game" an.  Geben Sie die Internetadresse des Unternehmens ein, oder verwenden Sie für dieses Beispiel "http:\/\/www.contoso.com".  
  
7.  Wählen Sie am unteren Rand der Registerkarte **Projekt\-Assistent \(Game Installer\)** den Link **Installationsinterview** aus.  
  
8.  Aktivieren Sie auf der Seite **Installationsinterview** unter **Möchten Sie ein Lizenzvertrag\-Dialogfeld anzeigen** das Optionsfeld **Nein**.  Wählen Sie unter **Möchten Sie Benutzer auffordern, ihren Firmennamen und Benutzernamen einzugeben** das Optionsfeld **Nein** aus.  
  
9. Erweitern Sie im **Projektmappen\-Explorer** das Projekt **Game Installer**, erweitern Sie den Knoten **Setup organisieren**, und öffnen Sie die Seite **Allgemeine Informationen**.  
  
10. Geben Sie auf der Registerkarte **Allgemeine Informationen \(Game Installer\)** im Editorfenster eine **Tagersteller\-ID**, z. B. regid.2012\-12.com.Contoso, an.  
  
11. Erweitern Sie im **Projektmappen\-Explorer** unter dem Projekt **Game Installer** den Knoten **Anwendungsdaten angeben**, und öffnen Sie die Seite **Dateien**.  
  
12. Öffnen Sie auf der Registerkarte **Dateien \(Game Installer\)** im Editorfenster unter **Dateien des Quellcomputers** das Kontextmenü für **Primäre Ausgabe von Game** und wählen Sie **Kopieren** aus.  
  
13. Öffnen Sie ein Kontextmenü im Bereich unter der Spalte **Name** in **Dateien des Zielcomputers**, und wählen Sie **Einfügen** aus.  Ein neues Element namens **Game.Primäre Ausgabe** wird angezeigt.  
  
14. Öffnen Sie im **Projektmappen\-Explorer** unter dem Knoten **Anwendungsdaten angeben** die Seite **Weitervertreibbare Komponenten**.  
  
15. Aktivieren Sie auf der Registerkarte **Weitervertreibbare Komponenten \(Game Installer\)** im Editorfenster das Kontrollkästchen **Visual C\+\+ 11.0 CRT \(x86\)**.  
  
16. Wählen Sie auf der Menüleiste **Erstellen** und **Projektmappe erstellen** aus, um das Spielprojekt und das Game Installer\-Projekt zu erstellen.  
  
17. Suchen Sie im Projektmappenordner das setup.exe\-Programm, das mit dem Game Installer\-Projekt erstellt wurde, und führen Sie es dann zum Installieren der Spielanwendung auf dem Computer aus.  Sie können diese Datei kopieren, um die Anwendung und die erforderlichen Bibliotheksdateien auf einem anderen Computer zu installieren.  
  
18. Sie können im Setup\-Projekt viele Optionen festlegen, um Ihre Anforderungen anpassen.  Weitere Informationen finden Sie im **Projektmappen\-Explorer** unter dem **Game Installer**\-Projekt. Öffnen Sie dort die Seite **Erste Schritte** und wählen Sie dann F1 aus, um die ISLE\-Hilfebibliothek zu öffnen.  
  
## Nächste Schritte  
 **Zurück:** [Exemplarische Vorgehensweise: Debuggen eines Projekts \(C\+\+\)](../ide/walkthrough-debugging-a-project-cpp.md)  
  
## Siehe auch  
 [Visual C\+\+ Guided Tour](assetId:///499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)