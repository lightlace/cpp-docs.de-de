---
title: 'Exemplarische Vorgehensweise: Bereitstellen des Programms (C++) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying applications [C++], walkthroughs
- setup projects [C++]
- program deployments [C++]
- projects [C++], setup
- projects [C++], deploying programs
- application deployment [C++], walkthroughs
ms.assetid: 79e6cc4e-dced-419d-aaf7-d62d1367603f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1753c63673b9dd083e2b690788801bd467938c3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33335535"
---
# <a name="walkthrough-deploying-your-program-c"></a>Exemplarische Vorgehensweise: Bereitstellen des Programms (C++)
Nachdem Sie die Anwendung erstellt haben, indem Sie die früheren exemplarischen Vorgehensweisen vorgenommen haben, die unter [Using the Visual Studio IDE for C++ Desktop Development (Verwenden der Visual Studio-IDE für C++-Desktopentwicklung)](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md) aufgeführt sind, besteht der letzte Schritt in der Erstellung eines Installationsprogramms, damit andere Benutzer das Programm auf ihren Computern installieren können. Dazu fügen Sie der vorhandenen Projektmappe ein neues Projekt hinzu. Die Ausgabe dieses neuen Projekts ist eine setup.exe-Datei , mit der die Anwendung auf einem anderen Computer installiert wird.  
  
 In dieser exemplarischen Vorgehensweise wird der Windows Installer zum Bereitstellen der Anwendung verwendet. Sie können auch ClickOnce verwenden, um eine Anwendung bereitzustellen. Weitere Informationen finden Sie unter [ClickOnce Deployment for Visual C++ Applications](../ide/clickonce-deployment-for-visual-cpp-applications.md). Weitere Informationen über die allgemeine Bereitstellung finden Sie unter [Deploying Applications, Services, and Components (Bereitstellen von Anwendungen, Diensten und Komponenten)](/visualstudio/deployment/deploying-applications-services-and-components).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
  
-   In dieser exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie die Grundlagen der Programmiersprache C++ beherrschen.  
  
-   Es wird ebenfalls davon ausgegangen, dass Sie die früheren exemplarischen Vorgehensweisen abgeschlossen haben, die unter [Using the Visual Studio IDE for C++ Desktop Development (Verwenden der Visual Studio-IDE für die C++-Desktopentwicklung)](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md) aufgeführt sind.  
  
-   Diese exemplarische Vorgehensweise kann nicht in den Express-Editionen von Visual Studio ausgeführt werden.  
  
-   Wenn bisher noch nicht geschehen, laden Sie "InstallShield Limited Edition (ISLE)", wie in den Schritten weiter unten in diesem Artikel beschrieben, herunter. ISLE ist für Visual Studio-Entwickler kostenlos und ersetzt die Funktionen der Projektvorlagen für Setup und Bereitstellung in früheren Versionen von Visual Studio.  
  
### <a name="to-install-the-isle-setup-and-deployment-project-template"></a>So installieren Sie die Setup- und Bereitstellungsprojektvorlage von ISLE  
  
1.  Wenn eine Verbindung zum Internet besteht, klicken Sie in der Menüleiste auf **Datei**, **Neu** und **Projekt**, um das Dialogfeld **Neues Projekt** zu öffnen.  
  
2.  Erweitern Sie im linken Bereich des Dialogfelds die Knoten **Installiert**, **Vorlagen** und **Andere Projekttypen**, und wählen Sie dann **Setup und Bereitstellung** aus. Klicken Sie im mittleren Bereich auf die Option **InstallShield Limited Edition aktivieren** und dann auf die Schaltfläche **OK**.  
  
3.  Befolgen Sie die Anweisungen zur Installation von "InstallShield Limited Edition für Visual Studio (ISLE)".  
  
4.  Nachdem Sie ISLE heruntergeladen, installiert und aktiviert haben, schließen Sie Visual Studio und öffnen Sie das Programm erneut.  
  
5.  Klicken Sie in der Menüleiste auf **Datei** und **Zuletzt geöffnete Projekte und Projektmappen**, und wählen Sie dann Sie Projektmappe **Game** aus, um sie erneut zu öffnen.  
  
### <a name="to-create-a-setup-project-and-install-your-program"></a>So erstellen Sie ein Setupprojekt und installieren das Programm  
  
1.  Ändern Sie die aktive Lösungskonfiguration in Release. Wählen Sie auf der Menüleiste die Option **Erstellen**und dann **Konfigurations-Manager**aus. Wählen Sie **Release** in der Dropdownliste **Konfiguration der aktuellen Projektmappe** im Dialogfeld **Konfigurations-Manager** aus. Klicken Sie auf die Schaltfläche **Schließen**, um die Konfiguration zu speichern.  
  
2.  Klicken Sie in der Menüleiste auf **Datei**, **Neu** und **Projekt**, um das Dialogfeld **Neues Projekt** zu öffnen.  
  
3.  Erweitern Sie im linken Bereich des Dialogfelds die Knoten **Installiert**, **Vorlagen** und **Andere Projekttypen**, und wählen Sie dann **Setup und Bereitstellung** aus. Wählen Sie im mittleren Bereich **InstallShield Limited Edition-Projekt** aus.  
  
4.  Geben Sie im Feld **Name** einen Namen für das Setup-Projekt ein. Geben Sie im Rahmen dieses Beispiels **Game Installer** ein. Wählen Sie in der Dropdownliste **Projektmappe** die Option **Zu Projektmappe hinzufügen** aus. Klicken Sie auf die Schaltfläche **OK**, um das Setup-Projekt zu erstellen. Eine Registerkarte **Projekt-Assistent (Game Installer)** wird im Editorfenster geöffnet.  
  
5.  Klicken Sie am unteren Rand der Registerkarte **Projekt-Assistent (Game Installer)** auf den Link **Anwendungsinformationen**.  
  
6.  Geben Sie auf der Seite **Anwendungsinformationen** Ihren Firmennamen so an, wie er im Installer angezeigt werden soll. Sie können Ihren eigenen Firmennamen oder **Contoso** für dieses Beispiel verwenden. Geben Sie den Anwendungsnamen an. In diesem Beispiel geben Sie **Game** an. Geben Sie die Internetadresse des Unternehmens ein, oder verwenden Sie für dieses Beispiel **http://www.contoso.com**.  
  
7.  Klicken Sie am unteren Rand der Registerkarte **Projekt-Assistent (Game Installer)** auf den Link **Installationsinterview**.  
  
8.  Wählen Sie auf der Seite **Installationsinterview** unter **Möchten Sie ein Lizenzvertrag-Dialogfeld anzeigen** **Nein** aus. Wählen Sie unter **Möchten Sie Benutzer auffordern, ihren Firmennamen und Benutzernamen einzugeben** **Nein** aus.  
  
9. Erweitern Sie im **Projektmappen-Explorer** das Projekt **Game Installer**, erweitern Sie den Knoten **Setup organisieren**, und öffnen Sie die Seite **Allgemeine Informationen**.  
  
10. Geben Sie auf der Registerkarte **Allgemeine Informationen (Game Installer)** im Editorfenster eine **Tagersteller-ID**, z.B. **regid.2012-12.com.Contoso**, an.  
  
11. Erweitern Sie im **Projektmappen-Explorer** unter dem Projekt **Game Installer** den Knoten **Anwendungsdaten angeben**, und öffnen Sie die Seite **Dateien**.  
  
12. Öffnen Sie auf der Registerkarte **Dateien (Game Installer)** im Editorfenster unter **Dateien des Quellcomputers** das Kontextmenü für **Primäre Ausgabe von Game**, und klicken Sie auf **Kopieren**.  
  
13. Öffnen Sie ein Kontextmenü im Bereich unter der Spalte **Name** in **Dateien des Zielcomputers**, und klicken Sie auf **Einfügen**. Ein neues Element namens **Game.Primary Output** wird angezeigt.  
  
14. Öffnen Sie im **Projektmappen-Explorer** unter dem Knoten **Anwendungsdaten angeben** die Seite **Verteilbare Dateien**.  
  
15. Aktivieren Sie auf der Registerkarte **Verteilbare Dateien (Game Installer)** im Editorfenster das Kontrollkästchen **Visual C++ 11.0 CRT (x86)**.  
  
16. Klicken Sie in der Menüleiste auf **Erstellen** und **Projektmappe erstellen**, um das Game-Projekt und das Game Installer-Projekt zu erstellen.  
  
17. Suchen Sie im Projektmappenordner das setup.exe-Programm, das mit dem Game Installer-Projekt erstellt wurde, und führen Sie es dann zum Installieren der Spielanwendung auf dem Computer aus. Sie können diese Datei kopieren, um die Anwendung und die erforderlichen Bibliotheksdateien auf einem anderen Computer zu installieren.  
  
18. Sie können im Setup-Projekt viele Optionen festlegen, um Ihre Anforderungen anpassen. Weitere Informationen finden Sie, indem Sie im **Projektmappen-Explorer** im **Game Installer**-Projekt die Seite **Erste Schritte** öffnen und die Taste F1 drücken, um die ISLE-Hilfebibliothek zu öffnen.  
  
## <a name="next-steps"></a>Nächste Schritte  
 **Zurück:** [Exemplarische Vorgehensweise: Debuggen eines Projekts (C++)](../ide/walkthrough-debugging-a-project-cpp.md)  
  
## <a name="see-also"></a>Siehe auch  
 [C++ Language Reference (C++-Programmiersprachenreferenz)](../cpp/cpp-language-reference.md)   
 [Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)  
 [Deploying Desktop Applications (Bereitstellen von Desktopanwendungen)](../ide/deploying-native-desktop-applications-visual-cpp.md)