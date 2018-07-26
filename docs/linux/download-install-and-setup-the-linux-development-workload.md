---
title: Installieren einer neuen Linux-Workload für C++ in Visual Studio | Microsoft-Dokumentation
description: Informationen zum Herunterladen, Installieren und Einrichten der Linux-Workload für C++ in Visual Studio
ms.custom: ''
ms.date: 07/20/2018
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
ms.openlocfilehash: e33b9ac72ca7691ccbb80a9a30349d3a1e31e194
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207558"
---
# <a name="download-install-and-setup-the-linux-workload"></a>Herunterladen, Installieren und Einrichten der Linux-Workload

Sie müssen die Workload **Linux Entwicklung mit C++** installieren, damit Sie die Visual Studio-IDE zum Erstellen und Debuggen von C++-Projekten unter Linux verwenden können.

## <a name="visual-studio-setup"></a>Setup von Visual Studio
1. Starten Sie den Visual Studio-Installer, und wählen Sie die Arbeitsauslastung **Linux Entwicklung mit C++** aus.

   ![Erweiterung für Visual C++ für Linux-Entwicklung](media/linuxworkload.png)

2. Klicken Sie auf **Installieren**, um mit der Installation fortzufahren.

## <a name="linux-setup"></a>Linux-Setup
Auf dem Linux-Zielcomputer müssen **openssh-server**, **g++**, **gdb** und **gdbserver** installiert sein. Zudem muss der SSH-Daemon ausgeführt werden.  Ist dies nicht der Fall, kann die Installation wie folgt durchgeführt werden:
 
1. Führen Sie bei einer Shelleingabeaufforderung auf dem Linux-Computer Folgendes aus:

   `sudo apt-get install openssh-server g++ gdb gdbserver`

   Aufgrund des Befehls „sudo“ werden Sie möglicherweise aufgefordert, Ihr Stammkennwort einzugeben.  Ist dies der Fall, geben Sie es ein und setzen den Vorgang fort.  Nach Abschluss dieses Vorgangs sind diese Dienste und Tools installiert.

1. Stellen Sie sicher, dass der SSH-Dienst auf dem Linux-Computer ausgeführt wird, indem Sie Folgendes ausführen:

   `sudo service ssh start`
   
   Damit wird der Dienst im Hintergrund gestartet und ausgeführt, sodass Verbindungen akzeptiert werden.
