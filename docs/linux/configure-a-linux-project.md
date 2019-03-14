---
title: Konfigurieren eines C++ Projekts unter Linux in Visual Studio
ms.date: 11/12/2018
ms.assetid: 4d7c6adf-54b9-4b23-bd23-5de0c825b768
ms.openlocfilehash: 0d0825a3aca8ca03759d7f7b42db90ce9700c10b
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57745182"
---
# <a name="configure-a-linux-project"></a>Konfigurieren eines Linux-Projekts

In diesem Thema wird das Konfigurieren eines C++-Projekts, das auf einer Linux-Projektvorlage basiert, unter Linux in Visual Studio beschrieben. Informationen zu Linux CMake-Projekten finden Sie unter [Konfigurieren eines Linux CMake-Projekts](cmake-linux-project.md).

## <a name="general-settings"></a>Allgemeine Einstellungen

Für ein Linux-Projekt mit Visual Studio lassen sich eine Vielzahl von Optionen konfigurieren.  Zum Anzeigen dieser Optionen wählen Sie das Menü **Projekt > Eigenschaften** aus oder klicken mit der rechten Maustaste auf das Projekt im **Projektmappen-Explorer** und wählen dann **Eigenschaften** aus dem Kontextmenü aus: Die **allgemeinen** Einstellungen werden angezeigt.

![Allgemeine Konfiguration](media/settings_general.png)

Standardmäßig wird eine ausführbare Datei (.out) mit dem Tool erstellt.  Zum Erstellen einer statischen oder dynamischen Bibliothek oder um eine vorhandene Makefile zu nutzen, verwenden Sie die Auswahl **Konfigurationstyp**.

Weitere Informationen zu den Optionen auf den Eigenschaftenseiten finden Sie unter [Referenz zur Linux-Projekteigenschaftenseite](prop-pages-linux.md).

## <a name="remote-settings"></a>Remoteeinstellungen

Um die Einstellungen für den Linux-Remotecomputer zu ändern, konfigurieren Sie die Remoteoptionen, die in den Einstellungen unter [Allgemein](prop-pages/general-linux.md) angezeigt werden:

- Verwenden Sie zum Ändern des Linux-Zielcomputers den Eintrag **Remotebuildcomputer**.  Dadurch können Sie eine der zuvor erstellten Verbindungen auswählen.  Weitere Informationen dazu, wie Sie einen neuen Eintrag erstellen, finden Sie im Abschnitt [Connecting to Your Remote Linux Computer (Verbindung mit Ihren Linux-Remotecomputer](connect-to-your-remote-linux-computer.md).

- Das **Remotebuild-Stammverzeichnis** bestimmt das Stammverzeichnis, in dem das Projekt auf dem Linux-Remotecomputer erstellt wird.  Standardmäßig handelt es sich dabei um **~/projects**, sofern nicht anders angegeben.

- Das **Remotebuild-Projektverzeichnis** ist das Verzeichnis, in dem dieses spezifische Projekt auf dem Linux-Remotecomputer erstellt wird.  Standardmäßig handelt es sich dabei um das Verzeichnis **$(RemoteRootDir)/$(ProjektName)**. Es wird zu einem Verzeichnis erweitert, das den Namen des aktuellen Projekts unter dem oben angegebenen Stammverzeichnis trägt.

> [!NOTE]
> Verwenden Sie zum Ändern der C- und C++-Standardcompiler bzw. der Linker und Archivierungsprogramme, die zur Erstellung des Projekts verwendet werden, die entsprechenden Einträge im Abschnitt **C/C++ > Allgemein** sowie im Abschnitt **Linker > Allgemein**.  Diese können beispielsweise für die Verwendung einer bestimmten GCC-Version oder sogar des Clang-Compilers festgelegt werden. Weitere Informationen finden Sie unter [C/C++-Eigenschaften (Linux C++)](prop-pages/c-cpp-linux.md) und [Linkereigenschaften (Linux C++)](prop-pages/linker-linux.md).

## <a name="include-directories-and-intellisense-support"></a>Einschließen von Verzeichnissen und IntelliSense-Unterstützung

**Visual Studio 2017 Version 15.6 oder früher:**<br/>
Standardmäßig enthält Visual Studio keine Includedateien auf Systemebene des Linux-Computers.  So sind in Visual Studio beispielsweise keine Element aus dem Verzeichnis **/Usr/include** vorhanden.
Für vollständige [IntelliSense](/visualstudio/ide/using-intellisense)-Unterstützung müssen Sie diese Dateien an einen Speicherort auf dem Entwicklungscomputer kopieren und Visual Studio auf diesen Speicherort verweisen.  Eine Möglichkeit besteht darin, die Dateien über SCP (Secure Copy) zu kopieren.  Unter Windows 10 können Sie [Bash unter Windows ](https://msdn.microsoft.com/commandline/wsl/about) verwenden, um SCP ausführen.  Unter früheren Versionen von Windows können Sie beispielsweise [PSCP (PuTTY Secure Copy)](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html) nutzen.

Sie können die Dateien mithilfe eines Befehls wie dem folgenden kopieren:

`scp -r linux_username@remote_host:/usr/include .`

Dazu müssen Sie natürlich für **linux_username** und **remote_host** die für Ihre eigene Umgebung passenden Werte eingeben.

Nachdem Sie die Dateien kopiert haben, verwenden Sie in den Projekteigenschaften den Eintrag **VC++-Verzeichnisse**, um Visual Studio mitzuteilen, wo sich die zusätzlichen Includedateien befinden, die Sie gerade kopiert haben.

![VC++-Verzeichnisse](media/settings_directories.png)

**Visual Studio 2017, Version 15.7 und höher**:<br/>
Weitere Informationen finden Sie unter [Verwalten von Remoteheadern für IntelliSense](#remote_intellisense).

## <a name="copy-sources"></a>Kopieren der Quellen

Die Quelldateien werden bei der Erstellung auf Ihrem Entwicklungs-PC auf den Linux-Computer kopiert und dort kompiliert.  Standardmäßig werden alle Datenquellen im Visual Studio-Projekt an die Speicherorte kopiert, die in den oben genannten Einstellungen festgelegt wurden.  Zusätzliche Quellen können ebenfalls zur Liste hinzugefügt werden und das Kopieren von Datenquellen kann vollständig deaktiviert werden, was der Standardeinstellung für Makefile-Projekt entspricht.

- **Zu kopierende Quellen** legt fest, welche Quellen auf den Remotecomputer kopiert werden.  Standardmäßig bezieht **\@(RemoteZuKopierendeQuellen)** alle Quellcodedateien im Projekt, jedoch keine Asset-/Ressourcendateien wie beispielsweise Bilder ein.

- **Quellen kopieren** kann aktiviert und deaktiviert werden und kann damit das Kopieren von Quelldateien auf den Remotecomputer aktivieren bzw. deaktivieren.

- Mit **Weitere zu kopierende Quellen** können Sie zusätzliche Quelldateien hinzufügen, die anschließend auf das Remotesystem kopiert werden.  Sie können eine durch Semikolons getrennte Liste angeben, oder Sie können die Syntax **: =** verwenden, um einen lokalen und einen Remote-Namen anzugeben:

`C:\Projects\ConsoleApplication1\MyFile.cpp:=~/projects/ConsoleApplication1/ADifferentName.cpp;C:\Projects\ConsoleApplication1\MyFile2.cpp:=~/projects/ConsoleApplication1/ADifferentName2.cpp;`

## <a name="build-events"></a>Buildereignisse

Da die gesamte Kompilierung auf einem Remotecomputer erfolgt, wurden dem Abschnitt über Build Events in den Projekteigenschaften mehrere zusätzliche Buildereignisse hinzugefügt.  Dazu gehören das **Remote-Präbuildereignis**, das **Remote-Prälinkereignis** und das **Remote-Postbuildereignis**. Diese Ereignisse finden auf dem Remotecomputer vor oder nach den einzelnen Schritten im Prozess statt.

![Buildereignisse](media/settings_buildevents.png)

## <a name="remote_intellisense"></a> IntelliSense für Remoteheader (Visual Studio 2017-Version 15.7 und höher)

Beim Hinzufügen einer neuen Verbindung im **Verbindungs-Manager** erkennt Visual Studio automatisch die Includeverzeichnisse für den Compiler auf dem Remotesystem. Visual Studio komprimiert diese Dateien dann und kopiert sie in ein Verzeichnis auf dem lokalen Windows-Computer. Wenn Sie anschließend diese Verbindung in Visual Studio oder CMake nutzen, wird mithilfe der Header in diesen Verzeichnissen IntelliSense bereitgestellt.

Diese Funktion hängt davon ab, ob auf dem Linux-Computer Zip installiert ist. Sie können Zip mit diesem apt-get-Befehl installieren:

```cmd
apt install zip
```

Navigieren Sie zum Verwalten Ihres Header-Caches zu **Extras > Optionen > Plattformübergreifend > Verbindungs-Manager > IntelliSense-Manager für Remoteheader**. Wählen Sie zum Aktualisieren des Header-Caches nach Änderungen auf dem Linux-Computer die Remoteverbindung aus, und klicken Sie dann auf **Aktualisieren**. Klicken Sie auf **Löschen**, um die Header zu entfernen, ohne die Verbindung selbst zu löschen. Klicken Sie auf **Erkunden**, um das lokale Verzeichnis im **Datei-Explorer** zu öffnen. Behandeln Sie diesen Ordner, als sei er schreibgeschützt. Wählen Sie zum Herunterladen von Headern für eine vorhandene Verbindung, die vor Version 15.3 erstellt wurde, die Verbindung aus, und klicken Sie dann auf **Herunterladen**.

![IntelliSense-Remoteheader](media/remote-header-intellisense.png)

## <a name="see-also"></a>Siehe auch

[Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md)<br/>
[Allgemeine C++-Eigenschaften (Linux C++)](prop-pages/general-linux.md)<br/>
[VC++-Verzeichnisse (Linux C++)](prop-pages/directories-linux.md)<br/>
[Kopieren von Quellprojekteigenschaften (Linux C++)](prop-pages/copy-sources-project.md)<br/>
[Buildereigniseigenschaften (Linux C++)](prop-pages/build-events-linux.md)
