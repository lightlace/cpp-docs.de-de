---
title: Bereitstellen einer Visual C++-Anwendung mithilfe eines Setup-Projekts
ms.date: 09/17/2018
helpviewer_keywords:
- deployment for Visual C++
ms.assetid: 66735cda-8fe3-4211-a19a-2cf717a12a3f
ms.openlocfilehash: 3dc607ea082e31ba73f34ce1ca8acd3ebc78292a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565593"
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-a-setup-project"></a>Exemplarische Vorgehensweise: Bereitstellen einer Visual C++-Anwendung mithilfe eines Setup-Projekts

In diesem Artikel wird beschrieben, wie Sie ein Setup-Projekt verwenden, um eine Visual C++-Anwendung bereitzustellen.

## <a name="prerequisites"></a>Erforderliche Komponenten

Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:

- Einen Computer, auf dem Visual Studio installiert ist.

- Einen zusätzlichen Computer, auf dem keine Visual C++-Bibliotheken vorhanden sind.

### <a name="to-deploy-an-application-by-using-a-setup-project"></a>So stellen Sie eine Anwendung mithilfe eines Setup-Projekts bereit

1. Erstellen Sie ein neues Projekt. Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.

1. Verwenden Sie den **MFC-Anwendungs-Assistenten** zum Erstellen einer neuen Visual Studio-Projektmappe. Erweitern Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C++**, klicken Sie auf **MFC** und dann auf **MFC-Anwendung**, geben Sie dann einen Namen für das Projekt ein, und klicken Sie auf **OK**, um den Assistenten zu finden. Klicken Sie auf **Fertig stellen**.

   > [!NOTE]
   > Wenn der Typ **MFC-Anwendung** nicht vorhanden ist:<br/>
   > **Visual Studio 2017**: Wählen Sie im Dialogfeld **Neues Projekt** im linken Bereich **Visual Studio-Installer öffnen** aus. Installieren Sie die Option unter **Desktopentwicklung mit C++** im Abschnitt **Optionale Komponenten** mit dem Namen **Visual C++ MFC für x86 und x64**.<br/>
   > **Visual Studio 2015**: Klicken Sie auf die Windows-Schaltfläche „Start“, und geben Sie **Software** ein. Öffnen Sie das Programm aus der Ergebnisliste, und suchen Sie dann Ihre Microsoft Visual Studio 2015-Installation in der Liste der installierten Programme. Doppelklicken Sie darauf, und wählen Sie dann **Ändern** und die Komponente **Microsoft Foundation Classes** unter **Visual C++** aus.

1. Ändern Sie die aktive Projektmappenkonfiguration in **Release**. Klicken Sie im Menü **Build** auf **Konfigurations-Manager**. Wählen Sie im Dialogfeld **Konfigurations-Manager** im Dropdownfeld **Aktive Projektmappenkonfiguration** die Option **Release** aus. Klicken Sie auf **Schließen**.

1. Drücken Sie **STRG**+**UMSCHALT**+**B**, um die Anwendung zu erstellen. Oder klicken Sie im Menü **Build** auf **Projektmappe erstellen**. Das Erstellen der Anwendung ermöglicht es dem Setupprojekt, die Ausgabe dieses MFC-Anwendungsprojekts zu verwenden.

1. Wenn dies noch nicht geschehen ist, laden Sie die Erweiterung Microsoft Visual Studio-Installerprojekte herunter. Die Erweiterung ist für Visual Studio-Entwickler kostenlos und fügt Visual Studio die Funktionen der Projektvorlagen für Setup und Bereitstellung hinzu. Wenn Sie mit dem Internet verbunden sind, wählen Sie in Visual Studio **Extras** > **Erweiterungen und Updates** aus. Wählen Sie im Dialogfeld **Erweiterungen und Updates** die Registerkarte **Online** aus, und geben Sie *Microsoft Visual Studio-Installerprojekte* in das Suchfeld ein. Drücken Sie die **EINGABETASTE**, wählen Sie **Microsoft Visual Studio \<Version > Installerprojekte** aus, und klicken Sie auf **Herunterladen**. Wählen Sie die Ausführung und Installation der Erweiterung aus, und starten Sie Visual Studio neu.

1. Klicken Sie in der Menüleiste auf **Datei** >  **Zuletzt geöffnete Projekte und Projektmappen**, und öffnen Sie Ihr Projekt dann erneut.

1. Klicken Sie in der Menüleiste auf **Datei** > **Neu** > **Projekt**, um das Dialogfeld **Neues Projekt** zu öffnen. Erweitern Sie dann im linken Bereich des Dialogfelds die Knoten **Installiert** > **Andere Projekttypen**, und wählen Sie dann **Visual Studio-Installer** aus. Wählen Sie im mittleren Bereich die Option **Setupprojekt** aus.

1. Geben Sie im Feld **Name** einen Namen für das Setup-Projekt ein. Wählen Sie in der Dropdownliste **Projektmappe** die Option **Zu Projektmappe hinzufügen** aus. Klicken Sie auf die Schaltfläche **OK**, um das Setup-Projekt zu erstellen. Eine Registerkarte **Datei-Assistent (ProjektName)** wird im Editor-Fenster geöffnet.

1. Klicken Sie mit der rechten Maustaste auf den Knoten **Anwendungsordner**, und wählen Sie **Hinzufügen** > **Projektausgabe** aus, um das Dialogfeld **Projektausgabegruppe hinzufügen** zu öffnen. Wählen Sie im Dialogfeld **Primäre Ausgabe** aus, und klicken Sie dann auf **OK**. Ein neues Element mit dem Namen **Primäre Ausgabe aus ProjektName (aktiv)** wird angezeigt.

1. Klicken Sie mit der rechten Maustaste auf den Knoten **Anwendungsordner**, und wählen Sie **Hinzufügen** > **Assembly** aus, um das Dialogfeld **Komponente auswählen** zu öffnen. Wählen Sie alle erforderlichen DLLs aus, die das Programm benötigt, und fügen Sie sie hinzu, wie im Artikel [Ermitteln der zu verteilenden DLLs](determining-which-dlls-to-redistribute.md) beschrieben.

1. Wählen Sie das Element **Primäre Ausgabe aus ProjektName (aktiv)** aus, klicken Sie mit der rechten Maustaste, und wählen Sie **Verknüpfung mit primärer Ausgabe aus ProjektName (aktiv) erstellen** aus. Ein neues Element mit dem Namen **Verknüpfung mit primärer Ausgabe aus ProjektName (aktiv)** wird angezeigt. Sie können das Verknüpfungselement umbenennen und dann mithilfe von Drag & Drop in den Knoten **Menü Benutzerprogramme** auf der linken Seite des Fensters ziehen.

1. Klicken Sie in der Menüleiste auf **Build** > **Konfigurations-Manager**. Aktivieren Sie in der Tabelle **Projekt** unter der Spalte **Erstellen** das Kontrollkästchen für das Bereitstellungsprojekt. Klicken Sie auf **Schließen**.

1. Klicken Sie in der Menüleiste auf **Erstellen** > **Projektmappe** erstellen, um das MFC-Projekt und das Bereitstellungsprojekt zu erstellen.

1. Suchen Sie im Projektmappenordner nach dem Programm „setup.exe“, das aus dem Bereitstellungsprojekt erstellt wurde. Sie können diese Datei (und die MSI-Datei) kopieren, um die Anwendung und die erforderlichen Bibliotheksdateien auf einem anderen Computer zu installieren. Führen Sie das Setupprogramm auf einem zweiten Computer aus, der über keine der Visual C++-Bibliotheken verfügt.

## <a name="see-also"></a>Siehe auch

[Bereitstellungsbeispiele](deployment-examples.md)<br/>
