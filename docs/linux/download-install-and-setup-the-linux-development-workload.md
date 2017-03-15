---
title: Herunterladen, Installieren und Einrichten der Linux-Arbeitsauslastung | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
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
translationtype: Human Translation
ms.sourcegitcommit: dff1e9e03911f65dfcffcd078e0739224f73f4aa
ms.openlocfilehash: 09ce0024b7a98729b28968fff081ed105b5463e1
ms.lasthandoff: 02/24/2017

---

# <a name="download-install-and-setup-the-linux-workload"></a>Herunterladen, Installieren und Einrichten der Linux-Arbeitsauslastung

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

