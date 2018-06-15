---
title: Erstellen eines Makefile-Projekts | Microsoft-Dokumentation
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
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "33336777"
---
# <a name="creating-a-makefile-project"></a>Erstellen eines Makefile-Projekts

Wenn Sie über ein vorhandenes Quellcodeprojekt verfügen, das Sie mithilfe eines Makefiles über die Befehlszeile erstellt haben, gibt es mit der Visual Studio-Entwicklungsumgebung mehrere Möglichkeiten, es in ein Projekt umzuwandeln, das das vollständige Potenzial der Visual Studio-IDE-Features ausschöpft. In diesem Artikel wird beschrieben, wie Sie ein Makefile-Projekt in Visual Studio erstellen, das Ihr vorhandenes Makefile zum Erstellen des Codes in der IDE verwendet. Alternativ können Sie den Assistenten für das **Erstellen von Projekten aus vorhandenen Codedateien** verwenden, um ein natives MSBuild-Projekt aus dem Quellcode zu erstellen. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines C++-Projekts aus vorhandenem Code](how-to-create-a-cpp-project-from-existing-code.md). Ab Visual Studio 2017 können Sie auch das Feature **Ordner öffnen** verwenden, mit dem mehrere vorhandene Buildsysteme verwendet werden können, als wären sie native Visual Studio-Projekte. Weitere Informationen finden Sie unter [Ordner öffnen-Projekte in Visual C++](non-msbuild-projects.md).

Erstellen Sie zum Verwenden von Visual Studio zum Öffnen und Erstellen Ihres Quellcodes mithilfe des vorhandenen Makefiles zunächst ein neues Projekt, indem Sie die Makefile-Projektvorlage auswählen. Ein Assistent hilft Ihnen beim Festlegen der Befehle und Umgebung, die das Makefile verwendet. Anschließend können Sie dieses Projekt verwenden, um Ihren Code in der Visual Studio-Entwicklungsumgebung zu erstellen.

Das Makefile-Projekt zeigt im Projektmappen-Explorer standardmäßig keine Dateien an. Die Buildeinstellungen, die auf der Eigenschaftenseite des Projekts angezeigt werden, werden vom Makefile-Projekt festgelegt.

Die Ausgabedatei, die Sie im Projekt festlegen, hat keinen Einfluss auf den vom Buildskript erstellten Namen; sie deklariert lediglich die Bestimmung. Ihr Makefile steuert weiterhin den Buildprozess und gibt die Buildziele an.

## <a name="to-create-a-makefile-project"></a>So erstellen Sie ein Makefile-Projekt

1. Führen Sie die Anweisungen im Artikel [Creating a Project with a Visual C++ Application Wizard (Erstellen eines Projekts mit einem Visual C++-Anwendungs-Assistenten)](../ide/creating-desktop-projects-by-using-application-wizards.md) durch.

1. Erweitern Sie **Visual C++** > **Allgemein** im Dialogfeld **Neues Projekt**, und klicken Sie dann im Vorlagenbereich auf **Makefile-Projekt**, um den Projekt-Assistenten zu öffnen.

1. Geben Sie auf der Seite [Anwendungseinstellungen](../ide/application-settings-makefile-project-wizard.md) die Befehls-, Ausgabe-, Bereinigungs- und Neuerstellungsinformationen für die Debug- und Verkaufsversion an.

1. Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen und das neu erstellte Projekt im **Projektmappen-Explorer** zu öffnen.

Sie können die Projekteigenschaften auf der Eigenschaftenseite des Projekts anzeigen und bearbeiten. Weitere Informationen zum Anzeigen der Eigenschaftenseite finden Sie unter [Setting Visual C++ Project Properties (Festlegen von Visual C++-Projekteigenschaften)](../ide/working-with-project-properties.md).

## <a name="see-also"></a>Siehe auch

[Makefile-Projekt-Assistent](../ide/makefile-project-wizard.md)<br/>
[Sonderzeichen in einem Makefile](../build/special-characters-in-a-makefile.md)<br/>
[Inhalt eines Makefiles](../build/contents-of-a-makefile.md)<br/>
