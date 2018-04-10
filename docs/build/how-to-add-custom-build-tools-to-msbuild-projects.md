---
title: 'Vorgehensweise: Hinzufügen von benutzerdefinierten Buildtools zu MSBuild-Projekten | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- msbuild.cpp.howto.addcustombuildtools
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: add custom build tools'
ms.assetid: de03899a-371d-4396-9bf9-34f45a65e909
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: efa484e4ad57a3a1f27621e16dddcf90135b7057
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-add-custom-build-tools-to-msbuild-projects"></a>Gewusst wie: Hinzufügen von benutzerdefinierten Buildtools zu MSBuild-Projekten
Ein benutzerdefiniertes Buildtool ist ein benutzerdefiniertes, Befehlszeilen-Tool, das eine bestimmte Datei zugeordnet ist.  
  
 Geben Sie für eine bestimmte Datei in der Projektdatei (.vcxproj), die über die Befehlszeile ausführen, beliebige zusätzliche Eingabe- oder Ausgabedateien und eine anzuzeigende Meldung. Wenn **MSBuild** bestimmt die Ausgabedateien im Hinblick auf Ihre Eingabedateien veraltet sind, wird die Meldung und führt das Befehlszeilentool "".  
  
 Um anzugeben, wann das benutzerdefinierte Buildtool ausgeführt wird, verwenden Sie eine oder beide der `CustomBuildBeforeTargets` und `CustomBuildAfterTargets` XML-Elemente in der Projektdatei. Beispielsweise können Sie angeben, dass Ihr benutzerdefiniertes Buildtool nach dem MIDL-Compiler und vor dem C/C++-Compiler ausgeführt. Geben Sie die `CustomBuildBeforeTargets` Element, das Tool ausführen, bevor ein bestimmtes Ziel ausgeführt wird; die `CustomBuildAfterTargets` Element zum Ausführen des Tools nach einem bestimmten Ziel; oder beide Elemente, um das Tool zwischen der Ausführung von zwei Zielen ausführen. Wenn keines der Elemente angegeben wird, führt Ihr benutzerdefiniertes Buildtool an seinem Standardspeicherort, d. h. vor der **"MIDL"** Ziel.  
  
 Benutzerdefinierte Buildschritte und benutzerdefinierten Buildtools gemeinsam nutzen die Angaben der `CustomBuildBeforeTargets` und `CustomBuildAfterTargets` XML-Elemente. Diese Ziele einmal in der Projektdatei angeben.  
  
### <a name="to-add-a-custom-build-tool"></a>So fügen Sie ein benutzerdefiniertes Buildtool hinzu  
  
1.  Die Projektdatei eine Elementgruppe hinzu, und fügen Sie ein Element für jede Eingabedatei hinzu. Geben Sie den Befehl, zusätzliche Eingaben, Ausgaben und eine Meldung als Elementmetadaten, wie hier gezeigt. In diesem Beispiel wird davon ausgegangen, dass eine Datei "faq.txt" im gleichen Verzeichnis wie das Projekt vorhanden ist.  
  
    ```  
    <ItemGroup>  
      <CustomBuild Include="faq.txt">  
        <Message>Copying readme...</Message>  
        <Command>copy %(Identity) $(OutDir)%(Identity)</Command>  
        <Outputs>$(OutDir)%(Identity)</Outputs>  
      </CustomBuild>  
    </ItemGroup>  
    ```  
  
### <a name="to-define-where-in-the-build-the-custom-build-tools-will-execute"></a>Um zu definieren, in denen in den Build der benutzerdefinierten Buildtools ausgeführt wird.  
  
1.  Fügen Sie der Projektdatei die folgende Eigenschaftengruppe hinzu. Müssen Sie mindestens eines der Ziele angeben, aber Sie können die anderen weglassen, wenn Sie nur interessiert, dass der Buildschritt vor (oder nach) ausgeführt werden ein bestimmtes Ziel. In diesem Beispiel führt die benutzerdefinierten Schritt nach dem Kompilieren, aber vor dem verknüpfen.  
  
    ```  
    <PropertyGroup>  
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>  
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>  
    </PropertyGroup>  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Verwenden von MSBuild zum Erstellen eines Visual C++-Projekts](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)   
 [Vorgehensweise: Verwenden von Buildereignissen in MSBuild-Projekten](../build/how-to-use-build-events-in-msbuild-projects.md)   
 [Vorgehensweise: Hinzufügen eines benutzerdefinierten Buildschritts zu MSBuild-Projekten](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)