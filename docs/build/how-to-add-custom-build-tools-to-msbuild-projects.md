---
title: "Gewusst wie: Hinzuf&#252;gen von benutzerdefinierten Buildtools zu MSBuild-Projekten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "msbuild.cpp.howto.addcustombuildtools"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MSBuild (C++), Gewusst wie: Hinzufügen von benutzerdefinierten Buildtools"
ms.assetid: de03899a-371d-4396-9bf9-34f45a65e909
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Gewusst wie: Hinzuf&#252;gen von benutzerdefinierten Buildtools zu MSBuild-Projekten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein benutzerdefiniertes Buildtool ist ein benutzerdefiniertes Befehlszeilentool, das einer bestimmten Datei zugeordnet ist.  
  
 Geben Sie für eine bestimmte Datei in der Projektdatei \(VCXPROJ\-Datei\) Folgendes an: die auszuführende Befehlszeile, alle zusätzlichen Eingabe\- oder Ausgabedateien und eine Meldung, die angezeigt werden soll.  Wenn von **MSBuild** bestimmt wird, dass die Ausgabedateien hinsichtlich der Eingabedateien nicht mehr aktuell sind, wird die Meldung angezeigt, und das Befehlszeilentool wird ausgeführt.  
  
 Verwenden Sie das `CustomBuildBeforeTargets`\-XML\-Element oder das `CustomBuildAfterTargets`\-XML\-Element in der Projektdatei oder beide Elemente, um anzugeben, wann das benutzterdefinierte Buildtool ausgeführt werden soll.  Sie können z. B. angeben, dass das benutzerdefinierte Buildtool nach dem MIDL\-Compiler und vor dem C\/C\+\+\-Compiler ausgeführt werden soll.  Geben Sie Folgendes an: das `CustomBuildBeforeTargets`\-Element, um das Tool auszuführen, bevor ein bestimmtes Ziel ausgeführt wird, das `CustomBuildAfterTargets`\-Element, um das Tool nach einem bestimmten Ziel auszuführen, oder beide Elemente, um das Tool zwischen der Ausführung von zwei Zielen auszuführen.  Wenn keines der Elemente angegeben wird, wird das benutzerdefinierte Buildtool an seinem Standardspeicherort ausgeführt, der vor dem **MIDL**\-Ziel liegt.  
  
 Für benutzerdefinierte Buildschritte und Buildtools werden die im `CustomBuildBeforeTargets`\-XML\-Element und `CustomBuildAfterTargets`\-XML\-Element angegebenen Informationen freigegeben.  Geben Sie diese Ziele einmal in der Projektdatei an.  
  
### So fügen Sie ein benutzerdefiniertes Tool hinzu  
  
1.  Fügen Sie der Projektdatei eine Elementgruppe hinzu, und fügen Sie für jede Eingabedatei ein Element hinzu.  Geben Sie den Befehl, zusätzliche Eingaben, Ausgaben und eine Meldung als Elementmetadaten an \(siehe vorliegende Darstellung\).  In diesem Beispiel wird angenommen, dass eine Datei mit der Bezeichnung "faq.txt" im gleichen Verzeichnis wie das Projekt vorhanden ist.  
  
    ```  
    <ItemGroup>  
      <CustomBuild Include="faq.txt">  
        <Message>Copying readme...</Message>  
        <Command>copy %(Identity) $(OutDir)%(Identity)</Command>  
        <Outputs>$(OutDir)%(Identity)</Outputs>  
      </CustomBuild>  
    </ItemGroup>  
    ```  
  
### So definieren Sie, an welcher Stelle im Build die benutzerdefinierten Tools ausgeführt werden  
  
1.  Fügen Sie der Projektdatei die folgende Eigenschaftengruppe hinzu:  Es muss mindestens eines der Ziele angegeben werden, wobei jedoch das andere Ziel weggelassen werden kann, wenn Sie nur festlegen möchten, dass der Buildschritt vor \(oder nach\) einem bestimmten Ziel ausgeführt wird.  In diesem Beispiel wird der benutzerdefinierte Schritt nach dem Kompilieren, jedoch vor dem Verknüpfen ausgeführt.  
  
    ```  
    <PropertyGroup>  
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>  
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>  
    </PropertyGroup>  
    ```  
  
## Siehe auch  
 [Exemplarische Vorgehensweise: Verwenden von MSBuild zum Erstellen eines Visual C\+\+\-Projekts](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)   
 [Gewusst wie: Verwenden von Buildereignissen in MSBuild\-Projekten](../build/how-to-use-build-events-in-msbuild-projects.md)   
 [Gewusst wie: Hinzufügen eines benutzerdefinierten Buildschritts zu MSBuild\-Projekten](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)