---
title: 'Vorgehensweise: Verwenden von Buildereignissen in MSBuild-Projekten | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.howto.usebuildevents
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: use build events in projects'
ms.assetid: 2a58dc9d-3d50-4e49-97c1-86c5a05ce218
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2367c85dbd4a4ef7b10d927592c0fb10a417f0e6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369772"
---
# <a name="how-to-use-build-events-in-msbuild-projects"></a>Gewusst wie: Verwenden von Buildereignissen in MSBuild-Projekten
Ein Buildereignis ist ein Befehl, [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] führt zu einem bestimmten Zeitpunkt im Buildprozess. Die *Präbuild* Ereignis tritt auf, bevor der Build gestartet wird; die *Linkervorstufen* Ereignis tritt auf, vor dem Starten der Link Schritt; und die *Postbuild* Ereignis tritt auf, nach der Erstellung erfolgreich beendet wurde. Ein Buildereignis tritt nur dann, wenn der zugeordnete Buildschritt auftritt. Z. B. die Prälinkereignis nicht ausgeführt, wenn der Linkschritt nicht ausgeführt werden kann.  
  
 Jede der drei Buildereignisse wird in einer Elementdefinitionsgruppe durch ein Command-Element dargestellt (`<Command>`), die ausgeführt wird und Message-Element (`<Message>`), angezeigt wird, wenn **MSBuild** führt das Buildereignis. Jedes Element ist optional, und wenn Sie das gleiche Element mehrfach angeben, wird das letzte Vorkommen hat Vorrang vor.  
  
 Ein optionales *Buildvorgang verwenden* Element (`<`* build-Ereignis ***UseInBuild**`>`) kann angegeben werden, in einer Eigenschaftsgruppe, um anzugeben, ob das Buildereignis ausgeführt wird. Der Wert des Inhalts einer *Buildvorgang verwenden* Element ist entweder `true` oder `false`. Standardmäßig wird ein Buildereignis ausgeführt, es sei denn, das entsprechende *Buildvorgang verwenden* -Elementgruppe ist `false`.  
  
 Die folgende Tabelle enthält die XML-Element für jeden Build:  
  
|XML-Element|Beschreibung|  
|-----------------|-----------------|  
|`PreBuildEvent`|Dieses Ereignis wird vor Beginn des Buildvorgangs ausgeführt.|  
|`PreLinkEvent`|Dieses Ereignis ausgeführt wird, bevor der Linkschritt beginnt.|  
|`PostBuildEvent`|Dieses Ereignis wird ausgeführt, nachdem der Build abgeschlossen ist.|  
  
 Die folgende Tabelle enthält alle *Buildvorgang verwenden* Element:  
  
|XML-Element|Beschreibung|  
|-----------------|-----------------|  
|`PreBuildEventUseInBuild`|Gibt an, ob zum Ausführen der *Präbuild* Ereignis.|  
|`PreLinkEventUseInBuild`|Gibt an, ob zum Ausführen der *Linkervorstufen* Ereignis.|  
|`PostBuildEventUseInBuild`|Gibt an, ob zum Ausführen der *Postbuild* Ereignis.|  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel hinzugefügt werden kann, innerhalb des Project-Elements der Datei "MyProject.vcxproj" im erstellten [Exemplarische Vorgehensweise: Verwenden von MSBuild zum Erstellen eines Visual C++-Projekts](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md). Ein *Präbuild* Ereignis macht eine Kopie von "Main.cpp". es kann ein *Linkervorstufen* Ereignis macht eine Kopie des main.obj; und ein *Postbuild* Ereignis erstellt eine Kopie des myproject.exe. Wenn das Projekt mit einer Releasekonfiguration erstellt wird, werden die Buildereignisse ausgeführt. Wenn das Projekt mit einer Debugkonfiguration erstellt wird, werden die Buildereignisse nicht ausgeführt.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)   
 [Exemplarische Vorgehensweise: Verwenden von MSBuild zum Erstellen eines Visual C++-Projekts](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)