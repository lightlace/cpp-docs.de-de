---
title: Bereitstellen einer Visual C++-Anwendung mithilfe eines Setup-Projekts
ms.date: 04/25/2019
helpviewer_keywords:
- deployment for Visual C++
ms.assetid: 66735cda-8fe3-4211-a19a-2cf717a12a3f
ms.openlocfilehash: 6829e917ed0a0e27bea7f42eb9bcfb2b9ad5d2e1
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877382"
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-a-setup-project"></a>Exemplarische Vorgehensweise: Bereitstellen einer Visual C++-Anwendung mithilfe eines Setupprojekts

In diesem Artikel wird beschrieben, wie Sie ein Setup-Projekt verwenden, um eine Visual C++-Anwendung bereitzustellen.

## <a name="prerequisites"></a>Vorraussetzungen

Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:

- Einen Computer, auf dem Visual Studio installiert ist.

- Einen zusätzlichen Computer, auf dem keine Visual C++-Bibliotheken vorhanden sind.

## <a name="create-the-setup-project"></a>Erstellen Sie das Setup-Projekt

Anweisungen zum Erstellen eines Setup-Projekts hängt davon ab, welche Version von Visual Studio, die Sie installiert haben. Stellen Sie sicher, dass Sie die Auswahl für die Version in der Zielauswahl oben links auf die richtige Version festgelegt haben.

::: moniker range="=vs-2019"

### <a name="to-create-the-project-in-visual-studio-2019"></a>Zum Erstellen des Projekts in Visual Studio-2019

1. Wählen Sie auf der Menüleiste **Datei** > **neu** > **Projekt** zum Öffnen der **Erstellen eines neuen Projekts** Dialogfeld.

   ![MFC-Anwendungsprojekt](media/vs2019-mfc-app-new-project.png "neue MFC-app")

1. Geben Sie am oberen Rand des Dialogfelds, `MFC` in die Suche ein, und wählen Sie dann **MFC‑Anwendung** in der Ergebnisliste aus. Wenn es nicht angezeigt wird, müssen Sie die Visual Studio-Installer-Anwendung über das Windows-Startmenü starten, und klicken auf die  **C++ Desktopentwicklung Workload** Kachel. Klicken Sie unter **Einzelkomponenten**, stellen Sie sicher, dass die MFC-Komponente aktiviert ist.

1. Klicken Sie in der nächsten Seite Geben Sie einen Namen für das Projekt, und geben Sie den Speicherort des Projekts ein, bei Bedarf.

1. Wählen Sie die **erstellen** klicken, um das Client-Projekt zu erstellen. Wenn die **MFS-Anwendungsassistenten** angezeigt wird, übernehmen Sie alle Standardeinstellungen.

1. Ändern Sie die aktive Projektmappenkonfiguration in **Release**. Klicken Sie im Menü **Build** auf **Konfigurations-Manager**. Wählen Sie im Dialogfeld **Konfigurations-Manager** im Dropdownfeld **Aktive Projektmappenkonfiguration** die Option **Release** aus. Klicken Sie auf **Schließen**.

1. Drücken Sie **STRG**+**UMSCHALT**+**B**, um die Anwendung zu erstellen. Oder klicken Sie im Menü **Build** auf **Projektmappe erstellen**. Das Erstellen der Anwendung ermöglicht es dem Setupprojekt, die Ausgabe dieses MFC-Anwendungsprojekts zu verwenden.

1. Wenn dies noch nicht geschehen ist, laden Sie die Erweiterung Microsoft Visual Studio-Installerprojekte herunter. Die Erweiterung ist für Visual Studio-Entwickler kostenlos und fügt Visual Studio die Funktionen der Projektvorlagen für Setup und Bereitstellung hinzu. Wenn Sie mit dem Internet in Visual Studio verbunden sind, wählen Sie **Erweiterungen** > **Verwalten von Erweiterungen**. Wählen Sie im Dialogfeld **Erweiterungen und Updates** die Registerkarte **Online** aus, und geben Sie *Microsoft Visual Studio-Installerprojekte* in das Suchfeld ein. Drücken Sie **EINGABETASTE**Option **Microsoft Visual Studio \<Version > Installer-Projekte**, und klicken Sie auf **herunterladen**. Wählen Sie die Ausführung und Installation der Erweiterung aus, und starten Sie Visual Studio neu.

   ![Visual Studio-Setup-Projekt](media/vs2019-extension-dialog-installer-project.png "nennen Sie das Clientprojekt")

1. Wählen Sie in der Visual Studio-Menüleiste **Datei** > **zuletzt geöffnete Projekte und Projektmappen**, und wählen Sie dann auf das Projekt erneut öffnen.

1. Wählen Sie auf der Menüleiste **Datei** > **neu** > **Projekt** zum Öffnen der **Erstellen eines neuen Projekts** Dialogfeld. Geben Sie in das Suchfeld "Setup", und wählen Sie in der Ergebnisliste **Setupprojekt**.

1. Geben Sie im Feld **Name** einen Namen für das Setup-Projekt ein. Wählen Sie in der Dropdownliste **Projektmappe** die Option **Zu Projektmappe hinzufügen** aus. Klicken Sie auf die Schaltfläche **OK**, um das Setup-Projekt zu erstellen. Eine Registerkarte **Datei-Assistent (ProjektName)** wird im Editor-Fenster geöffnet.

::: moniker-end

::: moniker range="=vs-2017"

### <a name="to-create-the-project-in-visual-studio-2017"></a>Zum Erstellen des Projekts in Visual Studio 2017

1. Erstellen Sie ein neues Projekt. Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.

1. Verwenden der **MFS-Anwendungsassistenten** um eine neue Visual Studio-Projektmappe zu erstellen. Erweitern Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C++**, klicken Sie auf **MFC** und dann auf **MFC-Anwendung**, geben Sie dann einen Namen für das Projekt ein, und klicken Sie auf **OK**, um den Assistenten zu finden. Klicken Sie auf **Fertig stellen**.

   > [!NOTE]
   > Wenn die **MFC-Anwendung** Typ ist nicht vorhanden, wählen Sie **Visual Studio-Installer öffnen** im linken Bereich des der **neues Projekt** Dialogfeld. Installieren Sie die Option unter **Desktopentwicklung mit C++** im Abschnitt **Optionale Komponenten** mit dem Namen **Visual C++ MFC für x86 und x64**.

1. Ändern Sie die aktive Projektmappenkonfiguration in **Release**. Klicken Sie im Menü **Build** auf **Konfigurations-Manager**. Wählen Sie im Dialogfeld **Konfigurations-Manager** im Dropdownfeld **Aktive Projektmappenkonfiguration** die Option **Release** aus. Klicken Sie auf **Schließen**.

1. Drücken Sie **STRG**+**UMSCHALT**+**B**, um die Anwendung zu erstellen. Oder klicken Sie im Menü **Build** auf **Projektmappe erstellen**. Das Erstellen der Anwendung ermöglicht es dem Setupprojekt, die Ausgabe dieses MFC-Anwendungsprojekts zu verwenden.

1. Wenn dies noch nicht geschehen ist, laden Sie die Erweiterung Microsoft Visual Studio-Installerprojekte herunter. Die Erweiterung ist für Visual Studio-Entwickler kostenlos und fügt Visual Studio die Funktionen der Projektvorlagen für Setup und Bereitstellung hinzu. Wenn Sie mit dem Internet verbunden sind, wählen Sie in Visual Studio **Extras** > **Erweiterungen und Updates** aus. Wählen Sie im Dialogfeld **Erweiterungen und Updates** die Registerkarte **Online** aus, und geben Sie *Microsoft Visual Studio-Installerprojekte* in das Suchfeld ein. Drücken Sie **EINGABETASTE**Option **Microsoft Visual Studio \<Version > Installer-Projekte**, und klicken Sie auf **herunterladen**. Wählen Sie die Ausführung und Installation der Erweiterung aus, und starten Sie Visual Studio neu.

1. Wählen Sie auf der Menüleiste **Datei** > **zuletzt geöffnete Projekte und Projektmappen**, und wählen Sie dann auf das Projekt erneut öffnen.

1. Klicken Sie in der Menüleiste auf **Datei** > **Neu** > **Projekt**, um das Dialogfeld **Neues Projekt** zu öffnen. Erweitern Sie dann im linken Bereich des Dialogfelds die Knoten **Installiert** > **Andere Projekttypen**, und wählen Sie dann **Visual Studio-Installer** aus. Wählen Sie im mittleren Bereich die Option **Setupprojekt** aus.

1. Geben Sie im Feld **Name** einen Namen für das Setup-Projekt ein. Wählen Sie in der Dropdownliste **Projektmappe** die Option **Zu Projektmappe hinzufügen** aus. Klicken Sie auf die Schaltfläche **OK**, um das Setup-Projekt zu erstellen. Eine Registerkarte **Datei-Assistent (ProjektName)** wird im Editor-Fenster geöffnet.

::: moniker-end

::: moniker range="=vs-2015"

### <a name="to-create-the-project-in-visual-studio-2015"></a>Zum Erstellen des Projekts in Visual Studio 2015

1. Erstellen Sie ein neues Projekt. Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.

1. Verwenden der **MFS-Anwendungsassistenten** um eine neue Visual Studio-Projektmappe zu erstellen. Erweitern Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C++**, klicken Sie auf **MFC** und dann auf **MFC-Anwendung**, geben Sie dann einen Namen für das Projekt ein, und klicken Sie auf **OK**, um den Assistenten zu finden. Klicken Sie auf **Fertig stellen**.

   > [!NOTE]
   > Wenn die **MFC-Anwendung** Typ ist nicht vorhanden, klicken Sie auf die Schaltfläche "Windows Start" und den Typ **Software**. Öffnen Sie das Programm aus der Ergebnisliste, und suchen Sie dann Ihre Microsoft Visual Studio 2015-Installation in der Liste der installierten Programme. Doppelklicken Sie darauf, und wählen Sie dann **Ändern** und die Komponente **Microsoft Foundation Classes** unter **Visual C++** aus.

1. Ändern Sie die aktive Projektmappenkonfiguration in **Release**. Von der **erstellen** , wählen Sie im Menü **Configuration Manager**. Wählen Sie im Dialogfeld **Konfigurations-Manager** im Dropdownfeld **Aktive Projektmappenkonfiguration** die Option **Release** aus. Klicken Sie auf **Schließen**.

1. Drücken Sie **STRG**+**UMSCHALT**+**B**, um die Anwendung zu erstellen. Oder klicken Sie im Menü **Build** auf **Projektmappe erstellen**. Das Erstellen der Anwendung ermöglicht es dem Setupprojekt, die Ausgabe dieses MFC-Anwendungsprojekts zu verwenden.

1. Wenn dies noch nicht geschehen ist, laden Sie die Erweiterung Microsoft Visual Studio-Installerprojekte herunter. Die Erweiterung ist für Visual Studio-Entwickler kostenlos und fügt Visual Studio die Funktionen der Projektvorlagen für Setup und Bereitstellung hinzu. Wenn Sie mit dem Internet verbunden sind, wählen Sie in Visual Studio **Extras** > **Erweiterungen und Updates** aus. Wählen Sie im Dialogfeld **Erweiterungen und Updates** die Registerkarte **Online** aus, und geben Sie *Microsoft Visual Studio-Installerprojekte* in das Suchfeld ein. Drücken Sie **EINGABETASTE**Option **Microsoft Visual Studio \<Version > Installer-Projekte**, und klicken Sie auf **herunterladen**. Wählen Sie die Ausführung und Installation der Erweiterung aus, und starten Sie Visual Studio neu.

1. Wählen Sie auf der Menüleiste **Datei** > **zuletzt geöffnete Projekte und Projektmappen**, und wählen Sie dann auf das Projekt erneut öffnen.

1. Klicken Sie in der Menüleiste auf **Datei** > **Neu** > **Projekt**, um das Dialogfeld **Neues Projekt** zu öffnen. Erweitern Sie dann im linken Bereich des Dialogfelds die Knoten **Installiert** > **Andere Projekttypen**, und wählen Sie dann **Visual Studio-Installer** aus. Wählen Sie im mittleren Bereich die Option **Setupprojekt** aus.

1. Geben Sie im Feld **Name** einen Namen für das Setup-Projekt ein. Wählen Sie in der Dropdownliste **Projektmappe** die Option **Zu Projektmappe hinzufügen** aus. Klicken Sie auf die Schaltfläche **OK**, um das Setup-Projekt zu erstellen. Eine Registerkarte **Datei-Assistent (ProjektName)** wird im Editor-Fenster geöffnet.

::: moniker-end

## <a name="add-items-to-the-project"></a>Elemente zum Projekt hinzufügen

1. Klicken Sie mit der rechten Maustaste auf den Knoten **Anwendungsordner**, und wählen Sie **Hinzufügen** > **Projektausgabe** aus, um das Dialogfeld **Projektausgabegruppe hinzufügen** zu öffnen. Wählen Sie im Dialogfeld **Primäre Ausgabe** aus, und klicken Sie dann auf **OK**. Ein neues Element mit dem Namen **Primäre Ausgabe aus ProjektName (aktiv)** wird angezeigt.

1. Klicken Sie mit der rechten Maustaste auf den Knoten **Anwendungsordner**, und wählen Sie **Hinzufügen** > **Assembly** aus, um das Dialogfeld **Komponente auswählen** zu öffnen. Wählen Sie alle erforderlichen DLLs aus, die das Programm benötigt, und fügen Sie sie hinzu, wie im Artikel [Ermitteln der zu verteilenden DLLs](determining-which-dlls-to-redistribute.md) beschrieben.

1. Wählen Sie das Element **Primäre Ausgabe aus ProjektName (aktiv)** aus, klicken Sie mit der rechten Maustaste, und wählen Sie **Verknüpfung mit primärer Ausgabe aus ProjektName (aktiv) erstellen** aus. Ein neues Element mit dem Namen **Verknüpfung mit primärer Ausgabe aus ProjektName (aktiv)** wird angezeigt. Sie können das Verknüpfungselement umbenennen und dann mithilfe von Drag & Drop in den Knoten **Menü Benutzerprogramme** auf der linken Seite des Fensters ziehen.

1. Klicken Sie in der Menüleiste auf **Build** > **Konfigurations-Manager**. Aktivieren Sie in der Tabelle **Projekt** unter der Spalte **Erstellen** das Kontrollkästchen für das Bereitstellungsprojekt. Klicken Sie auf **Schließen**.

1. Klicken Sie in der Menüleiste auf **Erstellen** > **Projektmappe** erstellen, um das MFC-Projekt und das Bereitstellungsprojekt zu erstellen.

1. Suchen Sie im Projektmappenordner nach dem Programm „setup.exe“, das aus dem Bereitstellungsprojekt erstellt wurde. Sie können diese Datei (und die MSI-Datei) kopieren, um die Anwendung und die erforderlichen Bibliotheksdateien auf einem anderen Computer zu installieren. Führen Sie das Setupprogramm auf einem zweiten Computer aus, der über keine der Visual C++-Bibliotheken verfügt.

## <a name="see-also"></a>Siehe auch

[Bereitstellungsbeispiele](deployment-examples.md)<br/>
