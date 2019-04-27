---
title: 'Vorgehensweise: Hinzufügen eines benutzerdefinierten Buildschritts zu MSBuild-Projekten'
ms.date: 11/04/2016
f1_keywords:
- msbuild.cpp.howto.addcustombuildstep
helpviewer_keywords:
- 'msbuild (c++), howto: add a custom build step'
ms.assetid: a20a0c47-4df4-4754-a1f0-a94a99958916
ms.openlocfilehash: 4c64c6875d82000d6a0ac880b103b5e220015cb3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188924"
---
# <a name="how-to-add-a-custom-build-step-to-msbuild-projects"></a>Vorgehensweise: Hinzufügen eines benutzerdefinierten Buildschritts zu MSBuild-Projekten

Ein benutzerdefinierter Buildschritt wird einen benutzerdefinierten Schritt in einem Build an. Ein benutzerdefinierter Buildschritt verhält sich wie jede andere *-Befehlstool* Schritt, wie z. B. der standard Kompilier- oder Tool Schritt.

Geben Sie einen benutzerdefinierten Buildschritt in der Projektdatei (.vcxproj). Der Schritt kann eine Befehlszeile ausgeführt werden, eine zusätzliche Eingabe oder Ausgabedateien und eine anzuzeigende Meldung angeben. Wenn **MSBuild** feststellt, dass Ihre Ausgabedateien in Bezug auf Ihre Eingabedateien veraltet sind, wird die Meldung angezeigt und führt den Befehl.

Um anzugeben, der Speicherort der benutzerdefinierten Buildschritts Schritt in der Reihenfolge der Buildzielen, verwenden Sie eine oder beide der der `CustomBuildAfterTargets` und `CustomBuildBeforeTargets` XML-Elemente in der Projektdatei. Sie können z. B. angeben, dass der benutzerdefinierte Buildschritt ausgeführt, nach dem Link-Tool-Ziel und vor dem Manifesttool-Ziel wird. Der eigentliche Satz von verfügbaren Ziele hängt vom jeweiligen Build ab.

Geben Sie die `CustomBuildBeforeTargets` Element, das der benutzerdefinierte Buildschritt ausgeführt werden, bevor ein bestimmtes Ziel ausgeführt wird, die `CustomBuildAfterTargets` Element den Schritt ausführen, nachdem ein bestimmtes Ziel ausgeführt oder beide Elemente, um den Schritt zwischen zwei benachbarten Zielen ausführen. Wenn keines der Elemente angegeben wird, führt das benutzerdefinierte Buildtool an seinem Standardspeicherort, also nach der **Link** Ziel.

Benutzerdefinierte Buildschritte und benutzerdefinierte Tools freigeben in angegebene Informationen die `CustomBuildBeforeTargets` und `CustomBuildAfterTargets` XML-Elemente. Diese Ziele werden daher nur einmal in der Projektdatei angeben.

### <a name="to-define-what-is-executed-by-the-custom-build-step"></a>Zum definieren, was von der benutzerdefinierte Buildschritt ausgeführt wird

1. Fügen Sie eine Eigenschaftengruppe zur Projektdatei hinzu. Geben Sie in dieser Eigenschaftengruppe den Befehl, der Eingaben und Ausgaben und eine Nachricht, wie im folgenden Beispiel gezeigt. In diesem Beispiel erstellt eine CAB-Datei aus der "Main.cpp"-Datei, die Sie erstellt, im haben [Exemplarische Vorgehensweise: Verwenden von MSBuild zum Erstellen eines Visual C++-Projekts](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md).

    ```
    <ItemDefinitionGroup>
      <CustomBuildStep>
        <Command>makecab.exe $(ProjectDir)main.cpp $(TargetName).cab</Command>
        <Outputs>$(TargetName).cab</Outputs>
        <Inputs>$(TargetFileName)</Inputs>
      </CustomBuildStep>
    </ItemDefinitionGroup>
    ```

### <a name="to-define-where-in-the-build-the-custom-build-step-will-execute"></a>Um zu definieren, in dem in den Build der benutzerdefinierte Buildschritt ausgeführt wird.

1. Fügen Sie die folgende Eigenschaftengruppe zur Projektdatei hinzu. Sie können beide Ziele angeben, oder können Sie eine weglassen, wenn Sie lediglich die benutzerdefinierten Schritt zum Ausführen vor oder nach einem bestimmten Ziel möchten. In diesem Beispiel weist **MSBuild** , die benutzerdefinierten Schritt nach dem Kompilieren, jedoch vor dem Linkschritt auszuführen.

    ```
    <PropertyGroup>
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>
    </PropertyGroup>
    ```

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweise: Verwenden von MSBuild zum Erstellen eines Visual C++-Projekts](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)<br/>
[Vorgehensweise: Verwenden von Buildereignissen in MSBuild-Projekten](how-to-use-build-events-in-msbuild-projects.md)<br/>
[Vorgehensweise: Hinzufügen von benutzerdefinierten Buildtools zu MSBuild-Projekten](how-to-add-custom-build-tools-to-msbuild-projects.md)
