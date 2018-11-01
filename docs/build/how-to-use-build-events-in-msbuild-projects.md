---
title: 'Gewusst wie: Verwenden von Buildereignissen in MSBuild-Projekten'
ms.date: 11/04/2016
f1_keywords:
- msbuild.cpp.howto.usebuildevents
helpviewer_keywords:
- 'msbuild (c++), howto: use build events in projects'
ms.assetid: 2a58dc9d-3d50-4e49-97c1-86c5a05ce218
ms.openlocfilehash: 60e26b5cab77bb56f0574a91ad69a7df4d73fa1e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570273"
---
# <a name="how-to-use-build-events-in-msbuild-projects"></a>Gewusst wie: Verwenden von Buildereignissen in MSBuild-Projekten

Ein Buildereignis ist ein Befehl, den MSBuild zu einem bestimmten Zeitpunkt im Buildprozess ausführt. Die *vor dem Erstellen* Ereignis tritt auf, bevor der Build gestartet wird; die *Prälinkereignis* Ereignis tritt auf, bevor Sie die Link-Schritt-beginnt; und die *Postbuild* Ereignis tritt auf, nach der Erstellung erfolgreich beendet wurde. Ein Buildereignis tritt nur auf, wenn der zugeordnete Buildschritt tritt ein, an. Z. B. das Prälinkereignis nicht ausgeführt, wenn der Linkschritt nicht ausgeführt werden kann.

Jede der drei Build-Ereignissen wird in eine Elementdefinitionsgruppe durch ein Befehlselement dargestellt (`<Command>`), die ausgeführt wird und ein Nachrichtenelement (`<Message>`), angezeigt wird, wenn **MSBuild** führt das Ereignis erstellt. Jedes Element ist optional, und wenn Sie das gleiche Element mehrmals angeben, wird das letzte Vorkommen hat Vorrang vor.

Eine optionale *in Buildvorgang verwenden* Element (`<`*Buildereignis*`UseInBuild>`) kann angegeben werden, in eine Eigenschaftengruppe, um anzugeben, ob das Ereignis erstellt, ausgeführt wird. Der Wert des Inhalts einer *in Buildvorgang verwenden* Element ist entweder **"true"** oder **"false"**. Standardmäßig wird ein Buildereignis ausgeführt, es sei denn, der entsprechenden *in Buildvorgang verwenden* Element nastaven NA hodnotu `false`.

Die folgende Tabelle enthält die XML-Element für jeden Build:

|XML-Element|Beschreibung|
|-----------------|-----------------|
|`PreBuildEvent`|Dieses Ereignis wird vor Beginn des Buildvorgangs ausgeführt.|
|`PreLinkEvent`|Dieses Ereignis ausgeführt wird, bevor der Linkschritt beginnt.|
|`PostBuildEvent`|Dieses Ereignis wird ausgeführt, nachdem der Build abgeschlossen ist.|

Die folgende Tabelle führt jede *in Buildvorgang verwenden* Element:

|XML-Element|Beschreibung|
|-----------------|-----------------|
|`PreBuildEventUseInBuild`|Gibt an, ob zum Ausführen der *Präbuildereignis* Ereignis.|
|`PreLinkEventUseInBuild`|Gibt an, ob zum Ausführen der *Prälinkereignis* Ereignis.|
|`PostBuildEventUseInBuild`|Gibt an, ob zum Ausführen der *Postbuild* Ereignis.|

## <a name="example"></a>Beispiel

Im folgende Beispiel hinzugefügt werden kann, innerhalb des Project-Elements der Datei "MyProject.vcxproj" im erstellten [Exemplarische Vorgehensweise: Verwenden von MSBuild zum Erstellen eines Visual C++-Projekts](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md). Ein *vor dem Erstellen* Ereignis ist eine Kopie von "Main.cpp"; eine *Prälinkereignis* Ereignis ist eine Kopie des main.obj; und ein *nach der Erstellung* Ereignis erstellt eine Kopie des myproject.exe. Wenn das Projekt mit einer Releasekonfiguration erstellt wird, werden die Buildereignisse ausgeführt. Wenn das Projekt erstellt wird, eine Debugkonfiguration verwenden, werden die Buildereignisse nicht ausgeführt.

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

[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)<br/>
[Exemplarische Vorgehensweise: Verwenden von MSBuild zum Erstellen eines Visual C++-Projekts](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)