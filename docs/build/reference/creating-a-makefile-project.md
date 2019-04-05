---
title: Erstellen eines C++-Makefile-Projekts in Visual Studio
ms.date: 12/08/2018
f1_keywords:
- vc.appwiz.makefile.project
helpviewer_keywords:
- Makefile projects, creating
- project files [C++], Makefile projects
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
ms.openlocfilehash: 9c2edfe35233672e8117d336ba40cfea497b1a22
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59035597"
---
# <a name="create-a-c-makefile-project"></a>Erstellen eines C++-Makefile-Projekts

Ein *Makefile* ist eine Textdatei, die Anweisungen zum Kompilieren und Linken (oder *Erstellen*) einer Reihe von C++-Quellcodedateien enthält. Ein *Make*-Programm liest das Makefile und ruft einen Compiler, einen Linker und möglicherweise auch andere Programme auf, um eine ausführbare Datei zu erstellen. Microsofts Umsetzung dieser die *stellen* Programm heißt [NMAKE](nmake-reference.md);

Wenn Sie über ein vorhandenes Makefile-Projekt verfügen, können Sie folgende Optionen auswählen, wenn Sie es in der Visual Studio-IDE codieren und/oder debuggen möchten:

- Erstellen eines Makefile-Projekts in Visual Studio, die Ihre vorhandenen Makefile verwendet, um eine VCXPROJ-Datei zu konfigurieren, die Visual Studio für IntelliSense verwendet wird. (Sie verfügen nicht über alle IDE-Funktionen, die Sie mit einem nativen MSBuild-Projekt erhalten.) Siehe [So erstellen Sie ein Makefile-Projekt](#create_a_makefile_project) weiter unten.
- Verwenden des Assistenten für das **Erstellen von Projekten aus vorhandenen Codedateien**, um ein natives MSBuild-Projekt aus dem Quellcode zu erstellen. Das ursprüngliche Makefile wird anschließend nicht verwendet werden. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines C++-Projekts aus vorhandenem Code](../how-to-create-a-cpp-project-from-existing-code.md).
- **Visual Studio 2017 und höher:** Verwenden der **"Ordner öffnen"** Funktion bearbeiten und Erstellen eines Makefile-Projekts als – ohne jegliche Beteiligung des MSBuild-Systems ist. Weitere Informationen finden Sie unter [Open Folder projects for C++ (Verwenden von „Ordner öffnen“ mit Projekten in Visual C++)](../open-folder-projects-cpp.md).

## <a name="a-namecreateamakefileproject-to-create-a-makefile-project-with-the-makefile-project-template"></a><a name="create_a_makefile_project"> Zum Erstellen eines Makefile-Projekts mit der Makefile-Projektvorlage

In Visual Studio 2017 oder höher ist die Makefile-Projektvorlage verfügbar, wenn die Workload C++-Desktopentwicklung installiert ist.

Folgen Sie dem Assistenten, der Sie beim Festlegen der Befehle und der Umgebung unterstützt, die das Makefile verwendet. Sie können dieses Projekt klicken Sie dann verwenden, um Ihren Code in Visual Studio zu erstellen.

Das Makefile-Projekt zeigt im Projektmappen-Explorer standardmäßig keine Dateien an. Die Buildeinstellungen, die auf der Eigenschaftenseite des Projekts angezeigt werden, werden vom Makefile-Projekt festgelegt.

Die Ausgabedatei, die Sie im Projekt festlegen, hat keinen Einfluss auf den vom Buildskript erstellten Namen; sie deklariert lediglich die Bestimmung. Ihr Makefile steuert weiterhin den Buildprozess und gibt die Buildziele an.

1. Geben Sie auf der Visual Studio-Startseite „makefile“ in das Suchfeld **Neues Projekt** ein. Sie können auch **Visual C++** > **Allgemein** (Visual Studio 2015) oder **Andere** (Visual Studio 2017) im Dialogfeld **Neues Projekt** erweitern und dann im Vorlagenbereich auf **Makefile-Projekt** klicken, um den Projekt-Assistenten zu öffnen.

1. Geben Sie auf der Seite **Anwendungseinstellungen** die Befehls-, Ausgabe-, Bereinigungs- und Neuerstellungsinformationen für die Debug- und Verkaufsversion an.

1. Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen und das neu erstellte Projekt im **Projektmappen-Explorer** zu öffnen.

Sie können die Projekteigenschaften auf der Eigenschaftenseite des Projekts anzeigen und bearbeiten. Finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md) Informationen zum Anzeigen der Eigenschaftenseite.

## <a name="makefile-project-wizard"></a>Makefile-Projekt-Assistenten

Nachdem Sie ein Makefile-Projekt erstellt haben, können Sie anzeigen und bearbeiten Sie die folgenden Optionen in der **Nmake** Seite der Eigenschaftenseite des Projekts.

- **Erstellen Sie über die Befehlszeile ein:** Gibt die Befehlszeile ausgeführt wird, wenn der Benutzer einen Build aus dem Menü "Build" auswählt. Klicken Sie in das Feld "Build" Befehlszeile "auf der Nmake-Seite der Eigenschaftenseite des Projekts angezeigt.

- **Ausgabe:** Gibt den Namen der Datei an, in der die Ausgabe für die Befehlszeile enthalten ist. Diese Option basiert standardmäßig auf dem Projektnamen. Die Ausgabe-Feld auf der Nmake-Seite der Eigenschaftenseite des Projekts angezeigt.

- **Clean-Befehle:** Gibt die Befehlszeile ausgeführt werden, wenn der Benutzer im Menü erstellen Bereinigen ausgewählt. In der Befehlszeile bereinigen-Feld auf der Nmake-Seite der Eigenschaftenseite des Projekts angezeigt.

- **Erstellen Sie über die Befehlszeile ein:** Gibt die Befehlszeile ausgeführt wird, wenn der Benutzer die Neuerstellung im buildmenü auswählt. Angezeigt in der Neuerstellung alle über die Befehlszeile-Feld auf der Nmake-Seite der Eigenschaftenseite des Projekts.

## <a name="how-to-enable-intellisense-for-makefile-projects"></a>Vorgehensweise: Aktivieren von IntelliSense für Makefile-Projekte

IntelliSense schlägt in Makefile-Projekte fehl, wenn bestimmte projekteinstellungen oder Compileroptionen nicht ordnungsgemäß eingerichtet sind. Um die Makefile-Projekte so konfigurieren, dass IntelliSense wie erwartet funktioniert, gehen Sie wie folgt vor:

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten**. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Erweitern Sie den Knoten **Konfigurationseigenschaften**.

1. Wählen Sie die Eigenschaftenseite **NMake** aus, und ändern Sie dann die Eigenschaften unter **IntelliSense** nach Bedarf.

   - Legen Sie die Eigenschaft **Präprozessordefinitionen** so fest, dass alle Präprozessorsymbole in Ihrem Makefile-Projekt definiert werden. Weitere Informationen finden Sie unter [/D (Preprocessor Definitions) (/D (Präprozessordefinitionen))](d-preprocessor-definitions.md).

   - Legen Sie die Eigenschaft **Includesuchpfad** so fest, dass die Liste von Verzeichnissen angegeben wird, in denen der Compiler sucht, um Dateiverweise aufzulösen, die an Präprozessordirektiven in Ihrem Makefile-Projekt übergeben werden. Weitere Informationen finden Sie unter [/I (Additional Include Directories) (/I (Zusätzliche Includeverzeichnisse))](i-additional-include-directories.md).

    - Legen Sie die Umgebungsvariable **INCLUDE** für Projekte fest, die mithilfe der „cl.exe“ über ein Befehlsfenster erstellt werden, um Verzeichnisse anzugeben, in denen der Compiler sucht, um Dateiverweise aufzulösen, die an Präprozessordirektiven in Ihrem Makefile-Projekt übergeben werden.

   - Legen Sie die Eigenschaft **Erzwungene Includedateien** fest, um anzugeben, welche Headerdateien bei der Erstellung des Makefile-Projekts verarbeitet werden sollen. Weitere Informationen finden Sie unter [/FI (Name Forced Include File) (/FI (Name der expliziten Includedatei))](fi-name-forced-include-file.md).

   - Legen Sie die Eigenschaft **Assemblysuchpfad** fest, um die Liste von Verzeichnissen anzugeben, in denen der Compiler sucht, um Verweise auf .NET-Assemblys in Ihrem Projekt aufzulösen. Weitere Informationen finden Sie unter [/AI (Specify Metadata Directories) (/AI (Metadatenverzeichnisse festlegen))](ai-specify-metadata-directories.md).

   - Legen Sie die Eigenschaft **Erzwungene Verwendung von Assemblys** fest, um anzugeben, welche .NET-Assemblys bei der Erstellung des Makefile-Projekts verarbeitet werden sollen. Weitere Informationen finden Sie unter [/FU (Name Forced #using File) (/FU (Name der erzwungenen #using-Datei))](fu-name-forced-hash-using-file.md).

   - Legen Sie die Eigenschaft **Zusätzliche Optionen** fest, um zusätzliche Compileroptionen anzugeben, die von IntelliSense beim Analysieren von C++-Dateien verwendet werden.

1. Klicken Sie auf **OK**, um die Eigenschaftenseiten zu schließen.

1. Verwenden Sie den Befehl **Alle speichern**, um die geänderten Projekteinstellungen zu speichern.

Führen Sie das nächste Mal, wenn Sie Ihr Makefile-Projekt in der Visual Studio-Entwicklungsumgebung öffnen, den Befehl **Projektmappe bereinigen** und anschließend **Projektmappe erstellen** im Makefile-Projekt aus. IntelliSense sollte nun ordnungsgemäß in der IDE funktionieren.

## <a name="see-also"></a>Siehe auch

[Using IntelliSense](/visualstudio/ide/using-intellisense)<br>
[NMAKE-Referenz](nmake-reference.md)<br>
[Vorgehensweise: Erstellen Sie ein C++-Projekt aus vorhandenem Code](../how-to-create-a-cpp-project-from-existing-code.md)
[Sonderzeichen in einem Makefile](special-characters-in-a-makefile.md)<br/>
[Inhalt eines Makefiles](contents-of-a-makefile.md)<br/>
