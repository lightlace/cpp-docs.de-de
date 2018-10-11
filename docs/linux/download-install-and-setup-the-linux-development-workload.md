---
title: Installieren einer neuen Linux-Workload für C++ in Visual Studio | Microsoft-Dokumentation
description: Informationen zum Herunterladen, Installieren und Einrichten der Linux-Workload für C++ in Visual Studio
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-linux
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 403f1bcd8634c3f471f34ff1266501de5bf05d52
ms.sourcegitcommit: 87d317ac62620c606464d860aaa9e375a91f4c99
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45601391"
---
# <a name="download-install-and-setup-the-linux-workload"></a>Herunterladen, Installieren und Einrichten der Linux-Workload

Sie können die Visual Studio-IDE unter Windows verwenden, um C++-Projekte zu erstellen, zu bearbeiten und zu debuggen, die auf einem physischen Linux-Computer, einem virtuellen Computer oder dem [Windows-Subsystem für Linux](/windows/wsl/about) ausgeführt werden. Für jedes dieser Szenarien installieren Sie zunächst die Workload **Linux-Entwicklung mit C++**.

## <a name="visual-studio-setup"></a>Setup von Visual Studio

1. Geben Sie „Visual Studio-Installer“ in das Windows-Suchmenü ein, und suchen Sie unter den Ergebnissen **Apps** nach dem Installer. Doppelklicken Sie anschließend darauf. Wenn der Installer geöffnet wird, wählen Sie **Ändern**aus, und klicken Sie dann auf die Registerkarte **Workloads**. Scrollen Sie nach unten zu **Andere Toolsets**, und wählen Sie die Workload **Linux Entwicklung mit C++** aus.

   ![Workload „Visual C++ für Linux-Entwicklung“](media/linuxworkload.png)

1. Wenn Sie CMake verwenden oder IoT- oder eingebettete Zielplattformen nutzen möchten, navigieren Sie auf der rechten Seite zum Bereich **Installationsdetails**, und erweitern Sie **Optionale Komponenten** unter **Linux-Entwicklung mit C++**. Wählen Sie dann die gewünschten Komponenten aus. 

1. Klicken Sie auf **Ändern**, um mit der Installation fortzufahren.


## <a name="options-for-creating-a-linux-environment"></a>Optionen zum Erstellen einer Linux-Umgebung

Wenn Sie noch keinen Linux-Computer besitzen, können Sie einen virtuellen Linux-Computer in Azure erstellen. Weitere Informationen finden Sie unter [Schnellstart: Erstellen eines virtuellen Linux-Computers im Azure-Portal](/azure/virtual-machines/linux/quick-create-portal).

Eine weitere Möglichkeit unter Windows 10 besteht darin, das Windows-Subsystem für Linux zu aktivieren. Weitere Informationen finden Sie im [Windows 10-Installationshandbuch](/windows/wsl/install-win10).

## <a name="linux-setup"></a>Linux-Setup

Auf dem Linux-Zielcomputer müssen **openssh-server**, **g++**, **gdb** und **gdbserver** installiert sein. Zudem muss der SSH-Daemon ausgeführt werden. **ZIP** ist für die automatische Synchronisierung von Remoteheadern mit Ihrem lokalen Computer für IntelliSense-Unterstützung erforderlich. Wenn diese Anwendungen noch nicht vorhanden sind, können Sie sie wie folgt installieren:

1. Führen Sie bei einer Shelleingabeaufforderung auf dem Linux-Computer Folgendes aus:

   `sudo apt-get install openssh-server g++ gdb gdbserver zip`

   Aufgrund des Befehls „sudo“ werden Sie möglicherweise aufgefordert, Ihr Stammkennwort einzugeben.  Ist dies der Fall, geben Sie es ein und setzen den Vorgang fort.  Nach Abschluss dieses Vorgangs sind diese Dienste und Tools installiert.

1. Stellen Sie sicher, dass der SSH-Dienst auf dem Linux-Computer ausgeführt wird, indem Sie Folgendes ausführen:

   `sudo service ssh start`

   Damit wird der Dienst im Hintergrund gestartet und ausgeführt, sodass Verbindungen akzeptiert werden.
