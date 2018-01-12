---
title: Neues Projekt aus vorhandenem Code Releasekonfiguration | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.importwiz.releasesettings
dev_langs: C++
ms.assetid: 3e2fc73c-bdbd-4790-b2bd-d31731f0cece
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ff208af8bb89dbcb7df00b37ce542a5adae5fa23
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="specify-release-configuration-settings-create-new-project-from-existing-code-files-wizard"></a>Einstellungen für Releasekonfiguration angeben, Assistent "Neues Projekt aus vorhandenen Codedateien erstellen"
Verwenden Sie diese Seite des Assistenten für neue Projekt aus vorhandenen Codedateien erstellen, um Einstellungen für Releasekonfiguration Projekt anzugeben.  
  
## <a name="task-list"></a>Aufgabenliste  
 [Vorgehensweise: Erstellen eines C++-Projekts aus vorhandenem Code](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Identisch mit der Debug-Konfiguration**  
 Gibt an, dass der Assistent projekteinstellungen für Releasekonfiguration identisch zum Debuggen von Konfigurationseinstellungen-Projekt generiert wird. Diese Option ist standardmäßig aktiviert. Alle anderen Optionen auf dieser Seite sind inaktiv, es sei denn, Sie dieses Kontrollkästchen deaktiviert ist.  
  
 **Erstellen Sie über die Befehlszeile**  
 Gibt die Befehlszeile an, in dem das neue Projekt erstellt. Geben Sie den Namen des Compilers plus alle Schalter oder Argumente, die Sie verwenden, um das neue Projekt erstellen möchten. Diese Option ist bei der **externe Buildsystem** ausgewählt ist die **Projekteinstellungen angeben** Seite.  
  
 **Erstellen Sie über die Befehlszeile neu.**  
 Gibt die Befehlszeile an, die das neue Projekt wird neu erstellt. Diese Option ist bei der **externe Buildsystem** ausgewählt ist die **Projekteinstellungen angeben** Seite.  
  
 **Bereinigen über die Befehlszeile**  
 Gibt die Befehlszeile zum Löschen von unterstützenden Dateien, die von den Buildtools für das neue Projekt generiert. Diese Option ist bei der **externe Buildsystem** ausgewählt ist die **Projekteinstellungen angeben** Seite.  
  
 **Ausgabe (für das Debuggen)**  
 Gibt den Pfad der Ausgabedateien für die Debugkonfiguration des neuen Projekts an. Diese Option ist bei der **externe Buildsystem** ausgewählt ist die **Projekteinstellungen angeben** Seite.  
  
 **Präprozessordefinitionen (/ D)**  
 Definiert Präprozessorsymbole für das neue Projekt. Weitere Informationen finden Sie unter [/D (Preprocessor Definitions)](../build/reference/d-preprocessor-definitions.md).  
  
 **Suchpfad einschließen (/ I)**  
 Gibt die Verzeichnispfade zum Hinzufügen zur Liste der Verzeichnisse, die der Compiler durchsucht, um Dateiverweise aufzulösen, Präprozessordirektiven im neuen Projekt übergeben. Weitere Informationen finden Sie unter [/I (Zusätzliche Includeverzeichnisse)](../build/reference/i-additional-include-directories.md).  
  
 **Erzwungene eingeschlossene Dateien (/ Fi)**  
 Gibt die Header-Dateien zu verarbeiten, wenn das neue Projekt zu erstellen. Weitere Informationen finden Sie unter [/FI (Name der expliziten Includedatei)](../build/reference/fi-name-forced-include-file.md).  
  
 **.NET Assemblysuchpfad (/ AI)**  
 Gibt an, die Verzeichnispfade, die der Compiler durchsucht, um das Auflösen von Assemblyverweisen .NET Präprozessordirektiven im neuen Projekt übergeben. Weitere Informationen finden Sie unter [/AI (Metadatenverzeichnisse festlegen)](../build/reference/ai-specify-metadata-directories.md).  
  
 **Erzwungenes verwenden (/ FU)**  
 Gibt die zu verarbeitenden, wenn Sie das neue Projekt zu erstellen. Weitere Informationen finden Sie unter [/FU (Name der expliziten #using-Datei)](../build/reference/fu-name-forced-hash-using-file.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Projekteinstellungen angeben, Assistent "Neues Projekt aus vorhandenen Codedateien erstellen"](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)