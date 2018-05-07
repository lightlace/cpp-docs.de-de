---
title: 'Exemplarische Vorgehensweise: Bereitstellen des Programms (C++) | Microsoft Docs'
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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-deploying-your-program-c"></a>Exemplarische Vorgehensweise: Bereitstellen des Programms (C++)
Nun, dass Sie Ihre Anwendung erstellt haben, Abschließen der zuvor verwandten exemplarischen Vorgehensweisen, die in aufgeführt sind, indem [über die Visual Studio-IDE für C++-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md), im letzten Schritt wird ein Installationsprogramm erstellen, damit andere Benutzer können Installieren Sie das Programm auf ihren Computern. Dazu fügen Sie der vorhandenen Projektmappe ein neues Projekt hinzu. Die Ausgabe dieses neuen Projekts ist eine setup.exe-Datei , mit der die Anwendung auf einem anderen Computer installiert wird.  
  
 In dieser exemplarischen Vorgehensweise wird der Windows Installer zum Bereitstellen der Anwendung verwendet. Sie können auch ClickOnce verwenden, um eine Anwendung bereitzustellen. Weitere Informationen finden Sie unter [ClickOnce Deployment for Visual C++ Applications](../ide/clickonce-deployment-for-visual-cpp-applications.md). Weitere Informationen zur Bereitstellung im Allgemeinen finden Sie unter [Bereitstellen von Anwendungen, Diensten und Komponenten](/visualstudio/deployment/deploying-applications-services-and-components).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
  
-   In dieser exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie die Grundlagen der Programmiersprache C++ beherrschen.  
  
-   Außerdem wird angenommen, dass Sie zuvor verwandten exemplarischen Vorgehensweisen abgeschlossen haben, die aufgelisteten [über die Visual Studio-IDE für C++-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
-   Diese exemplarische Vorgehensweise kann nicht in den Express-Editionen von Visual Studio ausgeführt werden.  
  
-   Wenn bisher noch nicht geschehen, laden Sie "InstallShield Limited Edition (ISLE)", wie in den Schritten weiter unten in diesem Artikel beschrieben, herunter. ISLE ist für Visual Studio-Entwickler kostenlos und ersetzt die Funktionen der Projektvorlagen für Setup und Bereitstellung in früheren Versionen von Visual Studio.  
  
### <a name="to-install-the-isle-setup-and-deployment-project-template"></a>So installieren Sie die Setup- und Bereitstellungsprojektvorlage von ISLE  
  
1.  Wenn Sie mit dem Internet, in der Menüleiste verbunden sind, wählen **Datei**, **neu**, **Projekt** So öffnen die **neues Projekt** (Dialogfeld).  
  
2.  Erweitern Sie im linken Bereich des Dialogfelds die **installiert**, **Vorlagen**, und **andere Projekttypen** Knoten, und wählen Sie dann **Setup und Bereitstellung**. Wählen Sie im mittleren Bereich **InstallShield Limited Edition aktivieren** und wählen Sie dann die **OK** Schaltfläche.  
  
3.  Befolgen Sie die Anweisungen zur Installation von "InstallShield Limited Edition für Visual Studio (ISLE)".  
  
4.  Nachdem Sie ISLE heruntergeladen, installiert und aktiviert haben, schließen Sie Visual Studio und öffnen Sie das Programm erneut.  
  
5.  Wählen Sie in der Menüleiste **Datei**, **zuletzt geöffnete Projekte und Projektmappen**, und wählen Sie dann die **Spiel** Lösung, um es erneut zu öffnen.  
  
### <a name="to-create-a-setup-project-and-install-your-program"></a>So erstellen Sie ein Setupprojekt und installieren das Programm  
  
1.  Ändern Sie die aktive Lösungskonfiguration in Release. Wählen Sie auf der Menüleiste die Option **Erstellen**und dann **Konfigurations-Manager**aus. In der **Configuration Manager** Dialogfeld auf die **aktive Projektmappenkonfiguration** Dropdown-Liste **Version**. Wählen Sie die **schließen** Schaltfläche, um die Konfiguration zu speichern.  
  
2.  Wählen Sie in der Menüleiste **Datei**, **neu**, **Projekt** So öffnen die **neues Projekt** (Dialogfeld).  
  
3.  Erweitern Sie im linken Bereich des Dialogfelds die **installiert**, **Vorlagen**, und **andere Projekttypen** Knoten, und wählen Sie dann **Setup und Bereitstellung**. Wählen Sie im mittleren Bereich **InstallShield Limited Edition-Projekt**.  
  
4.  Geben Sie einen Namen für das Setup-Projekt in der **Namen** Feld. In diesem Beispiel geben Sie **Game Installer**. In der **Lösung** Dropdown-Liste **zu Projektmappe hinzufügen**. Wählen Sie die **OK** Schaltfläche, um das Setup-Projekt zu erstellen. Ein **Projekt-Assistent (Game Installer)** Registerkarte im Editor-Fenster wird geöffnet.  
  
5.  Am unteren Rand der **Projekt-Assistent (Game Installer)** Registerkarte, und wählen Sie die **Anwendungsinformationen** Link.  
  
6.  Auf der **Anwendungsinformationen** Seite, geben Sie den Namen Ihres Unternehmens, wie Sie im Installer angezeigt werden soll. Sie können den eigenen Firmennamen, in diesem Beispiel verwenden oder **Contoso**. Geben Sie den Anwendungsnamen an. Geben Sie in diesem Beispiel **Spiel**. Geben Sie die Internetadresse des Unternehmens, oder verwenden Sie für dieses Beispiel **http://www.contoso.com**.  
  
7.  Am unteren Rand der **Projekt-Assistent (Game Installer)** Registerkarte, und wählen Sie die **Installationsinterview** Link.  
  
8.  Auf der **Installationsinterview** Seite **möchten Sie ein Lizenzvertrag-Dialogfeld anzeigen**, wählen die **keine** Optionsfeld. Unter **möchten Sie den Benutzer zur Eingabe von ihren Firmennamen und Benutzernamen auffordern**, wählen die **keine** Optionsfeld.  
  
9. In **Projektmappen-Explorer**, erweitern Sie die **Game Installer** Projekt, erweitern Sie die **Setup organisieren** Knoten, und öffnen Sie dann die **Syntaxinformationen** Seite.  
  
10. Auf der **allgemeine Informationen (Game Installer)** Registerkarte im Editor-Fenster, geben Sie einen **Tag Creator ID**, z. B. **2012-12.com.contoso, an**.  
  
11. In **Projektmappen-Explorer**unter der **Game Installer** Projekt, erweitern Sie die **Anwendungsdaten** Knoten, und öffnen Sie dann die **Dateien** Seite ".  
  
12. Auf der **Dateien (Game Installer)** Registerkarte im Editor-Fenster, unter **Quelldateien des Computers**, öffnen Sie das Kontextmenü für **primäre Ausgabe von Game** , und wählen Sie **Kopie**.  
  
13. Öffnen Sie ein Kontextmenü im Bereich unter der **Namen** Spalte in **Dateien des Zielcomputers**, und wählen Sie **einfügen**. Ein neues Element mit dem Namen **Game Ausgabe** angezeigt wird.  
  
14. In **Projektmappen-Explorer**unter der **Anwendungsdaten** geöffneten Knoten die **verteilbare Komponenten** Seite.  
  
15. Auf der **verteilbare Komponenten (Game Installer)** Registerkarte im Editor-Fenster, wählen Sie die **Visual C++ 11.0 CRT (x86)** Kontrollkästchen.  
  
16. Wählen Sie in der Menüleiste **erstellen**, **Projektmappe** um das Spielprojekt und das Game Installer-Projekt zu erstellen.  
  
17. Suchen Sie im Projektmappenordner das setup.exe-Programm, das mit dem Game Installer-Projekt erstellt wurde, und führen Sie es dann zum Installieren der Spielanwendung auf dem Computer aus. Sie können diese Datei kopieren, um die Anwendung und die erforderlichen Bibliotheksdateien auf einem anderen Computer zu installieren.  
  
18. Sie können im Setup-Projekt viele Optionen festlegen, um Ihre Anforderungen anpassen. Weitere Informationen in **Projektmappen-Explorer**unter der **Game Installer** -Projekt, öffnen die **Einstieg** Seite und wählen Sie dann die F1-Taste, um die ISLE-Hilfebibliothek zu öffnen.  
  
## <a name="next-steps"></a>Nächste Schritte  
 **Vorherige:** [Exemplarische Vorgehensweise: Debuggen eines Projekts (C++)](../ide/walkthrough-debugging-a-project-cpp.md)  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)  
 [Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)