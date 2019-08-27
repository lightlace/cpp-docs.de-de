---
title: 'Vorgehensweise: Verwenden von Buildereignissen in MSBuild-Projekten'
ms.date: 11/04/2016
helpviewer_keywords:
- 'msbuild (c++), howto: use build events in projects'
ms.assetid: 2a58dc9d-3d50-4e49-97c1-86c5a05ce218
ms.openlocfilehash: 3fe205223b6cf381bbf3e2872b1a84f9d81a3cb7
ms.sourcegitcommit: 2da5c42928739ca8cd683a9002598f28d8ec5f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70060069"
---
# <a name="how-to-use-build-events-in-msbuild-projects"></a>Vorgehensweise: Verwenden von Buildereignissen in MSBuild-Projekten

Ein Buildereignis ist ein Befehl, den MSBuild in einer bestimmten Phase im Buildprozess ausführt. Das Präbuildereignis tritt vor dem Start des Builds auf. Das *Pre-Link-* Ereignis tritt auf, bevor der Link Schritt gestartet wird. und das Postbuildereignis tritt auf, nachdem der Build erfolgreich beendet wurde. Ein Buildereignis tritt nur auf, wenn der zugeordnete Buildschritt auftritt. Beispielsweise tritt das prälingereignis nicht auf, wenn der Link Schritt nicht ausgeführt wird.

Jedes der drei Buildereignisse wird in einer Element Definitions Gruppe durch ein ausgeführtes`<Command>`Befehls Element () und ein Message-Element`<Message>`() dargestellt, das angezeigt wird, wenn **MSBuild** das Buildereignis ausführt. Jedes Element ist optional, und wenn Sie dasselbe Element mehrmals angeben, hat das letzte Vorkommen Vorrang.

Ein optionales *use-in-Build-* Element (`<`*Build-Event*`UseInBuild>`) kann in einer Eigenschaften Gruppe angegeben werden, um anzugeben, ob das Buildereignis ausgeführt wird. Der Wert des Inhalts eines *use-in-Build-* Elements ist entweder **true** oder **false**. Standardmäßig wird ein Buildereignis ausgeführt, es sei denn, das entsprechende *use-in-Build-* Element ist auf `false`festgelegt.

In der folgenden Tabelle sind die einzelnen Build-Ereignis-XML-Elemente aufgelistet

|XML-Element|Beschreibung|
|-----------------|-----------------|
|`PreBuildEvent`|Dieses Ereignis wird vor Beginn des Builds ausgeführt.|
|`PreLinkEvent`|Dieses Ereignis wird vor Beginn des Link Schritts ausgeführt.|
|`PostBuildEvent`|Dieses Ereignis wird ausgeführt, nachdem der Build abgeschlossen wurde.|

In der folgenden Tabelle sind die einzelnen *use-in-Build-* Elemente aufgelistet:

|XML-Element|Beschreibung|
|-----------------|-----------------|
|`PreBuildEventUseInBuild`|Gibt an, ob das Präbuildereignis ausgeführt werden soll.|
|`PreLinkEventUseInBuild`|Gibt an, ob das prälingereignis ausgeführt werden soll.|
|`PostBuildEventUseInBuild`|Gibt an, ob das Postbuildereignis ausgeführt werden soll.|

## <a name="example"></a>Beispiel

Das folgende Beispiel kann innerhalb des Project-Elements der MyProject. vcxproj-Datei hinzugefügt werden, [die in Walkthrough erstellt wurde: Verwenden von MSBuild zum Erstellen C++ eines](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)Projekts. Ein Präbuildereignis erstellt eine Kopie von "Main. cpp;". ein *Prälinkereignis* erstellt eine Kopie von "Main. obj;". ein Postbuildereignis erstellt eine Kopie von "MyProject. exe". Wenn das Projekt mit einer Releasekonfiguration erstellt wird, werden die Buildereignisse ausgeführt. Wenn das Projekt mit einer Debugkonfiguration erstellt wird, werden die Buildereignisse nicht ausgeführt.

``` xml
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

[MSBuild on the Command Line – C++ (C++: MSBuild in der Befehlszeile)](msbuild-visual-cpp.md)<br/>
[Exemplarische Vorgehensweise: Verwenden von MSBuild zum Erstellen eines C++-Projekts](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)
