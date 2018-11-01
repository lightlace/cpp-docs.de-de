---
title: Erstellen Sie eine C++-Konsolen-app-Projekts | Microsoft-Dokumentation
description: Erstellen Sie eine Hello World-Konsolenanwendung in Visual C++
ms.custom: mvc
ms.date: 12/12/2017
ms.topic: tutorial
ms.technology:
- cpp-tools
ms.devlang: C++
dev_langs:
- C++
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1dbd3c15aaf8d4702905ba1b8301b36cb9c1a2e0
ms.sourcegitcommit: 92c568e9466ffd7346a4120c478c9bdea61c8756
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2018
ms.locfileid: "47029553"
---
# <a name="create-a-c-console-app-project"></a>Erstellen Sie eine C++-Konsolen-app-Projekts

Der üblichen Ausgangspunkt für ein C++-Programmierer ist eine "Hello, World!" die Anwendung, die in der Befehlszeile ausgeführt wird. Das ist, was Sie in Visual Studio in diesem Schritt erstellen.

## <a name="prerequisites"></a>Erforderliche Komponenten

- Haben Sie Visual Studio mit der Desktopentwicklung mit C++-Arbeitslast installiert und auf Ihrem Computer ausgeführt. Wenn sie noch nicht installiert ist, finden Sie unter [Installieren von C++-Unterstützung in Visual Studio 2017](../build/vscpp-step-0-installation.md).

## <a name="create-your-app-project"></a>Erstellen Sie Ihr app-Projekt

Visual Studio verwendet *Projekte*, um Code für eine App zu ordnen, und *Projektmappen*, um Ihre Projekte zu ordnen. Ein Projekt enthält alle Optionen, Konfigurationen, und Regeln verwendet, um Ihre apps zu erstellen, und verwaltet die Beziehung zwischen allen Projektdateien und externen Dateien. Zum Erstellen Ihrer app zuerst erstellen Sie ein neues Projekt und Projektmappe.

1. Öffnen Sie in Visual Studio die **Datei** Menü, und wählen Sie **neu > Projekt** zum Öffnen der **neues Projekt** Dialogfeld.

   ![Öffnen Sie das Dialogfeld "Neues Projekt"](../build/media/vscpp-file-new-project.gif "öffnen Sie das Dialogfeld \"Neues Projekt\"")

1. In der **neues Projekt** wählen Sie im Dialogfeld **installiert**, **Visual C++** , wenn es nicht bereits aktiviert ist, und wählen Sie dann die **leeres Projekt** Vorlage. In der **Namen** Feld *HelloWorld*. Wählen Sie **OK** zum Erstellen des Projekts.

   ![Benennen und erstellen Sie das neue Projekt](../build/media/vscpp-concierge-project-name-callouts.png "Namen und das neue Projekt zu erstellen")

Visual Studio erstellt ein neues, leeres Projekt, für die Sie für die Art von app spezialisiert werden kann, die Sie erstellen und Ihre Quellcodedateien hinzufügen möchten. Sie werden als Nächstes tun.

[Ich führte ein Problem aufgetreten.](#create-your-app-project-issues)

## <a name="make-your-project-a-console-app"></a>Stellen Sie Ihr Projekt eine Konsolen-app

Visual Studio kann alle Arten von apps und Komponenten für Windows und andere Plattformen erstellen. Die **leeres Projekt** Vorlage keine speziellen, über welche Art von app erstellt. Zum Erstellen einer *Konsolen-app*möglich, die ausgeführt wird, in eine Konsole oder ein Eingabeaufforderungsfenster, müssen Sie Visual Studio zum Erstellen der app, um die Konsole-Subsystem verwenden mitteilen.

1. Öffnen Sie in Visual Studio die **Projekt** im Menü, und wählen Sie **Eigenschaften** zum Öffnen der **HelloWorld-Eigenschaftenseiten** Dialogfeld.

1. In der **Eigenschaftenseiten** Dialogfeld unter **Konfigurationseigenschaften**Option **Linker**, **System**, und wählen Sie dann das Eingabefeld neben die **Subsystem** Eigenschaft. Wählen Sie in der Dropdown-Menü, das angezeigt wird, **Konsole (/ SUBSYSTEM: CONSOLE)**. Wählen Sie **OK** zum Speichern der Änderungen.

   ![Öffnen Sie das Dialogfeld "Eigenschaftenseiten"](../build/media/vscpp-properties-linker-subsystem.gif "öffnen Sie das Dialogfeld \"Eigenschaftenseiten\"")

Visual Studio weiß jetzt zum Erstellen Ihres Projekts in einem Konsolenfenster ausführen. Als Nächstes, Sie fügen eine Quellcodedatei hinzu und geben Sie den Code für Ihre app.

[Ich führte ein Problem aufgetreten.](#make-your-project-a-console-app-issues)

## <a name="add-a-source-code-file"></a>Fügen Sie eine Quellcodedatei hinzu.

1. In **Projektmappen-Explorer**, wählen Sie das HelloWorld-Projekt. Wählen Sie auf der Menüleiste **Projekt**, **neues Element hinzufügen** zum Öffnen der **neues Element hinzufügen** Dialogfeld.

1. In der **neues Element hinzufügen** wählen Sie im Dialogfeld **Visual C++** unter **installiert** , wenn sie nicht bereits ausgewählt ist. Wählen Sie im mittleren Bereich **C++-Datei (.cpp)**. Ändern der **Namen** zu *HelloWorld.cpp*. Wählen Sie **hinzufügen** um das Dialogfeld zu schließen, und erstellen Sie die Datei.

   ![Fügen Sie eine Quelldatei für HelloWorld.cpp](../build/media/vscpp-add-new-item.gif "fügen Sie eine Quelldatei für HelloWorld.cpp")

Visual Studio erstellt eine neue, leere Quellcodedatei und in einem Editor-Fenster, bereit für die Eingabe von Quellcode geöffnet.

[Ich führte ein Problem aufgetreten.](#add-a-source-code-file-issues)

## <a name="add-code-to-the-source-file"></a>Fügen Sie Code zur Quelldatei hinzu.

1. Kopieren Sie diesen Code in das Editorfenster HelloWorld.cpp.

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

Wenn der Code im Editor wie folgt aussieht, können Sie zu fahren mit dem nächsten Schritt erstellen Sie Ihre app.

[Ich führte ein Problem aufgetreten.](#add-a-source-code-file-issues)

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Erstellen und Ausführen eines C++-Projekts](vscpp-step-2-build.md)

## <a name="troubleshooting-guide"></a>Handbuch zur Problembehandlung

Sind Sie hier für Lösungen für häufige Probleme, wenn Sie Ihr erstes C++-Projekt erstellen.

### <a name="create-your-app-project-issues"></a>Erstellen Sie Ihre app Projektprobleme

Wenn die **neues Projekt** Dialogfeld nicht angezeigt. ein **Visual C++** Eintrag unter **installiert**, Ihre Kopie von Visual Studio nicht möglicherweise die **Desktop Entwicklung mit C++** arbeitsauslastung installiert. Sie können das Installationsprogramm direkt Ausführen der **neues Projekt** Dialogfeld. Wählen Sie die **Visual Studio-Installer öffnen** Link zu den Installer erneut starten. Wenn die **User Account Control** Dialogfeld fordert Berechtigungen an, wählen Sie **Ja**. Im Installationsprogramm stellen Sie sicher, dass die **Desktopentwicklung mit C++** arbeitsauslastung aktiviert ist, und wählen Sie **OK** Visual Studio-Installation zu aktualisieren.

Wenn ein anderes Projekt mit dem gleichen Namen bereits vorhanden ist, wählen Sie einen anderen Namen für Ihr Projekt, oder löschen Sie das vorhandene Projekt, und versuchen Sie es erneut. Um ein vorhandenes Projekt zu löschen, löschen Sie den Projektmappenordner (der Ordner, der die Datei "HelloWorld.sln" enthält) im Datei-Explorer aus.

[Wechseln Sie zurück](#create-your-app-project).

### <a name="make-your-project-a-console-app-issues"></a>Stellen Sie Ihr Projekt ein app-Problemen Konsole

Wenn Sie nicht sehen **Linker** aufgeführt **Konfigurationseigenschaften**, wählen Sie **Abbrechen** zu schließen die **Eigenschaftenseiten** Dialogfeld und klicken Sie dann Stellen Sie sicher, dass die **HelloWorld** Projekt ausgewählt ist **Projektmappen-Explorer**, nicht die Lösung oder eine andere Datei oder den Ordner, bevor Sie es erneut versuchen.

Das Dropdown-Steuerelement erscheint nicht in der **SubSystem** Eigenschaft im Bearbeitungsfeld, bis Sie die Eigenschaft auswählen. Sie können es auswählen, indem Sie mit dem Zeiger, oder drücken Sie Tab, um die Dialogfeldsteuerelemente bis durchlaufen **SubSystem** wird hervorgehoben. Wählen Sie im Dropdown-Steuerelement, oder drücken Sie Alt + nach-unten, um ihn zu öffnen.

[Zurück](#make-your-project-a-console-app)

### <a name="add-a-source-code-file-issues"></a>Hinzufügen einer Quelle Codeprobleme-Datei

Es ist kein Problem, wenn Sie der Quellcodedatei einen anderen Namen geben. Allerdings fügen Sie nicht auf mehr als eine Quellcodedatei mit dem gleichen Code zum Projekt hinzu.

Wenn Sie die falsche Art von Datei Ihrem Projekt hinzugefügt haben, z. B. eine Headerdatei, löschen Sie ihn, und versuchen Sie es erneut. Um die Datei zu löschen, wählen Sie diese in **Projektmappen-Explorer** , und drücken Sie die ENTF-Taste.

[Wechseln Sie zurück](#add-a-source-code-file).

### <a name="add-code-to-the-source-file-issues"></a>Fügen Sie Code hinzu, um die Probleme mit der Quelle

Wenn Sie versehentlich geschlossen haben die Datei-Editor Quellcodefenster, um es anschließend erneut öffnen, doppelklicken Sie auf auf HelloWorld.cpp in die **Projektmappen-Explorer** Fenster.

Rote Wellenlinien unter alle Elemente in der Quellcode-Editor angezeigt werden, sicher, dass Ihr Code im Beispiel in der Schreibweise, Satzzeichen und Groß-/Kleinschreibung übereinstimmt. Fall spielt in C++-Code.

[Wechseln Sie zurück](#add-code-to-the-source-file).

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />