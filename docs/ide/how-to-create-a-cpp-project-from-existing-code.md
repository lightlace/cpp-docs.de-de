---
title: 'Gewusst wie: Erstellen eines C++-Projekts aus vorhandenem Code'
ms.date: 11/04/2016
helpviewer_keywords:
- C++, creating projects from existing code
ms.assetid: e328a938-395c-48ea-9e35-dd433de12b31
ms.openlocfilehash: dafd4e939444c581a76e9ccfcab4c3f6bbe819d3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552502"
---
# <a name="how-to-create-a-c-project-from-existing-code"></a>Gewusst wie: Erstellen eines C++-Projekts aus vorhandenem Code

In Visual Studio können Sie vorhandene Codedateien mit dem Assistenten **Neues Projekt aus vorhandenen Codedateien erstellen** in ein Visual C++-Projekt portieren. Der Assistent ist in älteren Express-Editionen von Visual Studio nicht verfügbar. Dieser Assistent erstellt eine neue Projektmappe und ein neues Projekt, die das MSBuild-System zum Verwalten der Quelldateien und Buildkonfiguration verwenden.

Durch das Portieren Ihrer vorhandenen Codedateien in ein Visual C++-Projekt wird Ihnen ermöglicht, alle nativen MSBuild-Projektverwaltungsfeatures zu verwenden, die in der IDE integriert sind. Wenn Sie es vorziehen, Ihr vorhandenes Buildsystem zu verwenden, z.B. NMake-Makefiles, CMake oder andere, können Sie stattdessen die Option „Ordner öffnen“ verwenden. Weitere Informationen finden Sie unter [Ordner öffnen-Projekte in Visual C++](../ide/non-msbuild-projects.md). Mit beiden Optionen können Sie IDE-Features wie [IntelliSense](/visualstudio/ide/using-intellisense) und [Projekteigenschaften](../ide/working-with-project-properties.md) verwenden.

### <a name="to-create-a-c-project-from-existing-code"></a>So erstellen Sie ein C++-Projekt aus vorhandenem Code

1. Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt aus vorhandenem Code**.

1. Wählen Sie auf der ersten Seite des Assistenten **Neues Projekt aus vorhandenen Codedateien erstellen** in der Liste **Ein Projekt welchen Typs möchten Sie erstellen?** die Option **Visual C++** aus. Klicken Sie auf **Weiter** , um fortzufahren.

1. Legen Sie den Speicherort Ihres Projekts und das Verzeichnis für Ihre Quelldateien fest. Ausführliche Informationen zu dieser Seite finden Sie unter [Specify Project Location and Source Files, Create New Project From Existing Code Files Wizard (Projektspeicherort und Quelldateien festlegen, Assistent „Neues Projekt aus vorhandenen Codedateien erstellen“)](../ide/specify-project-location-and-source-files.md). Klicken Sie auf **Weiter** , um fortzufahren.

1. Legen Sie die zu verwendenden Projekteinstellungen fest. Ausführliche Informationen zu dieser Seite finden Sie unter [Specify Project Settings, Create New Project From Existing Code Files Wizard (Projekteinstellungen angeben, Assistent „Neues Projekt aus vorhandenen Codedateien erstellen“)](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md). Klicken Sie auf **Weiter** , um fortzufahren.

1. Legen Sie die zu verwendenden Debugkonfigurationseinstellungen fest. Ausführliche Informationen zu dieser Seite finden Sie unter [Specify Debug Configuration Settings, Create New Project From Existing Code Files Wizard (Einstellungen für Debugkonfiguration angeben, Assistent „Neues Projekt aus vorhandenen Codedateien erstellen“)](../ide/specify-debug-configuration-settings.md). Klicken Sie auf **Weiter** , um fortzufahren.

1. Legen Sie die zu verwendenden Releasekonfigurationseinstellungen fest. Ausführliche Informationen zu dieser Seite finden Sie unter [Specify Release Configuration Settings, Create New Project From Existing Code Files Wizard (Einstellungen für Releasekonfiguration angeben, Assistent „Neues Projekt aus vorhandenen Codedateien erstellen“)](../ide/specify-release-configuration.md). Klicken Sie auf **Fertig stellen**, um das neue Projekt zu generieren.

## <a name="see-also"></a>Siehe auch

[Projektspeicherort und Quelldateien festlegen, Assistent "Neues Projekt aus vorhandenen Codedateien erstellen"](../ide/specify-project-location-and-source-files.md)<br>
[Projekteinstellungen angeben, Assistent "Neues Projekt aus vorhandenen Codedateien erstellen"](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)<br>
[Einstellungen für Debugkonfiguration angeben, Assistent "Neues Projekt aus vorhandenen Codedateien erstellen"](../ide/specify-debug-configuration-settings.md)<br>
[Einstellungen für Releasekonfiguration angeben, Assistent „Neues Projekt aus vorhandenen Codedateien erstellen“](../ide/specify-release-configuration.md)