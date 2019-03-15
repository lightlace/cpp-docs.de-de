---
title: Visual Studio Projects - C++
ms.date: 12/12/2018
f1_keywords:
- vcprojects
- creatingmanagingVC
helpviewer_keywords:
- ATL projects, creating
- Visual C++ projects, creating
- projects [C++], creating
- Visual C++ projects
- ATL projects
ms.assetid: 11003cd8-9046-4630-a189-a32bf3b88047
ms.openlocfilehash: b5fb9ac87547578f101676d4cf424c7065155842
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825542"
---
# <a name="visual-studio-projects---c"></a>Visual Studio-Projekte – C++

Ein *Visual Studio-Projekt* basiert ein Projekt auf das MSBuild-Build-System. MSBuild ist das systemeigene Buildsystem für Visual Studio und ist im Allgemeinen, dass die beste Buildsystem für UWP-apps als auch Desktop-Anwendungen, die MFC- oder ATL-Bibliotheken, COM-Komponenten und anderen Windows-spezifische Programme verwenden. MSBuild ist eng in Visual Studio integriert, aber Sie können es auch über die Befehlszeile verwenden. 

## <a name="create-a-project"></a>Erstellen eines Projekts

Sie können C++-Projekte erstellen, indem Sie die Auswahl **Datei &#124; neu &#124; Projekt**, und klicken Sie dann Visual C++ im linken Bereich auswählen. Im mittleren Bereich sehen Sie eine Liste der Projektvorlagen das Projekt aus: 

   ![Projektvorlagen](../media/vs2017-new-project.png "Visual Studio 2017-Dialogfeld „Neues Projekt“")

Weitere Informationen zu allen Standard-Projektvorlagen, die in Visual Studio enthalten sind, finden Sie unter [C++-Projektvorlagen in Visual Studio](reference/visual-cpp-project-types.md). Sie können eigene Projektvorlagen erstellen. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Projektvorlagen](/visualstudio/ide/how-to-create-project-templates).

Nachdem Sie ein Projekt erstellen, wird Sie der [Projektmappen-Explorer](/visualstudio/ide/solutions-and-projects-in-visual-studio) Fenster:

   ![Projektmappen-Explorer](media/mathlibrary-solution-explorer-153.png)

Wenn Sie ein neues Projekt erstellen, wird auch eine Projektmappendatei (sln) erstellt. Sie können zusätzliche Projekte der Projektmappe hinzufügen, indem Sie mit der rechten Maustaste auf diese im **Projektmappen-Explorer**. Die Projektmappendatei wird verwendet, Buildabhängigkeiten zu koordinieren, wenn Sie mehrere verwandte Projekte sich nicht viel mehr. Alle Compileroptionen werden auf Projektebene festgelegt.

## <a name="add-items"></a>Hinzufügen von Elementen

Quellcodedateien, Symbole oder andere Elemente Ihrem Projekt hinzufügen, indem Sie mit der rechten Maustaste auf das Projekt im **Projektmappen-Explorer** und **hinzufügen > New** oder **hinzufügen > vorhandenes**.

## <a name="add-third-party-libraries"></a>Hinzufügen von Bibliotheken von Drittanbietern

Verwenden Sie zum Hinzufügen von Drittanbieterbibliotheken der [Vcpkg](../vcpkg.md) -Paket-Manager. Führen Sie die Visual Studio-integrationsschritt richten Sie die Pfade zu dieser Bibliothek, wenn Sie es aus einem beliebigen Visual Studio-Projekt verweisen. 

## <a name="set-compiler-options-and-other-build-properties"></a>Festlegen von Compileroptionen und andere Buildeigenschaften

Zum Konfigurieren von Buildeinstellungen für ein Projekt mit der Maustaste, auf das Projekt im **Projektmappen-Explorer** , und wählen Sie **Eigenschaften**. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](working-with-project-properties.md).

## <a name="compile-and-run"></a>Kompilieren und ausführen

Zum Kompilieren, und führen Sie das neue Projekt ein, drücken Sie die **F5** oder klicken Sie auf die *debug-Dropdownliste* mit dem grünen Pfeil auf der Hauptsymbolleiste. Die *Dropdownliste "Konfiguration"* ist, in dem Sie, ob bei der ein *Debuggen* oder *Version* Build (oder eine andere benutzerdefinierte Konfiguration verwenden).

Ein neues Projekt wird ohne Fehler kompiliert. Wenn Sie Ihren eigenen Code hinzufügen, können Sie gelegentlich einen Fehler verursachen oder eine Warnung ausgelöst. Ein Fehler wird verhindert, dass den Build abgeschlossen; eine Warnung wird nicht verwendet. Alle Fehler und Warnungen werden angezeigt, bei der Erstellung des Projekts in das Fenster "Ausgabe" sowohl in der Fehlerliste. 

   ![Liste von Ausgabe-Fenster und Fehler](../media/vs2017-output-error-list.png)

Sie können in der Fehlerliste drücken **F1** auf einen hervorgehobenen Fehler, um die Dokumentationsthema anzuzeigen.

## <a name="in-this-section"></a>In diesem Abschnitt

[Festlegen von C++-Compiler und erstellen Sie die Eigenschaften in Visual Studio](working-with-project-properties.md)<br/>
Gewusst wie Eigenschaftenseiten und Eigenschaftenblätter verwenden, um Ihre projekteinstellungen festzulegen.

[Reference-Bibliotheken und Komponenten zum Zeitpunkt der Erstellung](adding-references-in-visual-cpp-projects.md)<br/>
Informationen zum Einschließen von Bibliotheken, DLL-Dateien, COM- und -Komponenten in einem Projekt.
 
[Organisieren von Projektausgabedateien](how-to-organize-project-output-files-for-builds.md)<br/>
So passen Sie den Speicherort der ausführbaren Dateien im Buildprozess erstellt werden.

[Benutzerdefinierte Buildschritte und Buildereignisse](understanding-custom-build-steps-and-build-events.md)<br/>
Das Hinzufügen von beliebigen Befehl für den Buildprozess an bestimmten Punkten.

[Erstellen eines Projekts aus vorhandenem Code](how-to-create-a-cpp-project-from-existing-code.md)<br/>
Vorgehensweise: Erstellen Sie ein neues Visual Studio-Projekt aus einer losen Auflistung von Quelldateien.

## <a name="see-also"></a>Siehe auch

[Projekte und Buildsysteme](projects-and-build-systems-cpp.md)<br>
