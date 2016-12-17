---
title: "Gewusst wie: Verwenden von Buildereignissen in MSBuild-Projekten"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "msbuild.cpp.howto.usebuildevents"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MSBuild (C++), Gewusst wie: Verwenden von Buildereignissen in Projekten"
ms.assetid: 2a58dc9d-3d50-4e49-97c1-86c5a05ce218
caps.latest.revision: 23
caps.handback.revision: "23"
ms.author: "corob"
manager: "ghogen"
---
# Gewusst wie: Verwenden von Buildereignissen in MSBuild-Projekten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Buildereignis ist ein Befehl, der von [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] in einer bestimmten Phase des Buildprozesses ausgeführt wird.  Das *Präbuildereignis* tritt vor dem Buildvorgang auf; das *Prälinkereignis* tritt vor die startet auf; und das *Postbuild* ereignis tritt nach dem Build beendet erfolgreich auf.  Ein Buildereignis tritt nur auf, wenn der zugeordnete Buildschritt auftritt.  Das Prälinkereignis tritt z. B. nicht auf, wenn der Verknüpfungsschritt nicht ausgeführt wird.  
  
 Jedes der drei Buildereignisse wird in einer Elementdefinitionsgruppe durch folgende Elemente dargestellt: durch ein Befehlselement \(`<Command>`\), das ausgeführt wird, und durch ein Meldungselement, das angezeigt wird, \(`<Message>`\) wenn das Buildereignis von **MSBuild** ausgeführt wird.  Jedes Element ist optional, und wenn Sie das gleiche Element mehrfach angeben, erhält das letzte Vorkommen Vorrang.  
  
 Ein optionales Element vom Typ In *Buildvorgang* verwenden \(`<`*build\-event***UseInBuild**`>`\) kann in einer Eigenschaftengruppe angegeben werden, um anzugeben, ob das Buildereignis ausgeführt wird.  Der Wert des Inhalts eines Elements vom Typ *In Buildvorgang verwenden* ist entweder `true` oder `false`.  Standardmäßig wird ein Buildereignis ausgeführt, sofern das entsprechende Element vom Typ *In Buildvorgang verwenden* nicht auf `false` festgelegt wird.  
  
 In der folgenden Tabelle wird jedes XML\-Element für Buildereignisse aufgeführt:  
  
|XML\-Element|**Beschreibung**|  
|------------------|----------------------|  
|`PreBuildEvent`|Dieses Ereignis wird vor Beginn des Buildvorgangs ausgeführt.|  
|`PreLinkEvent`|Dieses Ereignis wird ausgeführt, bevor der Verknüpfungsschritt beginnt.|  
|`PostBuildEvent`|Dieses Ereignis wird ausgeführt, nachdem der Buildvorgang beendet wurde.|  
  
 In der folgenden Tabelle ist jedes Element vom Typ *In Buildvorgang verwenden* aufgeführt:  
  
|XML\-Element|**Beschreibung**|  
|------------------|----------------------|  
|`PreBuildEventUseInBuild`|Gibt an, ob das *Präbuildereignis* ausgeführt werden soll.|  
|`PreLinkEventUseInBuild`|Gibt an, ob das *Prälinkereignis* ausgeführt werden soll.|  
|`PostBuildEventUseInBuild`|Gibt an, ob das *Postbuildereignis* ausgeführt werden soll.|  
  
## Beispiel  
 Das folgende Beispiel kann innerhalb des Projektelements der in [Exemplarische Vorgehensweise: Verwenden von MSBuild zum Erstellen eines Visual C\+\+\-Projekts](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md) erstellten Datei "myproject.vcxproj" hinzugefügt werden.  In einem *Präbuildereignis* wird eine Kopie von "main.cpp" erstellt; in einem *Prälinkereignis* wird eine Kopie von "main.obj" erstellt; und in einem *Postbuildereignis* wird eine Kopie von "myproject.exe" erstellt.  Wenn das Projekt mit einer Releasekonfiguration erstellt wird, werden die Buildereignisse ausgeführt.  Wenn das Projekt mit einer Debugkonfiguration erstellt wird, werden die Buildereignisse nicht ausgeführt.  
  
```  
<ItemDefinitionGroup>  
  <PreBuildEvent>  
    <Command>copy $(ProjectDir)main.cpp $(ProjectDir)copyOfMain.cpp</Command>  
    <Message>Making a copy of main.cpp </Message>  
  </PreBuildEvent>  
  <PreLinkEvent>  
 <Command>copy $(ProjectDir)$(Configuration)\main.obj $(ProjectDir)$(Configuration)\copyOfMain.obj</Command>  
    <Message>Making a copy of main.obj</Message>  
  </PreLinkEvent>  
  <PostBuildEvent>  
 <Command>copy $(ProjectDir)$(Configuration)\$(TargetFileName) $(ProjectDir)$(Configuration)\copyOfMyproject.exe</Command>  
    <Message>Making a copy of myproject.exe</Message>  
  </PostBuildEvent>  
</ItemDefinitionGroup>  
  
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">  
  <PreBuildEventUseInBuild>true</PreBuildEventUseInBuild>  
  <PreLinkEventUseInBuild>true</PreLinkEventUseInBuild>  
  <PostBuildEventUseInBuild>true</PostBuildEventUseInBuild>  
</PropertyGroup>  
  
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">  
  <PreBuildEventUseInBuild>false</PreBuildEventUseInBuild>  
  <PreLinkEventUseInBuild>false</PreLinkEventUseInBuild>  
  <PostBuildEventUseInBuild>false</PostBuildEventUseInBuild>  
</PropertyGroup>  
```  
  
## Siehe auch  
 [MSBuild \(Visual C\+\+\)](../build/msbuild-visual-cpp.md)   
 [Exemplarische Vorgehensweise: Verwenden von MSBuild zum Erstellen eines Visual C\+\+\-Projekts](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)