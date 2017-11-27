---
title: Debuggereigenschaften (Linux C++) | Microsoft Docs
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c1c0fcc-a49b-451c-a5cb-ce9711fac064
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.RaspberryDebugger.DebuggerType
- VC.Project.IVCLocalDebugPageObject.CommandArguments
- VC.Project.IVCLocalDebugPageObject.WorkingDirectory
- VC.Project.RaspberryDebugger.LaunchActivity
- VC.Project.LinuxDebugger.DebugChildProcesses
ms.openlocfilehash: d47645eab33ffb0ee6a203fdfb0cf30c856ea63f
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2017
---
# <a name="c-debugging-properties-linux-c"></a>C++-Debugeigenschaften (Linux C++)

Eigenschaft | Beschreibung | Auswahlmöglichkeiten
--- | ---| ---
Befehl vor dem Start | Ein Befehl, der für die Shell ausgeführt wird, bevor das Debuggen beginnt und bevor der Debugger ausgeführt wird. Er kann verwendet werden, um die Debugumgebung zu beeinflussen.
Program | Der vollständige Pfad zu dem auf dem Remotesystem zu debuggenden Programm. Dies ist ein Pfad auf dem Remotesystem. Wenn die Angabe leer oder unverändert gelassen wird, wird standardmäßig die aktuelle Projektausgabe verwendet.
Programmargumente | Die Befehlszeilenargumente, die an das zu debuggende Programm übergeben werden sollen.
Arbeitsverzeichnis | Das Arbeitsverzeichnis der Remoteanwendung. Standardmäßig ist dies das Basisverzeichnis des Benutzers.
Zusätzliche Debuggerbefehle | Zusätzliche GDB-Befehle, die der Debugger vor dem Starten des Debuggens ausführt.
Debuggerportnummer | Die Portnummer für die Debuggerkommunikation mit dem Remotedebugger. Der Port darf nicht lokal in Gebrauch sein. Dieser Wert muss eine positive Zahl zwischen 1 und 65.535 sein. Wenn keine Angabe erfolgt, wird eine freie Portnummer verwendet.
Portnummer des Remotedebuggers | Die Portnummer, an der der Remotedebuggerserver (gdbserver) auf dem Remotesystem lauscht. Der Port darf auf dem Remotesystem nicht in Gebrauch sein. Dieser Wert muss eine positive Zahl zwischen 1 und 65.535 sein. Wenn keine Angabe erfolgt, wird eine freie Portnummer ab 4.444 verwendet.
Debugmodus | Gibt an, wie der Debugger mit GDB kommuniziert. Im GDB-Modus steuert der Debugger GDB über die Shell auf dem Remotesystem. Im gdbserver-Modus wird GDB lokal ausgeführt und stellt eine Verbindung mit dem gdbserver her, der remote ausgeführt wird. | **gdbserver**<br>**gdb**<br>
Zusätzliche Symbolsuchpfaden | Zusätzlicher Suchpfad für Debugsymbole (solib-search-path).
Untergeordnete Prozesse debuggen | Gibt an, ob Debuggen für untergeordnete Prozesse aktiviert werden soll.
Python Pretty Printing aktivieren | Aktiviert Pretty Printing von Ausdruckswerten. Wird nur im GDB-Debugmodus unterstützt.
Visualisierungsdatei | Systemeigene Visualisierungsstandarddatei (NATVIS-Datei), die die Visualisierungsdirektiven für SLT-Typen enthält. Andere NATVIS-Dateien, die zur aktuellen Projektmappe gehören, werden automatisch geladen.
Zusätzliche Dateipfadzuordnung für Quellen | Zusätzliche Pfadäquivalenzen für den Debugger, um Windows-Quelldateinamen Linux-Quelldateinamen zuzuordnen. Das Format ist „\<Windows-Pfad>=\<Linux-Pfad>;...“. Auf einen Quelldateinamen, der unter dem Windows-Pfad gefunden wird, wird so verwiesen, als ob er an der gleichen relativen Position unter dem Linux-Pfad gefunden wurde. Dateien, die im lokalen Projekt gefunden werden, benötigen keine zusätzliche Zuordnung.