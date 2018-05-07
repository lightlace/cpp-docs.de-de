---
title: Erstellen eines Makefile-Projekts | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2018
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
ms.openlocfilehash: dc854f96f1c41baf28a5af4ca1f253e47d9a8914
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="creating-a-makefile-project"></a>Erstellen eines Makefile-Projekts

Wenn Sie eine vorhandene Quellcodeprojekt, die Sie über die Befehlszeile mit einem Makefile erstellen verfügen, hat der Visual Studio-Entwicklungsumgebung mehrere Möglichkeiten, wandelt sie in ein Projekt, das vollständige Visual Studio-IDE-Funktionen nutzen kann. Dieser Artikel beschreibt das Erstellen eines Makefile-Projekts in Visual Studio, die Ihre vorhandenen Makefile verwendet wird, um den Code in der IDE erstellen. Alternativ können Sie die **neues Projekt aus vorhandenen Codedateien erstellen** Assistenten zum Erstellen eines systemeigenen MSBuild-Projekts aus dem Quellcode. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines C++-Projekts aus vorhandenem Code](how-to-create-a-cpp-project-from-existing-code.md). Ab Visual Studio 2017, können Sie auch die **Ordner öffnen** -Funktion, die mehrere vorhandene Build Systeme verwenden kann, als wären sie systemeigene Visual Studio-Projekte. Weitere Informationen finden Sie unter [Ordner öffnen-Projekte in Visual C++](non-msbuild-projects.md).

Verwendung von Visual Studio öffnen und den Quellcode mithilfe der vorhandenen Makefile erstellen, erstellen Sie zunächst ein neues Projekt, indem Sie die MakeFile-Projektvorlage auswählen. Ein Assistent können Sie die Befehle und die Umgebung verwendet wird, indem Sie die Makefile angeben. Dieses Projekt können dann um den Code in der Visual Studio-Entwicklungsumgebung zu erstellen.

Standardmäßig werden keine Dateien von Makefile-Projekt im Projektmappen-Explorer angezeigt. Makefile-Projekt gibt die Buildeinstellungen, die auf der Seite der Projekteigenschaften wiedergegeben werden.

Die Ausgabedatei, die Sie im Projekt festlegen, hat keinen Einfluss auf den vom Buildskript erstellten Namen; sie deklariert lediglich die Bestimmung. Makefile noch während des Erstellungsprozesses steuert und gibt an, die Build-Ziele.

## <a name="to-create-a-makefile-project"></a>So erstellen Sie ein Makefile-Projekt

1. Befolgen Sie die Anweisungen im Hilfethema [Erstellen eines Projekts mit einem Visual C++-Anwendungs-Assistenten](../ide/creating-desktop-projects-by-using-application-wizards.md).

1. In der **neues Projekt** Dialogfeld erweitern Sie **Visual C++** > **allgemeine** und wählen Sie dann **Makefile-Projekt** in der Vorlagen (Bereich) auf den Projektassistenten zu öffnen.

1. In der [Anwendungseinstellungen](../ide/application-settings-makefile-project-wizard.md) die Befehlsausgabe bereinigen, außerdem Rebuild-Informationen für die Debug- und im erstellt.

1. Klicken Sie auf **Fertig stellen** um den Assistenten schließen und öffnen Sie das neu erstellte Projekt in **Projektmappen-Explorer**.

Sie können die Projekteigenschaften auf der Eigenschaftenseite des Projekts anzeigen und bearbeiten. Finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../ide/working-with-project-properties.md) Informationen zum Anzeigen der Eigenschaftenseite.

## <a name="see-also"></a>Siehe auch

[Makefile-Projekt-Assistent](../ide/makefile-project-wizard.md)<br/>
[Sonderzeichen in einem Makefile](../build/special-characters-in-a-makefile.md)<br/>
[Inhalt eines Makefiles](../build/contents-of-a-makefile.md)<br/>
