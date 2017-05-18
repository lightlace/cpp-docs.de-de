---
title: Konfigurieren eines Linux-Projekts | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d7c6adf-54b9-4b23-bd23-5de0c825b768
author: BrianPeek
ms.author: brpeek
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 1683c03c522b0b332ced9e93188c65e996ac633d
ms.openlocfilehash: ec7ec2a7f5f0393f00efb6d662494e7be2a3f696
ms.contentlocale: de-de
ms.lasthandoff: 03/22/2017

---

# <a name="configure-a-linux-project"></a>Konfigurieren eines Linux-Projekts

## <a name="general-settings"></a>Allgemeine Einstellungen
Für ein Linux-Projekt mit Visual Studio lassen sich eine Vielzahl von Optionen konfigurieren.  Zum Anzeigen dieser Optionen wählen Sie das Menü **Projekt > Eigenschaften** aus oder klicken mit der rechten Maustaste auf das Projekt im **Projektmappen-Explorer** und wählen **Eigenschaften** aus dem Kontextmenü:

![Allgemeine Konfiguration](media/settings_general.png)

Standardmäßig wird eine ausführbare Datei (.out) mit dem Tool erstellt.  Zum Erstellen einer statischen oder dynamischen Bibliothek oder um eine vorhandene Makefile zu nutzen, verwenden Sie die Auswahl **Konfigurationstyp**.

## <a name="remote-settings"></a>Remoteeinstellungen
Wählen Sie zum Ändern der Einstellungen für den Linux-Remotecomputer das Element **Remoteeinstellungen** aus:

![Remoteeinstellungen](media/settings_remote.png)

* Verwenden Sie zum Ändern des Ziel-Linux-Computer den Eintrag **Zielcomputer**.  Dadurch können Sie eine der zuvor erstellten Verbindungen auswählen.  Weitere Informationen dazu, wie Sie einen neuen Eintrag erstellen, finden Sie im Abschnitt [Connecting to Your Remote Linux Computer (Verbindung mit Ihren Linux-Remotecomputer](connect-to-your-remote-linux-computer.md).

* Das **Remotestammverzeichnis** bestimmt das Stammverzeichnis, in dem das Projekt auf dem Linux-Remotecomputer erstellt wird.  Standardmäßig handelt es sich dabei um **~/projects**, sofern nicht anders angegeben.

* Das **Remoteprojektverzeichnis** befindet sich dort, wo das angegebene Projekt auf dem Linux-Remotecomputer erstellt wird.  Standardmäßig handelt es sich dabei um das Verzeichnis **$(RemoteRootDir)/$(ProjektName)**. Es wird zu einem Verzeichnis erweitert, das den Namen des aktuellen Projekts unter dem oben angegebenen Stammverzeichnis trägt.

* Nutzen Sie abschließend zum Ändern der standardmäßigen C- und C++-Compiler bzw. der Linker und Archivierungsprogramme, die zur Erstellung des Projekts verwendet wurden, die entsprechenden Einträge im Abschnitt **Toolsstandardwerte**.  Diese können beispielsweise für die Verwendung einer bestimmten GCC-Version oder sogar des Clang-Compilers festgelegt werden.

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
Da die gesamte Kompilierung auf einem Remotecomputer erfolgt, wurden dem Abschnitt über Build Events in den Projekteigenschaften mehrere zusätzliche Buildereignisse hinzugefügt.  Dazu gehören **Remote-Präbuildereignis**, **Remote-Prälinkereignis** und **Remove Post-Build Event** (Postbuildereignis entfernen). Sie finden auf dem Remotecomputer vor oder nach den einzelnen Schritte im Prozess statt.

![Buildereignisse](media/settings_buildevents.png)

## <a name="see-also"></a>Siehe auch
[Working with Project Properties (Arbeiten mit Projekteigenschaften)](../ide/working-with-project-properties.md)
