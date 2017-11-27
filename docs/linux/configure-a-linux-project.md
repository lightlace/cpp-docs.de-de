---
title: Konfigurieren eines C++ Linux-Projekts in Visual Studio | Microsoft Docs
ms.custom: 
ms.date: 11/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d7c6adf-54b9-4b23-bd23-5de0c825b768
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e727f4588c425e3a6c94d7ceb09ebc8d494e24cf
ms.sourcegitcommit: 1b480aa74886930b3bd0435d71cfcc3ccda36424
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="configure-a-linux-project"></a>Konfigurieren eines Linux-Projekts
Dieses Thema beschreibt das Konfigurieren eines Visual Studio Linux-Projekts. Informationen zu CMake Linux-Projekten finden Sie unter [Konfigurieren eines Linux CMake-Projekts](cmake-linux-project.md).

## <a name="general-settings"></a>Allgemeine Einstellungen
Für ein Linux-Projekt mit Visual Studio lassen sich eine Vielzahl von Optionen konfigurieren.  Zum Anzeigen dieser Optionen wählen Sie das Menü **Projekt > Eigenschaften** aus oder klicken mit der rechten Maustaste auf das Projekt im **Projektmappen-Explorer** und wählen dann **Eigenschaften** aus dem Kontextmenü aus: Die **allgemeinen** Einstellungen werden angezeigt.

![Allgemeine Konfiguration](media/settings_general.png)

Standardmäßig wird eine ausführbare Datei (.out) mit dem Tool erstellt.  Zum Erstellen einer statischen oder dynamischen Bibliothek oder um eine vorhandene Makefile zu nutzen, verwenden Sie die Auswahl **Konfigurationstyp**.

## <a name="remote-settings"></a>Remoteeinstellungen
Um die Einstellungen für den Linux-Remotecomputer zu ändern, konfigurieren Sie die Remoteoptionen, die in den Einstellungen unter **Allgemein** angezeigt werden:

* Verwenden Sie zum Ändern des Linux-Zielcomputers den Eintrag **Remotebuildcomputer**.  Dadurch können Sie eine der zuvor erstellten Verbindungen auswählen.  Weitere Informationen dazu, wie Sie einen neuen Eintrag erstellen, finden Sie im Abschnitt [Connecting to Your Remote Linux Computer (Verbindung mit Ihren Linux-Remotecomputer](connect-to-your-remote-linux-computer.md).

* Das **Remotebuild-Stammverzeichnis** bestimmt das Stammverzeichnis, in dem das Projekt auf dem Linux-Remotecomputer erstellt wird.  Standardmäßig handelt es sich dabei um **~/projects**, sofern nicht anders angegeben.

* Das **Remotebuild-Projektverzeichnis** ist das Verzeichnis, in dem dieses spezifische Projekt auf dem Linux-Remotecomputer erstellt wird.  Standardmäßig handelt es sich dabei um das Verzeichnis **$(RemoteRootDir)/$(ProjektName)**. Es wird zu einem Verzeichnis erweitert, das den Namen des aktuellen Projekts unter dem oben angegebenen Stammverzeichnis trägt.

> [!NOTE]
> Verwenden Sie zum Ändern der C- und C++-Standardcompiler bzw. der Linker und Archivierungsprogramme, die zur Erstellung des Projekts verwendet werden, die entsprechenden Einträge im Abschnitt **C/C++ > Allgemein** sowie im Abschnitt **Linker > Allgemein**.  Diese können beispielsweise für die Verwendung einer bestimmten GCC-Version oder sogar des Clang-Compilers festgelegt werden.

## <a name="vc-directories"></a>VC++-Verzeichnisse
Standardmäßig enthält Visual Studio keine Includedateien auf Systemebene des Linux-Computers.  So sind in Visual Studio beispielsweise keine Element aus dem Verzeichnis **/Usr/include** vorhanden.  Für vollständige [IntelliSense](/visualstudio/ide/using-intellisense)-Unterstützung müssen Sie diese Dateien an einen Speicherort auf dem Entwicklungscomputer kopieren und Visual Studio auf diesen Speicherort verweisen.  Eine Möglichkeit besteht darin, die Dateien über SCP (Secure Copy) zu kopieren.  Unter Windows 10 können Sie [Bash unter Windows ](https://msdn.microsoft.com/commandline/wsl/about) verwenden, um SCP ausführen.  Unter früheren Versionen von Windows können Sie beispielsweise [PSCP (PuTTY Secure Copy)](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html) nutzen.

Sie können die Dateien mithilfe eines Befehls wie dem folgenden kopieren:

`scp -r linux_username@remote_host:/usr/include .`

Dazu müssen Sie natürlich für **linux_username** und **remote_host** die für Ihre eigene Umgebung passenden Werte eingeben.

Nachdem Sie die Dateien kopiert haben, verwenden Sie in den Projekteigenschaften den Eintrag **VC++-Verzeichnisse**, um Visual Studio mitzuteilen, wo sich die zusätzlichen Includedateien befinden, die Sie gerade kopiert haben.

![VC++-Verzeichnisse](media/settings_directories.png)

## <a name="copy-sources"></a>Kopieren der Quellen
Die Quelldateien werden bei der Erstellung auf Ihrem Entwicklungs-PC auf den Linux-Computer kopiert und dort kompiliert.  Standardmäßig werden alle Datenquellen im Visual Studio-Projekt an die Speicherorte kopiert, die in den oben genannten Einstellungen festgelegt wurden.  Zusätzliche Quellen können ebenfalls zur Liste hinzugefügt werden und das Kopieren von Datenquellen kann vollständig deaktiviert werden, was der Standardeinstellung für Makefile-Projekt entspricht.

* **Zu kopierende Quellen** legt fest, welche Quellen auf den Remotecomputer kopiert werden.  Standardmäßig bezieht **@(RemoteZuKopierendeQuellen)** alle Quellcodedateien im Projekt, jedoch keine Asset-/Ressourcendateien wie beispielsweise Bilder ein.

* **Quellen kopieren** kann aktiviert und deaktiviert werden und kann damit das Kopieren von Quelldateien auf den Remotecomputer aktivieren bzw. deaktivieren.

* Mit **Weitere zu kopierende Quellen** können Sie zusätzliche Quelldateien hinzufügen, die anschließend auf das Remotesystem kopiert werden.  Sie können eine durch Semikolons getrennte Liste angeben, oder Sie können die Syntax **: =** verwenden, um einen lokalen und einen Remote-Namen anzugeben:

  `C:\Projects\ConsoleApplication1\MyFile.cpp:=~/projects/ConsoleApplication1/ADifferentName.cpp;C:\Projects\ConsoleApplication1\MyFile2.cpp:=~/projects/ConsoleApplication1/ADifferentName2.cpp;`

## <a name="build-events"></a>Buildereignisse
Da die gesamte Kompilierung auf einem Remotecomputer erfolgt, wurden dem Abschnitt über Build Events in den Projekteigenschaften mehrere zusätzliche Buildereignisse hinzugefügt.  Dazu gehören das **Remote-Präbuildereignis**, das **Remote-Prälinkereignis** und das **Remote-Postbuildereignis**. Diese Ereignisse finden auf dem Remotecomputer vor oder nach den einzelnen Schritten im Prozess statt.

![Buildereignisse](media/settings_buildevents.png)

## <a name="see-also"></a>Siehe auch
[Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md)  
[Allgemeine C++-Eigenschaften (Linux C++)](../linux/prop-pages/general-linux.md)  
[VC++-Verzeichnisse (Linux C++)](../linux/prop-pages/directories-linux.md)  
[Kopieren von Quellprojekteigenschaften (Linux C++)](../linux/prop-pages/copy-sources-project.md)  
[Buildereigniseigenschaften (Linux C++)](../linux/prop-pages/build-events-linux.md)