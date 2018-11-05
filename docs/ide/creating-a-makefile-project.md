---
title: Erstellen eines C++ Makefile-Projekts | Microsoft Docs
ms.custom: ''
ms.date: 10/19/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.makefile.project
dev_langs:
- C++
helpviewer_keywords:
- Makefile projects, creating
- project files [C++], Makefile projects
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5f937c11b2453bd296468c5f153b7c9495eba290
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990242"
---
# <a name="creating-a-c-makefile-project"></a>Erstellen eines C++-Makefile-Projekts

Ein *Makefile* ist eine Textdatei, die Anweisungen zum Kompilieren und Linken (oder *Erstellen*) einer Reihe von C++-Quellcodedateien enthält. Ein *Make*-Programm liest das Makefile und ruft einen Compiler, einen Linker und möglicherweise auch andere Programme auf, um eine ausführbare Datei zu erstellen. Microsofts Implementierung des *Make*-Programms heißt **NMAKE**. (Visual Studio verwendet standardmäßig das MSBuild-System, das auf VCXPROJ-Dateien basiert und über **Datei > Neu > Projekt** Dateien erstellt wird.)

Wenn Sie über ein vorhandenes Makefile-Projekt verfügen, können Sie folgende Optionen auswählen, wenn Sie es in der Visual Studio-IDE codieren und/oder debuggen möchten:

- Erstellen eines Makefile-Projekts in Visual Studio, das Ihr vorhandenes Makefile zum Erstellen des Codes in der IDE verwendet. (Sie verfügen nicht über alle IDE-Funktionen, die Sie mit einem nativen MSBuild-Projekt erhalten.) Siehe [So erstellen Sie ein Makefile-Projekt](#create_a_makefile_project) weiter unten.
- Verwenden des Assistenten für das **Erstellen von Projekten aus vorhandenen Codedateien**, um ein natives MSBuild-Projekt aus dem Quellcode zu erstellen. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines C++-Projekts aus vorhandenem Code](how-to-create-a-cpp-project-from-existing-code.md).
- **Visual Studio 2017 und höher:** Verwenden des Features **Ordner öffnen**, um ein Makefile-Projekt zu öffnen, ohne es zu MSBuild zu konvertieren. Weitere Informationen finden Sie unter [Ordner öffnen-Projekte in Visual C++](non-msbuild-projects.md).

## <a name="a-namecreateamakefileproject-to-create-a-makefile-project-with-the-makefile-project-template"></a><a name="create_a_makefile_project"> So erstellen Sie ein Makefile-Projekt mit der Makefile-Projektvorlage

In Visual Studio 2017 oder höher ist die Makefile-Projektvorlage verfügbar, wenn die Workload C++-Desktopentwicklung installiert ist.

Folgen Sie dem Assistenten, der Sie beim Festlegen der Befehle und der Umgebung unterstützt, die das Makefile verwendet. Anschließend können Sie dieses Projekt verwenden, um Ihren Code in der Visual Studio-Entwicklungsumgebung zu erstellen.

Das Makefile-Projekt zeigt im Projektmappen-Explorer standardmäßig keine Dateien an. Die Buildeinstellungen, die auf der Eigenschaftenseite des Projekts angezeigt werden, werden vom Makefile-Projekt festgelegt.

Die Ausgabedatei, die Sie im Projekt festlegen, hat keinen Einfluss auf den vom Buildskript erstellten Namen; sie deklariert lediglich die Bestimmung. Ihr Makefile steuert weiterhin den Buildprozess und gibt die Buildziele an.

1. Geben Sie auf der Visual Studio-Startseite „makefile“ in das Suchfeld **Neues Projekt** ein. Sie können auch **Visual C++** > **Allgemein** (Visual Studio 2015) oder **Andere** (Visual Studio 2017) im Dialogfeld **Neues Projekt** erweitern und dann im Vorlagenbereich auf **Makefile-Projekt** klicken, um den Projekt-Assistenten zu öffnen.

1. Geben Sie auf der Seite [Anwendungseinstellungen](../ide/application-settings-makefile-project-wizard.md) die Befehls-, Ausgabe-, Bereinigungs- und Neuerstellungsinformationen für die Debug- und Verkaufsversion an.

1. Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen und das neu erstellte Projekt im **Projektmappen-Explorer** zu öffnen.

Sie können die Projekteigenschaften auf der Eigenschaftenseite des Projekts anzeigen und bearbeiten. Weitere Informationen zum Anzeigen der Eigenschaftenseite finden Sie unter [Setting Visual C++ Project Properties (Festlegen von Visual C++-Projekteigenschaften)](../ide/working-with-project-properties.md).

## <a name="see-also"></a>Siehe auch

[Makefile-Projekt-Assistent](../ide/makefile-project-wizard.md)<br/>
[Sonderzeichen in einem Makefile](../build/special-characters-in-a-makefile.md)<br/>
[Inhalt eines Makefiles](../build/contents-of-a-makefile.md)<br/>
