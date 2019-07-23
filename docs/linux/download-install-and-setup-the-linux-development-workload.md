---
title: Installieren der C++-Workload unter Linux in Visual Studio
description: Informationen zum Herunterladen, Installieren und Einrichten der Linux-Workload für C++ in Visual Studio
ms.date: 06/11/2019
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
ms.openlocfilehash: 5df7b323d202f398059e92abaeeeedbf73439fa4
ms.sourcegitcommit: 7f5b29e24e1be9b5985044a030977485fea0b50c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2019
ms.locfileid: "68299792"
---
# <a name="download-install-and-set-up-the-linux-workload"></a>Herunterladen, Installieren und Einrichten der Linux-Workload

::: moniker range="vs-2015"

Linux-Projekte werden von Visual Studio 2017 und höher unterstützt.

::: moniker-end

::: moniker range=">=vs-2017"

Sie können die Visual Studio-IDE unter Windows verwenden, um C++-Projekte zu erstellen, zu bearbeiten und zu debuggen, die auf einem physischen Linux-Computer, einem virtuellen Computer oder dem [Windows-Subsystem für Linux](/windows/wsl/about) ausgeführt werden. 

Sie können an Ihrer bestehenden Codebasis arbeiten, die CMake oder ein anderes Buildsystem verwendet, ohne sie in ein Visual Studio-Projekt konvertieren zu müssen. Wenn Ihre Codebasis plattformübergreifend ist, können Sie sowohl Windows als auch Linux in Visual Studio als Ziel verwenden. Sie können zum Beispiel Ihren Code unter Windows mit Visual Studio bearbeiten, debuggen und ein Profil dafür erstellen und dann das Projekt schnell für weitere Tests neu auf Linux ausrichten. Die Linux-Headerdateien werden automatisch auf Ihren lokalen Computer kopiert. Dort werden sie von Visual Studio verwendet, um vollständige IntelliSense-Unterstützung bereitzustellen (Anweisungsvervollständigung, Gehe zu Definition usw.). 
 
Für jedes dieser Szenarios ist die Workload **Linux-Entwicklung mit C++** erforderlich. 

::: moniker-end

::: moniker range="vs-2019"

In Visual Studio 2019 können Sie separate Linux-Ziele zum Erstellen und Debuggen angeben. Wenn Sie das WSL als Ziel verwenden, ist es nicht mehr erforderlich, eine Remoteverbindung hinzufügen oder SSH zu konfigurieren.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="visual-studio-setup"></a>Setup von Visual Studio

1. Geben Sie „Visual Studio Installer“ in das Windows-Suchfeld ein:

   ![Windows-Suchfeld](media/visual-studio-installer-search.png)

2. Suchen Sie in den Ergebnissen unter **Apps** nach dem Installer, und doppelklicken Sie auf ihn. Wenn der Installer geöffnet wird, wählen Sie **Ändern**aus, und klicken Sie dann auf die Registerkarte **Workloads**. Scrollen Sie nach unten zu **Andere Toolsets**, und wählen Sie die Workload **Linux Entwicklung mit C++** aus.

   ![Workload „Visual C++ für Linux-Entwicklung“](media/linuxworkload.png)

1. Wenn Sie IoT- oder eingebettete Zielplattformen nutzen möchten, navigieren Sie auf der rechten Seite zum Bereich **Installationsdetails**, und erweitern Sie **Optionale Komponenten** unter **Linux-Entwicklung mit C++** . Wählen Sie dann die gewünschten Komponenten aus. CMake-Unterstützung für Linux ist standardmäßig ausgewählt.

1. Klicken Sie auf **Ändern**, um mit der Installation fortzufahren.

## <a name="options-for-creating-a-linux-environment"></a>Optionen zum Erstellen einer Linux-Umgebung

Wenn Sie noch keinen Linux-Computer besitzen, können Sie einen virtuellen Linux-Computer in Azure erstellen. Weitere Informationen finden Sie unter [Schnellstart: Erstellen eines virtuellen Linux-Computers im Azure-Portal](/azure/virtual-machines/linux/quick-create-portal).

Unter Windows 10 können Sie Ihre bevorzugte Linux-Distribution im WSL (Windows-Subsystem für Linux) installieren und als Ziel verwenden. Weitere Informationen finden Sie unter [Windows-Subsystem für Linux – Installationsleitfaden für Windows 10](/windows/wsl/install-win10). Das WSL ist eine praktische Konsolenumgebung, die jedoch nicht für grafische Anwendungen empfohlen wird. 

::: moniker-end

::: moniker range="vs-2019"

## <a name="linux-setup-ubuntu-on-wsl"></a>Linux-Setup: Ubuntu im WSL

Wenn Sie für WSL entwickeln, ist es nicht erforderlich, eine Remoteverbindung hinzuzufügen oder SSH zu konfigurieren, um einen Build zu erstellen und zu debuggen. **zip** und **rsync** sind zur automatischen Synchronisierung von Linux-Headern mit Visual Studio für die IntelliSense-Unterstützung erforderlich. Wenn die erforderlichen Anwendungen noch nicht vorhanden sind, können Sie sie wie folgt installieren:

```bash
sudo apt-get install g++ gdb make rsync zip
```
::: moniker-end

::: moniker range=">=vs-2017"

## <a name="ubuntu-on-remote-linux-systems"></a>Ubuntu auf Linux-Remotesystemen

Auf dem Linux-Zielsystem müssen **openssh-server**, **g++** , **gdb** und **gdbserver** installiert sein. Zudem muss der SSH-Daemon ausgeführt werden. **ZIP** ist für die automatische Synchronisierung von Remoteheadern mit Ihrem lokalen Computer für IntelliSense-Unterstützung erforderlich. Wenn diese Anwendungen noch nicht vorhanden sind, können Sie sie wie folgt installieren:

1. Führen Sie bei einer Shelleingabeaufforderung auf dem Linux-Computer Folgendes aus:

   ```bash
   sudo apt-get install openssh-server g++ gdb gdbserver zip
   ```

   Aufgrund des Befehls „sudo“ werden Sie möglicherweise aufgefordert, Ihr Stammkennwort einzugeben.  Ist dies der Fall, geben Sie es ein und setzen den Vorgang fort. Nach Abschluss dieses Vorgangs sind die erforderlichen Dienste und Tools installiert.

1. Stellen Sie sicher, dass der SSH-Dienst auf dem Linux-Computer ausgeführt wird, indem Sie Folgendes ausführen:

   ```bash
   sudo service ssh start
   ```
   Damit wird der Dienst im Hintergrund gestartet und ausgeführt, sodass Verbindungen akzeptiert werden können.

::: moniker-end

::: moniker range="vs-2019"

## <a name="fedora-on-wsl"></a>Fedora auf dem WSL

Fedora verwendet den **dnf**-Paket-Installer. Führen Sie den folgenden Befehl aus, um **g++** , **gdb**, **rsync** und **zip** herunterzuladen:

   ```bash
   sudo dnf install gcc-g++ gdb rsync zip
   ```

**zip** und **rsync** sind zur automatischen Synchronisierung von Linux-Headern mit Visual Studio für die IntelliSense-Unterstützung erforderlich.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="fedora-on-remote-linux-systems"></a>Fedora auf Linux-Remotesystemen

Der Zielcomputer, auf dem Fedora ausgeführt wird, verwendet den **Dnf**-Paket-Installer. Um **openssh-server**, **g++** , **gdb**, **gdbserver** und **zip** herunterzuladen und den ssh-Daemon neu zu starten, befolgen Sie diese Anweisungen:

1. Führen Sie bei einer Shelleingabeaufforderung auf dem Linux-Computer Folgendes aus:

   ```bash
   sudo dnf install openssh-server gcc-g++ gdb gdb-gdbserver zip
   ```
   Aufgrund des Befehls „sudo“ werden Sie möglicherweise aufgefordert, Ihr Stammkennwort einzugeben.  Ist dies der Fall, geben Sie es ein und setzen den Vorgang fort. Nach Abschluss dieses Vorgangs sind die erforderlichen Dienste und Tools installiert.

1. Stellen Sie sicher, dass der SSH-Dienst auf dem Linux-Computer ausgeführt wird, indem Sie Folgendes ausführen:

   ```bash
   sudo systemctl start sshd
   ```

   Damit wird der Dienst im Hintergrund gestartet und ausgeführt, sodass Verbindungen akzeptiert werden können.

::: moniker-end

::: moniker range="vs-2015"

Die Unterstützung für die C++-Entwicklung für Linux ist in Visual Studio 2017 und höher verfügbar.

::: moniker-end

## <a name="next-steps"></a>Nächste Schritte

Jetzt können Sie ein Linux-Projekt erstellen oder öffnen und es so konfigurieren, dass es auf dem Zielsystem ausgeführt wird. Weitere Informationen finden Sie unter:

- [Erstellen eines neuen Linux-Projekts](create-a-new-linux-project.md)
- [Konfigurieren eines Linux CMake-Projekts](cmake-linux-project.md)
