---
title: Erstellen ein C++-Konsolen-app-Projekts | Microsoft Docs
description: Erstellen einer Hello World-Konsolen-app in Visual C++
ms.custom: mvc
ms.date: 12/12/2017
ms.topic: tutorial
ms.technology:
- devlang-C++
ms.devlang: C++
dev_langs:
- C++
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 35b7b896dfb2a4c9dd37a9f59476cbc7f23c3902
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391232"
---
# <a name="create-a-c-console-app-project"></a>Erstellen eines C++-Konsolen-app-Projekts

Die üblichen Ausgangspunkt für C++-Programmierer ist eine "Hello, World!" Anwendung, die in der Befehlszeile ausgeführt wird. Das ist, was in Visual Studio in diesem Schritt erstellen Sie.

## <a name="prerequisites"></a>Erforderliche Komponenten

- Haben Sie Visual Studio mit der Desktopentwicklung C++ Arbeitslast installiert und auf Ihrem Computer ausgeführt. Wenn sie noch nicht installiert ist, finden Sie unter [Installieren von C++-Unterstützung in Visual Studio](../build/vscpp-step-0-installation.md).

## <a name="create-your-app-project"></a>Erstellen von app-Projekts

Visual Studio verwendet *Projekte*, um Code für eine App zu ordnen, und *Projektmappen*, um Ihre Projekte zu ordnen. Ein Projekt enthält die Optionen, Konfigurationen und Regeln, die zum Erstellen Ihrer apps und die Beziehung zwischen den Dateien des Projekts und externe Dateien verwaltet. Um Ihre app zu erstellen, zunächst erstellen ein neues Projekt und Projektmappe Sie.

1. Öffnen Sie in Visual Studio die **Datei** Menü, und wählen Sie **neu > Projekt** So öffnen die **neues Projekt** Dialogfeld.

   ![Öffnen Sie das Dialogfeld "Neues Projekt"](../build/media/vscpp-file-new-project.gif "öffnen Sie das Dialogfeld \"Neues Projekt\"")

1. In der **neues Projekt** wählen Sie im Dialogfeld **installiert**, **Visual C++** , wenn er nicht bereits ausgewählt ist, und wählen Sie dann die **leeres Projekt** Vorlage. In der **Namen** Feld *HelloWorld*. Wählen Sie **OK** zum Erstellen des Projekts.

   ![Das neue Projekt zu erstellen und benennen Sie](../build/media/vscpp-concierge-project-name-callouts.png "Namen und das neue Projekt zu erstellen")

Visual Studio erstellt ein neues, leeres Projekt, für die Sie für die Art der app spezialisiert werden kann, die Sie erstellen und die Quellcodedateien hinzufügen möchten. Als Nächstes müssen Sie die folgenden Aufgaben ausführen.

[Ich habe ein Problem aufgetreten.](#create-your-app-project-issues)

## <a name="make-your-project-a-console-app"></a>Stellen Sie dem Projekt eine Konsolen-app

Visual Studio kann alle Arten von apps und Komponenten für Windows und andere Plattformen erstellen. Die **leeres Projekt** Vorlage nicht bestimmte über welche Art von app erstellt wird. Zum Erstellen einer *Konsolen-app*jeweils in einer Konsolen- oder Eingabeaufforderungsfenster ausgeführt wird, müssen Sie feststellen, Visual Studio beim Erstellen Ihrer app, um die Konsole-Subsystem verwenden.

1. Öffnen Sie in Visual Studio die **Projekt** Menü, und wählen Sie **Eigenschaften** So öffnen die **HelloWorld-Eigenschaftenseiten** Dialogfeld.

1. In der **Eigenschaftenseiten** Dialogfeld unter **Konfigurationseigenschaften**Option **Linker**, **System**, und wählen Sie im Bearbeitungsfeld neben die **Subsystem** Eigenschaft. Wählen Sie im Dropdownmenü **Konsole (/ SUBSYSTEM: CONSOLE)**. Wählen Sie **OK** zum Speichern der Änderungen.

   ![Öffnen Sie das Dialogfeld "Eigenschaftenseiten"](../build/media/vscpp-properties-linker-subsystem.gif "öffnen Sie das Dialogfeld \"Eigenschaftenseiten\"")

Visual Studio weiß jetzt zum Erstellen des Projekts in einem Konsolenfenster ausgeführt. Als Nächstes, Sie fügen eine Quellcodedatei hinzu und geben Sie den Code für Ihre app.

[Ich habe ein Problem aufgetreten.](#make-your-project-a-console-app-issues)

## <a name="add-a-source-code-file"></a>Fügen Sie eine Quellcodedatei hinzu

1. In **Projektmappen-Explorer**, wählen Sie das HelloWorld-Projekt. Wählen Sie in der Menüleiste **Projekt**, **neues Element hinzufügen** So öffnen die **neues Element hinzufügen** Dialogfeld.

1. In der **neues Element hinzufügen** wählen Sie im Dialogfeld **Visual C++** unter **installiert** , wenn er nicht bereits ausgewählt ist. Wählen Sie im mittleren Bereich **C++-Datei (.cpp)**. Ändern der **Namen** auf *HelloWorld.cpp*. Wählen Sie **hinzufügen** das Dialogfeld zu schließen und die Datei erstellt.

   ![Fügen Sie eine Quelldatei für HelloWorld.cpp](../build/media/vscpp-add-new-item.gif "fügen eine Quelldatei für HelloWorld.cpp hinzu.")

Visual Studio erstellt eine neues, leeres Quellcodedatei und öffnet es in einem Editor-Fenster, geben Sie den Quellcode bereit.

[Ich habe ein Problem aufgetreten.](#add-a-source-code-file-issues)

## <a name="add-code-to-the-source-file"></a>Fügen Sie Code zur Quelldatei

1. Kopieren Sie diesen Code im Editorfenster HelloWorld.cpp.

   ```cpp
   #include <iostream>

   int main()
   {
       std::cout << "Hello, world!" << std::endl;
       return 0;
   }
   ```

   Der Code sollte im Editor-Fenster wie folgt aussehen:

   ![Hello World-Code in Editor](../build/media/vscpp-hello-world-editor.png "Hello World-Code-Editor")

Wenn der Code im Editor wie folgt aussieht, können Sie bereit sind, fahren mit dem nächsten Schritt fort, und erstellen Sie Ihre app.

[Ich habe ein Problem aufgetreten.](#add-a-source-code-file-issues)

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Erstellen und Ausführen eines C++-Projekts](vscpp-step-2-build.md)

## <a name="troubleshooting-guide"></a>Handbuch zur Problembehandlung

Komm her für Lösungen für häufige Probleme bei der Erstellung eines ersten C++-Projekts.

### <a name="create-your-app-project-issues"></a>Erstellen Sie Ihrer app Projektprobleme

Wenn die **neues Projekt** Dialogfeld nicht angezeigt. ein **Visual C++** Eintrag unter **installiert**, Ihre Kopie von Visual Studio wahrscheinlich verfügt nicht über die **Desktop Entwicklung mit C++** arbeitsauslastung installiert. Sie können das Installationsprogramm direkt Ausführen der **neues Projekt** Dialogfeld. Wählen Sie die **Installer für Visual Studio öffnen** Link, um das Installationsprogramm erneut zu starten. Wenn die **User Account Control** Dialogfeld Berechtigungen anfordert, wählen Sie **Ja**. Installationsprogramm, vergewissern Sie sich die **Desktopentwicklung mit C++** arbeitsauslastung aktiviert ist, und wählen Sie **OK** Visual Studio-Installation zu aktualisieren.

Wenn ein anderes Projekt mit dem gleichen Namen bereits vorhanden ist, wählen Sie einen anderen Namen für das Projekt, oder löschen Sie das vorhandene Projekt, und versuchen Sie es erneut. Um ein vorhandenes Projekt zu löschen, löschen Sie Projektmappenordner (im Ordner mit der helloworld.sln Datei) im Datei-Explorer aus.

[Wechseln Sie zurück](#create-your-app-project).

### <a name="make-your-project-a-console-app-issues"></a>Stellen Sie dem Projekt eine Problemen mit app-Konsole

Wenn Sie nicht sehen **Linker** aufgeführt **Konfigurationseigenschaften**, wählen Sie **"Abbrechen"** zu schließen die **Eigenschaftenseiten** Dialogfeld und klicken Sie dann Stellen Sie sicher, dass die **HelloWorld** Projekt ausgewählt ist, im **Projektmappen-Explorer**, nicht die Projektmappe oder eine andere Datei oder Ordner, bevor Sie den Vorgang wiederholen.

Das Dropdown-Steuerelement erscheint nicht in der **SubSystem** Eigenschaft Eingabefeld, bis Sie die Eigenschaft auswählen. Sie können mithilfe des Zeigers auswählen, oder drücken Sie Tab, um das Dialogfeld-Steuerelemente, bis der Reihe nach **SubSystem** wird hervorgehoben. Wählen Sie im Dropdown-Steuerelement, oder drücken Sie Alt + nach-unten, um ihn zu öffnen.

[Zurück](#make-your-project-a-console-app)

### <a name="add-a-source-code-file-issues"></a>Hinzufügen einer Quelle Datei Codeprobleme

Es ist angemessen, wenn Sie die Quellcodedatei an einen anderen Namen geben. Allerdings fügen Sie nicht mehr als eine Quellcodedatei mit dem gleichen Code zum Projekt hinzu.

Wenn Sie den falschen Datei dem Projekt hinzugefügt haben, z. B. eine Headerdatei löschen Sie ihn, und versuchen Sie es erneut. Um die Datei zu löschen, wählen Sie ihn in **Projektmappen-Explorer** , und drücken Sie die ENTF-Taste.

[Wechseln Sie zurück](#add-a-source-code-file).

### <a name="add-code-to-the-source-file-issues"></a>Fügen Sie Code hinzu, um die Probleme mit der Quelle

Wenn Sie versehentlich geschlossen haben Quellcodefenster für den Editor, um es anschließend erneut öffnen, doppelklicken Sie auf auf HelloWorld.cpp in der **Projektmappen-Explorer** Fenster.

Rote Wellenlinien unter alle Elemente in der Quellcode-Editors angezeigt werden, sicher, dass es sich bei der Code im Beispiel in der Schreibweise, Satzzeichen und Groß-/Kleinschreibung übereinstimmt. Fall spielt in C++-Code.

[Wechseln Sie zurück](#add-code-to-the-source-file).

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />