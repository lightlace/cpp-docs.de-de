---
title: Neues Projekt aus vorhandenem Code Debuggen Einstellung (Visual C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.importwiz.debugsettings
dev_langs: C++
ms.assetid: 607339a8-9d33-458b-8095-dc73f374e29d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1781d5c5bba0d818111673594a5526354a490bd7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="specify-debug-configuration-settings-create-new-project-from-existing-code-files-wizard"></a>Einstellungen für Debugkonfiguration angeben, Assistent "Neues Projekt aus vorhandenen Codedateien erstellen"
Verwenden Sie diese Seite des Assistenten für neue Projekt aus vorhandenen Codedateien erstellen, um Einstellungen für Debugkonfiguration Projekt anzugeben.  
  
## <a name="task-list"></a>Aufgabenliste  
 [Vorgehensweise: Erstellen eines C++-Projekts aus vorhandenem Code](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Erstellen Sie über die Befehlszeile**  
 Gibt die Befehlszeile an, in dem das neue Projekt erstellt. Geben Sie beispielsweise den Namen des Compilers (sowie alle Schalter und Argumente) oder die Buildskripts verwenden, um das neue Projekt erstellt werden sollen. Diese Option ist bei der **externe Buildsystem** ausgewählt ist die **Projekteinstellungen angeben** Seite; andernfalls ist es nicht verfügbar.  
  
 **Erstellen Sie über die Befehlszeile neu.**  
 Gibt die Befehlszeile an, die das neue Projekt wird neu erstellt. Diese Option ist bei der **externe Buildsystem** ausgewählt ist die **Projekteinstellungen angeben** Seite; andernfalls ist es nicht verfügbar.  
  
 **Bereinigen über die Befehlszeile**  
 Gibt die Befehlszeile zum Löschen von unterstützenden Dateien, die von den Buildtools für das neue Projekt generiert. Diese Option ist bei der **externe Buildsystem** ausgewählt ist die **Projekteinstellungen angeben** Seite; andernfalls ist es nicht verfügbar.  
  
 **Ausgabe (für das Debuggen)**  
 Gibt den Pfad der Ausgabedateien für die Debugkonfiguration des neuen Projekts an. Diese Option ist bei der **externe Buildsystem** ausgewählt ist die **Projekteinstellungen angeben** Seite; andernfalls ist es nicht verfügbar.  
  
 **Präprozessordefinitionen (/ D)**  
 Definiert Präprozessorsymbole für das neue Projekt. Weitere Informationen finden Sie unter [/D (Präprozessordefinitionen)](../build/reference/d-preprocessor-definitions.md).  
  
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
