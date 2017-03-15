---
title: "Gewusst wie: Hinzuf&#252;gen eines benutzerdefinierten Buildschritts zu MSBuild-Projekten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "msbuild.cpp.howto.addcustombuildstep"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MSBuild (C++), Gewusst wie: Hinzufügen eines benutzerdefinierten Buildschritts"
ms.assetid: a20a0c47-4df4-4754-a1f0-a94a99958916
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Gewusst wie: Hinzuf&#252;gen eines benutzerdefinierten Buildschritts zu MSBuild-Projekten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein benutzerdefinierter Buildschritt ist ein benutzerdefinierter Schritt in einem Build.  Ein benutzerdefinierter Buildschritt verhält sich wie ein beliebiger anderer Schritt in einem *Befehlstool*, z. B. wie der standardmäßige Schritt für Kompilier\- oder Linktools.  
  
 Geben Sie einen benutzerdefinierten Buildschritt in der Projektdatei \(VCXPROJ\-Datei\) an.  In diesem Schritt können eine auszuführende Befehlszeile, beliebige zusätzliche Eingabe\- oder Ausgabedateien und eine anzuzeigende Meldung angegeben werden.  Wenn von **MSBuild** bestimmt wird, dass die Ausgabedateien hinsichtlich der Eingabedateien veraltet sind, wird die Meldung angezeigt und der Befehl ausgeführt.  
  
 Verwenden Sie entweder das `CustomBuildAfterTargets`\-XML\-Element oder das `CustomBuildBeforeTargets`\-XML\-Element in der Projektdatei oder beide Elemente, um den Speicherort des benutzerdefinierten Buildschritts in der Sequenz der Buildziele anzugeben.  Sie können z. B. angeben, dass der benutzerdefinierte Buildschritt nach dem Linktoolziel und vor dem Manifesttoolziel ausgeführt wird.  Der tatsächliche Satz verfügbarer Ziele ist vom jeweiligen Build abhängig.  
  
 Geben Sie Folgendes an: das `CustomBuildBeforeTargets`\-Element, um den benutzerdefinierten Buildschritt auszuführen, bevor ein bestimmtes Ziel ausgeführt wird, das `CustomBuildAfterTargets`\-Element, um den Schritt auszuführen, nachdem ein bestimmtes Ziel ausgeführt wurde, oder beide Elemente, um den Schritt zwischen zwei benachbarten Zielen auszuführen.  Wenn keines der Elemente angegeben wird, wird das benutzerdefinierte Buildtool an seinem Standardspeicherort ausgeführt, der hinter dem **Link**\-Ziel liegt.  
  
 Für benutzerdefinierte Buildschritte und Buildtools werden die im `CustomBuildBeforeTargets`\-XML\-Element und im `CustomBuildAfterTargets`\-XML\-Element angegebenen Informationen freigegeben.  Geben Sie diese Ziele daher nur einmal in der Projektdatei an.  
  
### So definieren Sie, welche Schritte im benutzerdefinierten Buildschritt ausgeführt werden  
  
1.  Fügen Sie der Projektdatei eine Eigenschaftengruppe hinzu.  Geben Sie in dieser Eigenschaftengruppe den Befehl, seine Eingaben und Ausgaben und eine Meldung an \(siehe folgendes Beispiel\).  In diesem Beispiel wird eine CAB\-Datei aus der Datei "main.cpp" erstellt, die Sie in [Exemplarische Vorgehensweise: Verwenden von MSBuild zum Erstellen eines Visual C\+\+\-Projekts](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md) erstellt haben.  
  
    ```  
    <ItemDefinitionGroup>  
      <CustomBuildStep>  
        <Command>makecab.exe $(ProjectDir)main.cpp $(TargetName).cab</Command>  
        <Outputs>$(TargetName).cab</Outputs>  
        <Inputs>$(TargetFileName)</Inputs>  
      </CustomBuildStep>  
    </ItemDefinitionGroup>  
    ```  
  
### So definieren Sie, an welcher Stelle im Build der benutzerdefinierte Buildschritt ausgeführt wird  
  
1.  Fügen Sie der Projektdatei die folgende Eigenschaftengruppe hinzu:  Sie können beide Ziele angeben, oder Sie können ein Ziel auslassen, wenn nur der benutzerdefinierte Schritt vor oder nach einem bestimmten Ziel ausgeführt werden soll.  In diesem Beispiel wird **MSBuild** angewiesen, den benutzerdefinierten Schritt nach dem Kompilier\-, jedoch vor dem Verknüpfungsschritt auszuführen.  
  
    ```  
    <PropertyGroup>  
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>  
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>  
    </PropertyGroup>  
    ```  
  
## Siehe auch  
 [Exemplarische Vorgehensweise: Verwenden von MSBuild zum Erstellen eines Visual C\+\+\-Projekts](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)   
 [Gewusst wie: Verwenden von Buildereignissen in MSBuild\-Projekten](../build/how-to-use-build-events-in-msbuild-projects.md)   
 [Gewusst wie: Hinzufügen von benutzerdefinierten Buildtools zu MSBuild\-Projekten](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)