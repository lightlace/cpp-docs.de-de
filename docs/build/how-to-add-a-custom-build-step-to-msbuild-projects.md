---
title: "Vorgehensweise: Hinzufügen ein benutzerdefinierten Buildschritts zu MSBuild-Projekten | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: msbuild.cpp.howto.addcustombuildstep
dev_langs: C++
helpviewer_keywords: 'msbuild (c++), howto: add a custom build step'
ms.assetid: a20a0c47-4df4-4754-a1f0-a94a99958916
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d664b9fad6a9ec67dc009a90171119036dc13cde
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-add-a-custom-build-step-to-msbuild-projects"></a>Gewusst wie: Hinzufügen eines benutzerdefinierten Buildschritts zu MSBuild-Projekten
Ein benutzerdefinierten Buildschritt abmeldeanforderungen einen benutzerdefinierten Schritt in einem build Ein benutzerdefinierter Buildschritt verhält sich wie jeder andere *Befehlstool* Schritt, wie z. B. der standard Kompilier- oder Tool Schritt.  
  
 Geben Sie einen benutzerdefinierten Buildschritt in der Projektdatei (.vcxproj). Der Schritt kann über die Befehlszeile ausgeführt wird, eine zusätzliche Eingabe oder Ausgabedateien und eine anzuzeigende Meldung angegeben werden. Wenn **MSBuild** bestimmt die Ausgabedateien im Hinblick auf Ihre Eingabedateien veraltet sind, wird die Meldung und führt den Befehl.  
  
 Verwenden, um anzugeben, der Speicherort der benutzerdefinierten Buildschritts Schritt in der Reihenfolge der Build-Ziele einer oder beider der `CustomBuildAfterTargets` und `CustomBuildBeforeTargets` XML-Elemente in der Projektdatei. Beispielsweise können Sie angeben, dass der benutzerdefinierte Buildschritt nach dem Link-Tool-Ziel und vor dem Manifesttool-Ziel ausgeführt wird. Der eigentliche Satz verfügbarer Ziele hängt von der bestimmten Build.  
  
 Geben Sie die `CustomBuildBeforeTargets` Element benutzerdefinierten Buildschritt auszuführende, bevor ein bestimmtes Ziel ausgeführt wird, die `CustomBuildAfterTargets` Element an den Schritt ausgeführt werden, nachdem ein bestimmtes Ziel ausgeführt wird, oder beide Elemente, um den Schritt zwischen zwei benachbarten Zielen ausführen. Wenn keines der Elemente angegeben wird, führt Ihr benutzerdefiniertes Buildtool an seinem Standardspeicherort, d. h. nach der **Link** Ziel.  
  
 Benutzerdefinierte Buildschritte und benutzerdefinierten Buildtools gemeinsam nutzen die Angaben der `CustomBuildBeforeTargets` und `CustomBuildAfterTargets` XML-Elemente. Diese Ziele werden daher nur einmal in der Projektdatei angeben.  
  
### <a name="to-define-what-is-executed-by-the-custom-build-step"></a>Zum definieren, was vom benutzerdefinierten Buildschritt ausgeführt wird  
  
1.  Fügen Sie der Projektdatei eine Eigenschaftengruppe hinzu. Geben Sie in dieser Eigenschaftengruppe den Befehl, Eingaben und Ausgaben und eine Meldung wie im folgenden Beispiel gezeigt. In diesem Beispiel erstellt eine CAB-Datei aus der "Main.cpp"-Datei, die Sie erstellt, im haben [Exemplarische Vorgehensweise: Verwenden von MSBuild zum Erstellen eines Visual C++-Projekts](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md).  
  
    ```  
    <ItemDefinitionGroup>  
      <CustomBuildStep>  
        <Command>makecab.exe $(ProjectDir)main.cpp $(TargetName).cab</Command>  
        <Outputs>$(TargetName).cab</Outputs>  
        <Inputs>$(TargetFileName)</Inputs>  
      </CustomBuildStep>  
    </ItemDefinitionGroup>  
    ```  
  
### <a name="to-define-where-in-the-build-the-custom-build-step-will-execute"></a>Um zu definieren, in denen in den Build der benutzerdefinierte Buildschritt ausgeführt wird.  
  
1.  Fügen Sie der Projektdatei die folgende Eigenschaftengruppe hinzu. Sie können beide Ziele angeben, oder können Sie eine weglassen, wenn nur den benutzerdefinierten Schritt vor oder nach einem bestimmten Ziel ausgeführt werden sollen. In diesem Beispiel weist **MSBuild** , den benutzerdefinierten Schritt nach der Kompilierung, jedoch vor dem Linkschritt auszuführen.  
  
    ```  
    <PropertyGroup>  
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>  
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>  
    </PropertyGroup>  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Verwenden von MSBuild zum Erstellen eines Visual C++-Projekts](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)   
 [Vorgehensweise: Verwenden von Buildereignissen in MSBuild-Projekten](../build/how-to-use-build-events-in-msbuild-projects.md)   
 [Vorgehensweise: Hinzufügen von benutzerdefinierten Buildtools zu MSBuild-Projekten](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)