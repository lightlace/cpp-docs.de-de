---
title: "Erstellen und Ausführen ein C++-Konsolen-app-Projekts | Microsoft Docs"
description: "Installieren Sie Visual Studio-Unterstützung für Visual C++"
ms.custom: mvc
ms.date: 12/12/2017
ms.topic: get-started-article
ms.technology:
- devlang-C++
ms.devlang: C++
dev_langs:
- C++
ms.assetid: 45138d71-719d-42dc-90d7-1d0ca31a2f55
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2bbc2db5a86d44d2beabe32e265e91ddb0c90787
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="build-and-run-a-c-console-app-project"></a>Erstellen und Ausführen eines C++-Konsolen-app-Projekts

Wenn Sie ein app-Projekt in C++-Konsole erstellt und Code eingegeben haben, können Sie erstellen und führen Sie es in Visual Studio und führen Sie es dann als eigenständige Anwendung über die Befehlszeile.

## <a name="prerequisites"></a>Erforderliche Komponenten

- Haben Sie Visual Studio mit der Desktopentwicklung C++ Arbeitslast installiert und auf Ihrem Computer ausgeführt. Wenn sie noch nicht installiert ist, führen Sie die Schritte in [Installieren von C++-Unterstützung in Visual Studio](../build/vscpp-step-0-installation.md).

- Erstellen Sie eine "Hello, World!" Projekt, und geben Sie den Quellcode. Wenn Sie dies noch nicht gespeichert haben, führen Sie die Schritte in [erstellen ein C++-Konsolen-app-Projekts](../build/vscpp-step-1-create.md).

Wenn Visual Studio wie folgt aussieht, können Sie Ihre app erstellen und ausführen:

   ![Bereit zum Erstellen des neuen Projekts](../build/media/vscpp-ready-to-build.png "bereit, um das neue Projekt zu erstellen.")

## <a name="build-and-run-your-code-in-visual-studio"></a>Erstellen und Ausführen von Code in Visual Studio

1. Wählen Sie zum Erstellen des Projekts **Projektmappe** aus der **erstellen** Menü. Die **Ausgabe** Fenster zeigt die Ergebnisse des Buildprozesses.

   ![Erstellen Sie das Projekt](../build/media/vscpp-build-solution.gif "erstellen Sie das Projekt")

1. Wählen Sie zum Ausführen des Codes in der Menüleiste **Debuggen**, **Starten ohne Debuggen**.

   ![Starten Sie das Projekt](../build/media/vscpp-start-without-debugging.gif "starten Sie das Projekt")

    Ein Konsolenfenster wird geöffnet und führt dann die app. Wenn Sie eine Konsolen-app in Visual Studio starten, er führt den Code, druckt "drücken Sie dann eine beliebige Taste, um den Vorgang fortzusetzen. sein. ." bieten eine Möglichkeit, die Ausgabe wird angezeigt.

Herzlichen Glückwunsch! Sie haben Ihre erste erstellt "Hello, World!" Konsolen-app in Visual Studio! Drücken Sie im Konsolenfenster zu schließen und zurück zu Visual Studio an.

[Ich habe ein Problem aufgetreten.](#build-and-run-your-code-in-visual-studio-issues)

## <a name="run-your-code-in-a-command-window"></a>Führen Sie den Code in einem Befehlsfenster

Normalerweise führen Sie die Konsolen-apps an der Eingabeaufforderung, nicht in Visual Studio. Nachdem Ihre app von Visual Studio erstellt wurde, können Sie ihn aus jeder Befehlsfenster ausführen. Hier wird erklärt, wie Suchen und Ihre neue app in einem Eingabeaufforderungsfenster ausführen.

1. In **Projektmappen-Explorer**, wählen Sie die HelloWorld-Projektmappe, und mit der rechten Maustaste um das Kontextmenü zu öffnen. Wählen Sie **Ordner in Datei-Explorer öffnen** zum Öffnen einer **Datei-Explorer** Fenster im Projektmappenordner HelloWorld.

1. In der **Datei-Explorer** Fenster öffnen Sie Ordner "Debuggen". Ihre app HelloWorld.exe und eine Reihe von anderen Debugdateien enthält. HelloWorld.exe auswählen, die UMSCHALTTASTE gedrückt halten und mit der rechten Maustaste um das Kontextmenü zu öffnen. Wählen Sie **als Pfad kopieren** auf den Pfad zu Ihrer app in die Zwischenablage zu kopieren.

1. Um ein Eingabeaufforderungsfenster zu öffnen, drücken Sie die Windows-R so öffnen die **ausführen** Dialogfeld. Geben Sie *cmd.exe* in der **öffnen** Textfeld, wählen Sie dann **OK** ein Eingabeaufforderungsfenster ausführen.

1. In das Eingabeaufforderungsfenster mit der rechten Maustaste in der Eingabeaufforderung den Pfad zu Ihrer app einfügen. Drücken Sie EINGABETASTE, um Ihre app auszuführen.

   ![Führen Sie die app an der Eingabeaufforderung](../build/media/vscpp-run-in-cmd.gif "führen Sie die app an der Eingabeaufforderung")

Herzlichen Glückwunsch, Sie haben erstellt, und führen Sie eine Konsolen-app in Visual Studio!

[Ich habe ein Problem aufgetreten.](#run-your-code-in-a-command-window-issues)

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie erstellt und führen Sie diese einfachen app haben, können Sie für komplexere Projekte. Finden Sie unter [über die Visual Studio-IDE für C++-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md) Weitere detaillierte Exemplarische Vorgehensweisen, die die Funktionen von Visual C++ in Visual Studio untersuchen.

## <a name="troubleshooting-guide"></a>Handbuch zur Problembehandlung

Komm her für Lösungen für häufige Probleme bei der Erstellung eines ersten C++-Projekts.

### <a name="build-and-run-your-code-in-visual-studio-issues"></a>Erstellen und Ausführen von Code in Visual Studio-Probleme

Wenn die rote Wellenlinien unter alle Elemente in der Quellcode-Editors angezeigt werden, möglicherweise der Build Fehler oder Warnungen. Überprüfen Sie, dass der Code im Beispiel in der Schreibweise, Satzzeichen und Groß-/Kleinschreibung übereinstimmt.

[Zurück.](#build-and-run-your-code-in-visual-studio)

### <a name="run-your-code-in-a-command-window-issues"></a>Führen Sie den Code in einem Befehlsfenster Probleme

Sie können auch in den Projektmappenordner für Debuggen in der Befehlszeile zur Ausführung Ihrer Anwendung navigieren. Ihre app kann nicht aus anderen Verzeichnissen ausgeführt werden, ohne den Pfad zu der app angeben. Allerdings können Sie Ihre app in ein anderes Verzeichnis kopieren und führen Sie es von dort aus.

Wenn Sie nicht sehen **als Pfad kopieren** klicken Sie im Kontextmenü verworfen werden, klicken Sie im Menü, und klicken Sie dann die UMSCHALTTASTE gedrückt halten, während Sie es erneut öffnen. Dies wird nur ergänzend bereitgestellt. Sie können auch kopieren Sie den Pfad zu dem Ordner, aus der Datei-Explorer Suchleiste und fügen Sie ihn in die **ausführen** Dialogfeld, und geben Sie dann den Namen der ausführbaren Datei am Ende. Es ist ein wenig mehr eingeben, aber es bringt das gleiche Ergebnis.

[Zurück.](#run-your-code-in-a-command-window)


<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
