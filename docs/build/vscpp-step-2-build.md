---
title: Erstellen und Ausführen eines C++-Konsolen-App-Projekts
description: Erstellen Sie und führen Sie eine Hello World-Konsolenanwendung in Visual C++
ms.custom: mvc
ms.date: 12/12/2017
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d71-719d-42dc-90d7-1d0ca31a2f55
ms.openlocfilehash: 59813a553a9034503d8bf432400db31e6e3d9478
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62314243"
---
# <a name="build-and-run-a-c-console-app-project"></a>Erstellen und Ausführen eines C++-Konsolen-App-Projekts

Wenn Sie eine C++-Konsolen-app-Projekts erstellt und Ihr Code eingegeben haben, können Sie erstellen und führen Sie es in Visual Studio und es dann als eine eigenständige app von der Befehlszeile aus ausführen.

## <a name="prerequisites"></a>Vorraussetzungen

- Visual Studio mit der Workload „Desktopentwicklung mit C++“ muss auf Ihrem Computer installiert sein und ausgeführt werden. Wenn sie noch nicht installiert ist, führen Sie die Schritte in [Installieren von C++-Unterstützung in Visual Studio](vscpp-step-0-installation.md).

- Erstellen einer "Hello, World!" Projekt aus, und geben Sie deren Quellcode. Wenn Sie dies noch nicht geschehen, führen Sie die Schritte in [erstellen Sie eine C++-Konsolen-app-Projekts](vscpp-step-1-create.md).

Wenn Visual Studio wie folgt aussieht, sind Sie bereit zum Erstellen und Ausführen Ihrer app:

   ![Erstellen Sie das neue Projekt](media/vscpp-ready-to-build.png "bereit, um das neue Projekt zu erstellen.")

## <a name="build-and-run-your-code-in-visual-studio"></a>Erstellen und Ausführen von Code in Visual Studio

1. Wählen Sie zum Erstellen Ihres Projekts aus dem Menü **Erstellen** die Option **Projektmappe erstellen** aus. Im Fenster **Ausgabe** wird das Ergebnis des Erstellungsprozess angezeigt.

   ![Erstellen des Projekts](media/vscpp-build-solution.gif "Erstellen des Projekts")

1. Klicken Sie zum Ausführen des Codes auf der Menüleiste auf **Debuggen** > **Ohne Debuggen starten**.

   ![Starten des Projekts](media/vscpp-start-without-debugging.gif "Starten des Projekts")

   Ein Konsolenfenster wird geöffnet, und Ihre App daraufhin ausgeführt. Wenn Sie eine Konsolen-App in Visual Studio starten, führt diese Ihren Code aus und gibt dann „Press any key to continue sein. .“ (Beliebige Taste zum Fortfahren drücken) zurück, damit Sie sich die Ausgabe ansehen können.

Herzlichen Glückwunsch! Sie haben Ihre erste „Hallo, Welt!“- Konsolen-App in Visual Studio erstellt! Drücken Sie eine Taste, um das Konsolenfenster zu schließen, und kehren Sie zu Visual Studio zurück.

[Ein Problem ist aufgetreten.](#build-and-run-your-code-in-visual-studio-issues)

## <a name="run-your-code-in-a-command-window"></a>Führen Sie den Code in einem Befehlsfenster

Normalerweise führen Sie an der Eingabeaufforderung ein, nicht in Visual Studio-Konsolen-apps aus. Nachdem Ihre app von Visual Studio erstellt wurde, können Sie ihn in einem beliebigen Befehlsfenster ausführen. So sieht das finden und Ausführen der neuen app in einem Eingabeaufforderungsfenster aus.

1. In **Projektmappen-Explorer**, wählen Sie die HelloWorld-Projektmappe, und mit der rechten Maustaste um das Kontextmenü zu öffnen. Wählen Sie **Ordner in Datei-Explorer öffnen** zum Öffnen einer **Datei-Explorer** Fenster im Projektmappenordner "HelloWorld".

1. In der **Datei-Explorer** Fenster öffnen Sie den Ordner "Debug". Ihre app HelloWorld.exe und einigen anderen Debuggen-Dateien enthält. HelloWorld.exe wählen Sie die UMSCHALTTASTE gedrückt halten und mit der rechten Maustaste um das Kontextmenü zu öffnen. Wählen Sie **als Pfad kopieren** auf den Pfad zu Ihrer app in die Zwischenablage zu kopieren.

1. Um ein Eingabeaufforderungsfenster zu öffnen, drücken Sie die Windows-R zum Öffnen der **ausführen** Dialogfeld. Geben Sie *cmd.exe* in die **öffnen** Textfeld, wählen Sie dann **OK** ein Eingabeaufforderungsfenster ausführen.

1. Klicken Sie im Eingabeaufforderungsfenster Befehl mit der rechten Maustaste den Pfad zu Ihrer app in der Befehlszeile einfügen. Drücken Sie die EINGABETASTE, um die Anwendung auszuführen.

   ![Führen Sie die app an der Eingabeaufforderung](media/vscpp-run-in-cmd.gif "führen Sie die app an der Eingabeaufforderung")

Herzlichen Glückwunsch, Sie erstellt haben, und führen Sie eine Konsolen-app in Visual Studio!

[Ein Problem ist aufgetreten.](#run-your-code-in-a-command-window-issues)

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie erstellt und diese einfache app ausgeführt haben, können Sie sich für komplexere Projekte. Finden Sie unter [mithilfe von Visual Studio-IDE für C++-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md) ausführlichere Exemplarische Vorgehensweisen, in denen die Funktionen von Visual C++ in Visual Studio untersucht.

## <a name="troubleshooting-guide"></a>Handbuch zur Problembehandlung

Sind Sie hier für Lösungen für häufige Probleme, wenn Sie Ihr erstes C++-Projekt erstellen.

### <a name="build-and-run-your-code-in-visual-studio-issues"></a>Erstellen und Ausführen von Code in Visual Studio-Probleme

Wenn rote Wellenlinien unter alle Elemente in der Quellcode-Editor angezeigt werden, sind für der Build möglicherweise Fehler oder Warnungen. Überprüfen Sie, dass Ihr Code im Beispiel in der Schreibweise, Satzzeichen und Groß-/Kleinschreibung übereinstimmt.

[Zurück.](#build-and-run-your-code-in-visual-studio)

### <a name="run-your-code-in-a-command-window-issues"></a>Führen Sie den Code in einem Befehlsfenster Probleme

Sie können auch in den Debugmodus Projektmappenordner in der Befehlszeile zum Ausführen der app navigieren. Sie können nicht aus anderen Verzeichnissen Ihre app ausführen, ohne den Pfad zu der app. Allerdings können Sie Ihre app in ein anderes Verzeichnis kopieren und von dort ausführen.

Wenn Sie nicht sehen **als Pfad kopieren** im Kontextmenü die Option, klicken Sie im Menü zu schließen, und klicken Sie dann die UMSCHALTTASTE gedrückt halten, während sie erneut zu öffnen. Dies wird nur ergänzend bereitgestellt. Sie können auch kopieren Sie den Pfad zu dem Ordner, aus der Suchleiste des Datei-Explorer und fügen Sie ihn in die **ausführen** im Dialogfeld, und geben Sie den Namen der ausführbaren Datei am Ende. Es ist noch ein wenig mehr Tipperei, aber das gleiche Ergebnis hat.

[Zurück.](#run-your-code-in-a-command-window)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
