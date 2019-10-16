---
title: 'Gewusst wie: Hinzufügen eines benutzerdefinierten Buildschritts zu MSBuild-Projekten'
ms.date: 10/16/2019
helpviewer_keywords:
- 'msbuild (c++), howto: add a custom build step'
ms.assetid: a20a0c47-4df4-4754-a1f0-a94a99958916
ms.openlocfilehash: 78d40a5b4a02fe9b065bbbdde33afc6180d75381
ms.sourcegitcommit: 9aab425662a66825772f091112986952f341f7c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72444917"
---
# <a name="how-to-add-a-custom-build-step-to-msbuild-projects"></a>Gewusst wie: Hinzufügen eines benutzerdefinierten Buildschritts zu MSBuild-Projekten

Ein benutzerdefinierter Buildschritt ist ein benutzerdefinierter Schritt in einem Build. Ein benutzerdefinierter Buildschritt verhält sich wie jeder andere *Befehls Tool* Schritt, z. b. der Standard Schritt Kompilierungs-oder Link Tool.

Geben Sie einen benutzerdefinierten Buildschritt in der Projektdatei (. vcxproj) an. Mit diesem Schritt können Sie eine auszuführende Befehlszeile, zusätzliche Eingabe-oder Ausgabedateien und eine anzuzeigende Meldung angeben. Wenn **MSBuild** feststellt, dass Ihre Ausgabedateien hinsichtlich der Eingabedateien veraltet sind, wird die Meldung angezeigt, und der Befehl wird ausgeführt.

Um den Speicherort des benutzerdefinierten Buildschritts in der Sequenz von Buildzielen anzugeben, verwenden Sie eines oder beide der XML-Elemente `CustomBuildAfterTargets` und `CustomBuildBeforeTargets` in der Projektdatei. Beispielsweise können Sie angeben, dass der benutzerdefinierte Buildschritt nach dem Ziel des Verknüpfungs Tools und vor dem Manifest-Tool Ziel ausgeführt wird. Der tatsächliche Satz verfügbarer Ziele hängt von Ihrem speziellen Build ab.

Geben Sie das `CustomBuildBeforeTargets`-Element an, um den benutzerdefinierten Buildschritt auszuführen, bevor ein bestimmtes Ziel ausgeführt wird, das `CustomBuildAfterTargets`-Element, um den Schritt nach dem Ausführen eines bestimmten Ziels auszuführen, oder beide Elemente, um den Schritt zwischen zwei angrenzenden Zielen auszuführen. Wenn keines der Elemente angegeben ist, wird das benutzerdefinierte Buildtool an seinem Standard Speicherort ausgeführt **, der sich** nach dem Verknüpfungs Ziel befindet.

Benutzerdefinierte Buildschritte und benutzerdefinierte Buildtools verwenden die in den XML-Elementen `CustomBuildBeforeTargets` und `CustomBuildAfterTargets` angegebenen Informationen gemeinsam. Geben Sie diese Ziele daher nur einmal in der Projektdatei an.

### <a name="to-define-what-is-executed-by-the-custom-build-step"></a>So definieren Sie, was durch den benutzerdefinierten Buildschritt ausgeführt wird

1. Fügen Sie der Projektdatei eine Eigenschaften Gruppe hinzu. Geben Sie in dieser Eigenschaften Gruppe den Befehl, seine Eingaben und Ausgaben sowie eine Meldung an, wie im folgenden Beispiel gezeigt. In diesem Beispiel wird eine CAB-Datei aus der Datei "Main. cpp" erstellt, die Sie in Exemplarische Vorgehensweise [: Verwenden von MSBuild zum Erstellen C++ eines Projekts](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)erstellt haben.

    ```
    <ItemDefinitionGroup>
      <CustomBuildStep>
        <Command>makecab.exe $(ProjectDir)main.cpp $(TargetName).cab</Command>
        <Outputs>$(TargetName).cab</Outputs>
        <Inputs>$(ProjectDir)main.cpp</Inputs>
      </CustomBuildStep>
    </ItemDefinitionGroup>
    ```

### <a name="to-define-where-in-the-build-the-custom-build-step-will-execute"></a>So definieren Sie, wo der benutzerdefinierte Buildschritt im Build ausgeführt wird

1. Fügen Sie der Projektdatei die folgende Eigenschaften Gruppe hinzu. Sie können beide Ziele angeben, oder Sie können einen Wert weglassen, wenn Sie nur den benutzerdefinierten Schritt vor oder nach einem bestimmten Ziel ausführen möchten. Dieses Beispiel weist **MSBuild** an, den benutzerdefinierten Schritt nach dem Kompilierungs Schritt, jedoch vor dem Link Schritt auszuführen.

    ```
    <PropertyGroup>
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>
    </PropertyGroup>
    ```

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweise: Verwenden von MSBuild C++ zum Erstellen eines Projekts](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)<br/>
[Vorgehensweise: Verwenden von Buildereignissen in MSBuild-Projekten](how-to-use-build-events-in-msbuild-projects.md)<br/>
[Vorgehensweise: Hinzufügen von benutzerdefinierten Buildtools zu MSBuild-Projekten](how-to-add-custom-build-tools-to-msbuild-projects.md)
