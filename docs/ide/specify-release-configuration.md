---
title: Releasekonfiguration „Neues Projekt aus vorhandenem Code“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.importwiz.releasesettings
dev_langs:
- C++
ms.assetid: 3e2fc73c-bdbd-4790-b2bd-d31731f0cece
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 414d50ad15ad9eb85760aac470421df39e250ad0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390811"
---
# <a name="specify-release-configuration-settings-create-new-project-from-existing-code-files-wizard"></a>Einstellungen für Releasekonfiguration angeben, Assistent "Neues Projekt aus vorhandenen Codedateien erstellen"

Verwenden Sie diese Seite des Assistenten zum Erstellen eines neuen Projekts aus vorhandenen Codedateien, um die Releasekonfiguration der Projekteinstellungen anzugeben.

## <a name="task-list"></a>Aufgabenliste

[Vorgehensweise: Erstellen eines C++-Projekts aus vorhandenem Code](../ide/how-to-create-a-cpp-project-from-existing-code.md)

## <a name="uielement-list"></a>UIElement-Liste

- **Identisch mit der Debugkonfiguration**

   Gibt an, dass der Assistent die Projekteinstellungen der Releasekonfiguration identisch mit den Projekteinstellungen für die Debugkonfiguration erstellt. Diese Option ist standardmäßig aktiviert. Alle anderen Optionen auf dieser Seite sind inaktiv, es sei denn, Sie deaktivieren dieses Kontrollkästchen.

- **Buildbefehlszeile**

   Gibt die Befehlszeile an, mit der das neue Projekt erstellt wird. Geben Sie den Namen des Compilers einschließlich aller Parameter und Argumente an, den Sie zum Erstellen des neuen Projekts verwenden möchten. Diese Option ist aktiviert, wenn die Option **Use external build system** (Externes Buildsystem verwenden) auf der Seite **Projekteinstellungen angeben** ausgewählt ist.

- **Neuerstellungsbefehlszeile**

   Gibt die Befehlszeile an, mit der das neue Projekt neu erstellt wird. Diese Option ist aktiviert, wenn die Option **Use external build system** (Externes Buildsystem verwenden) auf der Seite **Projekteinstellungen angeben** ausgewählt ist.

- **Befehlszeile „Bereinigen“**

   Gibt die Befehlszeile zum Löschen der von den Buildtools für das neue Projekt erstellten Unterstützungsdateien an. Diese Option ist aktiviert, wenn die Option **Use external build system** (Externes Buildsystem verwenden) auf der Seite **Projekteinstellungen angeben** ausgewählt ist.

- **Ausgabe (zum Debuggen)**

   Gibt den Verzeichnispfad der Ausgabedateien für die Debugkonfiguration des neuen Projekts an. Diese Option ist aktiviert, wenn die Option **Use external build system** (Externes Buildsystem verwenden) auf der Seite **Projekteinstellungen angeben** ausgewählt ist.

- **Präprozessordefinitionen (/D)**

   Definiert Präprozessorsymbole für das neue Projekt. Weitere Informationen finden Sie unter [/D (Preprocessor Definitions)](../build/reference/d-preprocessor-definitions.md).

- **Includesuchpfad (/I)**

   Gibt Verzeichnispfade an, die der Liste von Verzeichnissen hinzugefügt werden sollen, die der Compiler sucht, um Dateiverweise aufzulösen, die an Präprozessordirektiven im neuen Projekt übergeben werden. Weitere Informationen finden Sie unter [/I (Zusätzliche Includeverzeichnisse)](../build/reference/i-additional-include-directories.md).

- **Erzwungene Includedateien (/FI)**

   Gibt Headerdateien an, die beim Erstellen des neuen Projekts verarbeitet werden. Weitere Informationen finden Sie unter [/FI (Name der expliziten Includedatei)](../build/reference/fi-name-forced-include-file.md).

- **.NET-Assemblysuchpfad (/AI)**

   Gibt die Verzeichnispfade an, die der Compiler durchsucht, um .NET-Assemblyverweise aufzulösen, die an Präprozessordirektiven im neuen Projekt übergeben werden. Weitere Informationen finden Sie unter [/AI (Metadatenverzeichnisse festlegen)](../build/reference/ai-specify-metadata-directories.md).

- **Erzwungene Verwendung von .NET-Assemblys (/FU)**

   Gibt .NET-Assemblys an, die beim Erstellen des neuen Projekts verarbeitet werden. Weitere Informationen finden Sie unter [/FU (Name der expliziten #using-Datei)](../build/reference/fu-name-forced-hash-using-file.md).

## <a name="see-also"></a>Siehe auch

[Projekteinstellungen angeben, Assistent "Neues Projekt aus vorhandenen Codedateien erstellen"](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)