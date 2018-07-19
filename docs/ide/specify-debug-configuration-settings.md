---
title: Neues Projekt aus vorhandenen Codeeinstellungen zum Debuggen (Visual C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.importwiz.debugsettings
dev_langs:
- C++
ms.assetid: 607339a8-9d33-458b-8095-dc73f374e29d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b40bafe817ebf1dd25cc40115635b895502e0df8
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "33335041"
---
# <a name="specify-debug-configuration-settings-create-new-project-from-existing-code-files-wizard"></a>Einstellungen für Debugkonfiguration angeben, Assistent "Neues Projekt aus vorhandenen Codedateien erstellen"
Verwenden Sie diese Seite des Assistenten zum Erstellen eines neuen Projekts aus vorhandenen Codedateien, um die Debugkonfiguration der Projekteinstellungen anzugeben.  
  
## <a name="task-list"></a>Aufgabenliste  
 [Vorgehensweise: Erstellen eines C++-Projekts aus vorhandenem Code](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Buildbefehlszeile**  
 Gibt die Befehlszeile an, mit der das neue Projekt erstellt wird. Geben Sie beispielsweise den Namen des Compilers (einschließlich aller Optionen und Argumente) oder des Buildskripts an, der bzw. das zum Erstellen des neuen Projekts verwendet werden soll. Diese Option ist aktiviert, wenn die Option **Use external build system** (Externes Buildsystem verwenden) auf der Seite **Projekteinstellungen angeben** ausgewählt ist; andernfalls ist sie nicht verfügbar.  
  
 **Neuerstellungsbefehlszeile**  
 Gibt die Befehlszeile an, mit der das neue Projekt neu erstellt wird. Diese Option ist aktiviert, wenn die Option **Use external build system** (Externes Buildsystem verwenden) auf der Seite **Projekteinstellungen angeben** ausgewählt ist; andernfalls ist sie nicht verfügbar.  
  
 **Befehlszeile „Bereinigen“**  
 Gibt die Befehlszeile zum Löschen der von den Buildtools für das neue Projekt erstellten Unterstützungsdateien an. Diese Option ist aktiviert, wenn die Option **Use external build system** (Externes Buildsystem verwenden) auf der Seite **Projekteinstellungen angeben** ausgewählt ist; andernfalls ist sie nicht verfügbar.  
  
 **Ausgabe (zum Debuggen)**  
 Gibt den Verzeichnispfad der Ausgabedateien für die Debugkonfiguration des neuen Projekts an. Diese Option ist aktiviert, wenn die Option **Use external build system** (Externes Buildsystem verwenden) auf der Seite **Projekteinstellungen angeben** ausgewählt ist; andernfalls ist sie nicht verfügbar.  
  
 **Präprozessordefinitionen (/D)**  
 Definiert Präprozessorsymbole für das neue Projekt. Weitere Informationen finden Sie unter [/D (Preprocessor Definitions)](../build/reference/d-preprocessor-definitions.md).  
  
 **Includesuchpfad (/I)**  
 Gibt Verzeichnispfade an, die der Liste von Verzeichnissen hinzugefügt werden sollen, die der Compiler sucht, um Dateiverweise aufzulösen, die an Präprozessordirektiven im neuen Projekt übergeben werden. Weitere Informationen finden Sie unter [/I (Zusätzliche Includeverzeichnisse)](../build/reference/i-additional-include-directories.md).  
  
 **Erzwungene Includedateien (/FI)**  
 Gibt Headerdateien an, die beim Erstellen des neuen Projekts verarbeitet werden. Weitere Informationen finden Sie unter [/FI (Name der expliziten Includedatei)](../build/reference/fi-name-forced-include-file.md).  
  
 **.NET-Assemblysuchpfad (/AI)**  
 Gibt die Verzeichnispfade an, die der Compiler durchsucht, um .NET-Assemblyverweise aufzulösen, die an Präprozessordirektiven im neuen Projekt übergeben werden. Weitere Informationen finden Sie unter [/AI (Metadatenverzeichnisse festlegen)](../build/reference/ai-specify-metadata-directories.md).  
  
 **Erzwungene Verwendung von .NET-Assemblys (/FU)**  
 Gibt .NET-Assemblys an, die beim Erstellen des neuen Projekts verarbeitet werden. Weitere Informationen finden Sie unter [/FU (Name der expliziten #using-Datei)](../build/reference/fu-name-forced-hash-using-file.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Projekteinstellungen angeben, Assistent "Neues Projekt aus vorhandenen Codedateien erstellen"](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)
