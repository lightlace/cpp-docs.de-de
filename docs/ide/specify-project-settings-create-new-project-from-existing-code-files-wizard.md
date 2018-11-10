---
title: Projekteinstellungen angeben, Assistent "Neues Projekt aus vorhandenen Codedateien erstellen"
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.importwiz.appsettings
helpviewer_keywords:
- Create New Project From Existing Code Files Wizard, project settings
ms.assetid: 9b8860c9-d35f-4f18-9565-2934d3d7f569
ms.openlocfilehash: f46436295e16d527718e59f1c4c199643f9e35ed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522342"
---
# <a name="specify-project-settings-create-new-project-from-existing-code-files-wizard"></a>Projekteinstellungen angeben, Assistent "Neues Projekt aus vorhandenen Codedateien erstellen"

Verwenden Sie diese Seite des Assistenten zum Erstellen eines neuen Projekts aus vorhandenen Codedateien, um Folgendes anzugeben:

- Die Buildumgebung für das neue Projekt

- Buildeinstellungen, die dem spezifischen Typ des zu erstellenden Projekts entsprechen

## <a name="task-list"></a>Aufgabenliste

[Vorgehensweise: Erstellen eines C++-Projekts aus vorhandenem Code](../ide/how-to-create-a-cpp-project-from-existing-code.md)

## <a name="uielement-list"></a>UIElement-Liste

- **Visual Studio verwenden**

   Gibt an, dass Buildtools verwendet werden sollen, die zum Erstellen des neuen Projekts in Visual Studio enthalten sind. Diese Option ist standardmäßig ausgewählt.

- **Projekttyp**

   Gibt den Typ des Projekts an, das vom Assistenten generiert wird.

- **Windows-Anwendungsprojekt**

   Gibt an, dass der Assistent ein Projekt für eine ausführbare Windows-Anwendung generiert. Diese Option ist im Dropdownlistenfeld **Projekttyp** verfügbar.

- **Konsolenanwendungsprojekt**

   Gibt an, dass der Assistent ein Projekt für eine Konsolenanwendung generiert. Diese Option ist im Dropdownlistenfeld **Projekttyp** verfügbar.

- **DLL-Projekt (Dynamic Link Library)**

   Gibt an, dass der Assistent ein Projekt für eine leere DLL-Anwendung generiert. Diese Option ist im Dropdownlistenfeld **Projekttyp** verfügbar.

- **LIB-Projekt (Static Library, Statische Bibliothek)**

   Gibt an, dass der Assistent ein Projekt für eine LIB-Anwendung generiert. Diese Option ist im Dropdownlistenfeld **Projekttyp** verfügbar.

- **ATL-Unterstützung hinzufügen**

   Fügt dem neuen Projekt ATL-Unterstützung hinzu.

- **MFC-Unterstützung hinzufügen**

   Fügt dem neuen Projekt MFC-Unterstützung hinzu.

- **CLR-Unterstützung hinzufügen**

   Fügt dem neuen Projekt CLR-Programmierungsunterstützung hinzu.

- **Common Language Runtime**

   Legt fest, dass das neue Projekt mit CLR-Features konform sein muss.

- **Common Language Runtime (alte Syntax)**

   Legt fest, dass das neue Projekt mit der Syntax „Managed Extensions for C++“ konform sein muss, was die CLR-Programmiersyntax vor Visual C++ 2005 war.

- **Externes Buildsystem verwenden**

   Gibt an, dass Buildtools verwendet werden sollen, die zum Erstellen des neuen Projekts nicht in Visual Studio enthalten sind. Wenn diese Option ausgewählt ist, können Sie Buildbefehlszeilen auf den Seiten **Einstellungen für Debugkonfiguration angeben** und **Einstellungen für Releasekonfiguration angeben** angeben.

   > [!NOTE]
   > Wenn die Option **Externes Buildsystem verwenden** aktiviert ist, erstellt die IDE das neue Projekt nicht, die Optionen „/D“, „/I“, „/FI“, „/AI“, und „/FU“ sind für die Kompilierung also nicht erforderlich. Diese Optionen müssen allerdings ordnungsgemäß festgelegt werden, damit IntelliSense ordnungsgemäß funktioniert.

## <a name="see-also"></a>Siehe auch

[Einstellungen für Debugkonfiguration angeben, Assistent "Neues Projekt aus vorhandenen Codedateien erstellen"](../ide/specify-debug-configuration-settings.md)<br>
[Einstellungen für Releasekonfiguration angeben, Assistent „Neues Projekt aus vorhandenen Codedateien erstellen“](../ide/specify-release-configuration.md)