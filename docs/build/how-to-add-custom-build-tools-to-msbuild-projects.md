---
title: 'Vorgehensweise: Hinzufügen von benutzerdefinierten Buildtools zu MSBuild-Projekten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.howto.addcustombuildtools
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: add custom build tools'
ms.assetid: de03899a-371d-4396-9bf9-34f45a65e909
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e06a2a545862c0fa9cfdcf6311334ecc86de2bf
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714401"
---
# <a name="how-to-add-custom-build-tools-to-msbuild-projects"></a>Gewusst wie: Hinzufügen von benutzerdefinierten Buildtools zu MSBuild-Projekten

Ein benutzerdefiniertes Buildtool ist eine benutzerdefinierte Befehlszeilentool, das eine bestimmte Datei zugeordnet ist.

Geben Sie für eine bestimmte Datei in der Projektdatei (.vcxproj), die über die Befehlszeile ausführen "," alle weiteren anregungen mit "oder" Ausgabedateien "und" eine anzuzeigende Meldung. Wenn **MSBuild** feststellt, dass Ihre Ausgabedateien in Bezug auf Ihre Eingabedateien veraltet sind, wird die Meldung angezeigt und das Befehlszeilentool wird ausgeführt.

Um anzugeben, wenn das benutzerdefinierte Buildtool ausgeführt wird, verwenden Sie eine oder beide der `CustomBuildBeforeTargets` und `CustomBuildAfterTargets` XML-Elemente in der Projektdatei. Beispielsweise können Sie angeben, dass das benutzerdefinierte Buildtool ausgeführt werden, nach der MIDL-Compiler und vor der C/C++-Compiler. Geben Sie die `CustomBuildBeforeTargets` Element, das Tool ausführen, bevor ein bestimmtes Ziel ausgeführt wird; die `CustomBuildAfterTargets` Element, das Tool nach einem bestimmten Ziel, ausführen oder beide Elemente zum Ausführen des Tools zwischen der Ausführung von zwei Zielen. Wenn keines der Elemente angegeben wird, führt das benutzerdefinierte Buildtool an seinem Standardspeicherort, d. h. vor den **MIDL** Ziel.

Benutzerdefinierte Buildschritte und benutzerdefinierte Tools freigeben in angegebene Informationen die `CustomBuildBeforeTargets` und `CustomBuildAfterTargets` XML-Elemente. Geben Sie diese Ziele einmal in Ihrer Projektdatei hinzu.

### <a name="to-add-a-custom-build-tool"></a>Ein benutzerdefiniertes Buildtool hinzufügen

1. Fügen Sie eine Elementgruppe in die Projektdatei aus, und fügen Sie ein Element für jede Eingabedatei. Geben Sie den Befehl, zusätzlicher Eingaben, Ausgaben und eine Nachricht als Elementmetadaten, ein, wie hier gezeigt. In diesem Beispiel wird davon ausgegangen, dass eine Datei "faq.txt" im selben Verzeichnis wie Ihr Projekt vorhanden ist.

    ```
    <ItemGroup>
      <CustomBuild Include="faq.txt">
        <Message>Copying readme...</Message>
        <Command>copy %(Identity) $(OutDir)%(Identity)</Command>
        <Outputs>$(OutDir)%(Identity)</Outputs>
      </CustomBuild>
    </ItemGroup>
    ```

### <a name="to-define-where-in-the-build-the-custom-build-tools-will-execute"></a>Um zu definieren, in dem in den Build den benutzerdefinierten Buildtools ausgeführt wird.

1. Fügen Sie die folgende Eigenschaftengruppe zur Projektdatei hinzu. Sie müssen mindestens eines der Ziele angeben, jedoch können Sie die anderen weglassen, wenn Sie nur Buildschritt führen Sie vor dem (oder nach) interessiert sind ein bestimmtes Ziel. In diesem Beispiel führt die benutzerdefinierten Schritt nach dem Kompilieren, aber vor dem verknüpfen.

    ```
    <PropertyGroup>
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>
    </PropertyGroup>
    ```

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweise: Verwenden von MSBuild zum Erstellen eines Visual C++-Projekts](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)<br/>
[Vorgehensweise: Verwenden von Buildereignissen in MSBuild-Projekten](../build/how-to-use-build-events-in-msbuild-projects.md)<br/>
[Vorgehensweise: Hinzufügen eines benutzerdefinierten Buildschritts zu MSBuild-Projekten](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)