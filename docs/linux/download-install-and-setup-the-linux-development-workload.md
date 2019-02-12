---
title: Installieren der C++-Workload unter Linux in Visual Studio
description: Informationen zum Herunterladen, Installieren und Einrichten der Linux-Workload für C++ in Visual Studio
ms.date: 02/06/2019
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
ms.openlocfilehash: c01c8ddeeb8439a7610c0f6c7c11b608ab3675d8
ms.sourcegitcommit: 63c072f5e941989636f5a2b13800b68bb7129931
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "55763884"
---
# <a name="download-install-and-setup-the-linux-workload"></a>Herunterladen, Installieren und Einrichten der Linux-Workload

Sie können die Visual Studio-IDE unter Windows verwenden, um C++-Projekte zu erstellen, zu bearbeiten und zu debuggen, die auf einem physischen Linux-Computer, einem virtuellen Computer oder dem [Windows-Subsystem für Linux](/windows/wsl/about) ausgeführt werden. Für jedes dieser Szenarien installieren Sie zunächst die Workload **Linux-Entwicklung mit C++**.

## <a name="visual-studio-setup"></a>Setup von Visual Studio

1. Geben Sie „Visual Studio Installer“ in das Windows-Suchfeld ein: ![Windows-Suchfeld](media/visual-studio-installer-search.png)
2. Suchen Sie in den Ergebnissen unter **Apps** nach dem Installer, und doppelklicken Sie auf ihn. Wenn der Installer geöffnet wird, wählen Sie **Ändern**aus, und klicken Sie dann auf die Registerkarte **Workloads**. Scrollen Sie nach unten zu **Andere Toolsets**, und wählen Sie die Workload **Linux Entwicklung mit C++** aus.

   ![Workload „Visual C++ für Linux-Entwicklung“](media/linuxworkload.png)

1. Wenn Sie CMake verwenden oder IoT- oder eingebettete Zielplattformen nutzen möchten, navigieren Sie auf der rechten Seite zum Bereich **Installationsdetails**, und erweitern Sie **Optionale Komponenten** unter **Linux-Entwicklung mit C++**. Wählen Sie dann die gewünschten Komponenten aus.

1. Klicken Sie auf **Ändern**, um mit der Installation fortzufahren.

## <a name="options-for-creating-a-linux-environment"></a>Optionen zum Erstellen einer Linux-Umgebung

Wenn Sie noch keinen Linux-Computer besitzen, können Sie einen virtuellen Linux-Computer in Azure erstellen. Weitere Informationen finden Sie unter [Schnellstart: Erstellen eines virtuellen Linux-Computers im Azure-Portal](/azure/virtual-machines/linux/quick-create-portal).

Eine weitere Möglichkeit unter Windows 10 besteht darin, das Windows-Subsystem für Linux zu aktivieren. Weitere Informationen finden Sie im [Windows 10-Installationshandbuch](/windows/wsl/install-win10).

## <a name="linux-setup-ubuntu"></a>Linux-Setup: Ubuntu

Auf dem Linux-Zielcomputer müssen **openssh-server**, **g++**, **gdb** und **gdbserver** installiert sein. Zudem muss der SSH-Daemon ausgeführt werden. **ZIP** ist für die automatische Synchronisierung von Remoteheadern mit Ihrem lokalen Computer für IntelliSense-Unterstützung erforderlich. Wenn diese Anwendungen noch nicht vorhanden sind, können Sie sie wie folgt installieren:

1. Führen Sie bei einer Shelleingabeaufforderung auf dem Linux-Computer Folgendes aus:

   `sudo apt-get install openssh-server g++ gdb gdbserver zip`

   Aufgrund des Befehls „sudo“ werden Sie möglicherweise aufgefordert, Ihr Stammkennwort einzugeben.  Ist dies der Fall, geben Sie es ein und setzen den Vorgang fort. Nach Abschluss dieses Vorgangs sind die erforderlichen Dienste und Tools installiert.

1. Stellen Sie sicher, dass der SSH-Dienst auf dem Linux-Computer ausgeführt wird, indem Sie Folgendes ausführen:

   `sudo service ssh start`

   Damit wird der Dienst im Hintergrund gestartet und ausgeführt, sodass Verbindungen akzeptiert werden können.

## <a name="linux-setup-fedora"></a>Linux-Setup: Fedora

Der Zielcomputer, auf dem Fedora ausgeführt wird, verwendet den **Dnf**-Paket-Installer. Um **openssh-server**, **g++**, **gdb**, **gdbserver** und **zip** herunterzuladen und den ssh-Daemon neu zu starten, befolgen Sie diese Anweisungen:

1. Führen Sie bei einer Shelleingabeaufforderung auf dem Linux-Computer Folgendes aus:

   `sudo dnf install openssh-server gcc-g++ gdb gdb-gdbserver zip`

   Aufgrund des Befehls „sudo“ werden Sie möglicherweise aufgefordert, Ihr Stammkennwort einzugeben.  Ist dies der Fall, geben Sie es ein und setzen den Vorgang fort. Nach Abschluss dieses Vorgangs sind die erforderlichen Dienste und Tools installiert.

1. Stellen Sie sicher, dass der SSH-Dienst auf dem Linux-Computer ausgeführt wird, indem Sie Folgendes ausführen:

   `sudo systemctl start sshd`

   Damit wird der Dienst im Hintergrund gestartet und ausgeführt, sodass Verbindungen akzeptiert werden können.

