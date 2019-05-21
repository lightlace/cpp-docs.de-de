---
title: Erstellen eines ATL-Projekts
ms.date: 05/06/2019
f1_keywords:
- vc.appwiz.ATL.project
helpviewer_keywords:
- ATL projects, creating
- ATL70.DLL
- _ATL_MIN_CRT macro
- distributing files with ATL components
ms.assetid: 061d5f98-f669-440e-9380-42f017a0f9e8
ms.openlocfilehash: 971d6c05ad4669f32e3b232d5e91c501e197be30
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65707423"
---
# <a name="creating-an-atl-project"></a>Erstellen eines ATL-Projekts

Die einfachste Möglichkeit zum Erstellen eines ATL-Projekts besteht darin, den ATL-Projekt-Assistenten zu verwenden, der sich im **Win32-Projekte**-Ordner des Dialogfelds **Neues Projekt** befindet.

## <a name="to-create-an-atl-project-using-the-atl-project-wizard"></a>So erstellen Sie ein ATL-Projekt mit dem ATL-Projekt-Assistenten

1. Wählen Sie in Visual Studio **Datei > Neu > Projekt** im Hauptmenü aus.

1. Wählen Sie das **ATL-Projekt**-Symbol im Bereich **Vorlagen** aus, um den **ATL-Projekt-Assistenten** zu öffnen.

1. Definieren Sie Ihre Anwendungseinstellungen auf der Seite [Anwendungseinstellungen](../../atl/reference/application-settings-atl-project-wizard.md) des **ATL-Projekt-Assistenten**.

   > [!NOTE]
   > Überspringen Sie diesen Schritt, um die Standardeinstellungen des Assistenten beizubehalten.

1. Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen und das neue Projekt in der Entwicklungsumgebung zu öffnen.

Nachdem das Projekt erstellt wurde, können Sie die generierten Dateien im **Projektmappen-Explorer** anzeigen lassen. Weitere Informationen zu den vom Assistenten erstellten Dateien im Projekt finden Sie in der projekteigenen Datei "Readme.txt". Weitere Informationen zu den Dateitypen finden Sie unter [Für Visual Studio C++-Projekte erstellte Dateitypen](../../build/reference/file-types-created-for-visual-cpp-projects.md). Weitere Informationen zu den Konfigurationen für das neue ATL-Projekt sowie dazu, wie diese geändert werden können, finden Sie unter [Standardmäßige ATL-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md).

## <a name="see-also"></a>Siehe auch

[Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Eigenschaftenseiten](../../build/reference/property-pages-visual-cpp.md)
