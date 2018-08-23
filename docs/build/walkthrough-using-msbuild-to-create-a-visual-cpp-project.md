---
title: 'Exemplarische Vorgehensweise: Verwenden von MSBuild zum Erstellen eines Visual C++-Projekts | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.walkthrough.createproject
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), walkthrough: create a project'
ms.assetid: 52350d1c-c373-4868-923c-5e8be6f67adb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8bb957f0ab1dd2ea7d05151257aee0e15561e8a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609698"
---
# <a name="walkthrough-using-msbuild-to-create-a-visual-c-project"></a>Exemplarische Vorgehensweise: Verwenden von MSBuild zum Erstellen eines Visual C++-Projekts

Diese exemplarische Vorgehensweise veranschaulicht die Verwendung von MSBuild zum Erstellen eines Visual C++-Projekts an einer Eingabeaufforderung. Erfahren Sie, wie die C++-Quelldateien und eine XML-basierte Projektdatei für eine Visual C++-Konsolenanwendung zu erstellen. Nach der Erstellung des Projekts erfahren Sie, wie der Buildprozess angepasst wird.

In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:

- Erstellen der C++-Quelldateien für das Projekt

- Erstellen von XML-MSBuild-Projektdatei.

- Verwenden von MSBuild zum Erstellen Ihres Projekts.

- Verwenden von MSBuild zum Anpassen des Projekts.

## <a name="prerequisites"></a>Erforderliche Komponenten

Für diese exemplarische Vorgehensweise wird Folgendes benötigt:

- Eine Kopie von Visual Studio mit der **Desktopentwicklung mit C++** arbeitsauslastung installiert.

- Allgemeine Kenntnisse des MSBuild-Systems.

> [!NOTE]
> Verwenden Sie diesen Ansatz nicht, wenn Sie die Projektdatei wird später mithilfe von Visual Studio-IDE bearbeiten möchten. Wenn Sie eine VCXPROJ-Datei manuell erstellen, die Visual Studio-IDE möglicherweise nicht zum Bearbeiten oder zu laden, insbesondere dann, wenn das Projekt Platzhalter in Projektelementen verwendet.

> [!NOTE]
> Die meisten der Low-Level Buildanweisungen befinden sich die **targets** und **props** Dateien, die im VCTargets-Verzeichnis, in der Eigenschaft gespeicherten definiert sind `$(VCTargetsPath)`. Der standardmäßige Pfad für diese Dateien in Visual Studio 2017 Enterprise Edition ist "c:"\\Programmdateien (x86)\\Microsoft Visual Studio\\2017\\Enterprise\\Common7\\IDE\\ VC\\VCTargets\\.

## <a name="creating-the-c-source-files"></a>Erstellen der C++-Quelldateien

In dieser exemplarischen Vorgehensweise erstellen Sie ein Projekt, das eine Quell- und eine Headerdatei besitzt. Die Quelldatei "main.cpp" enthält die Hauptfunktion für die Konsolenanwendung. Die Headerdatei "main.h" enthält Code zum Einschließen der iostream-Headerdatei. Sie können diese C++-Dateien mit Visual Studio oder einem Text-Editor wie Visual Studio Code erstellen.

### <a name="to-create-the-c-source-files-for-your-project"></a>So erstellen Sie die C++-Quelldateien für das Projekt

1. Erstellen Sie ein Verzeichnis für das Projekt.

2. Erstellen Sie eine Datei mit dem Namen "main.cpp", und fügen Sie der Datei den folgenden Code hinzu:

    ```cpp
    // main.cpp : the application source code.
    #include <iostream>
    #include "main.h"
    int main()
    {
       std::cout << "Hello, from MSBuild!\n";
       return 0;
    }
    ```

3. Erstellen Sie eine Datei mit dem Namen "main.h", und fügen Sie der Datei den folgenden Code hinzu:

    ```cpp
    // main.h: the application header code.
    /* Additional source code to include. */
    ```

## <a name="creating-the-xml-msbuild-project-file"></a>Erstellen der XML-MSBuild-Projektdatei

Eine MSBuild-Projektdatei ist eine XML-Datei, die ein Projektstammelement enthält (\<Projekt >). Im folgenden Beispielprojekt die \<Projekt >-Element enthält sieben untergeordnete Elemente:

- Drei Elementgruppentags (\<ItemGroup >), die Projektkonfiguration und Plattform, Quelldateiname und Headerdateiname angeben.

- Drei importtags (\<Importieren >), die den Speicherort der Microsoft Visual C++-Einstellungen angeben.

- Ein eigenschaftsgruppentag (\<PropertyGroup >), das projekteinstellungen angibt.

### <a name="to-create-the-msbuild-project-file"></a>So erstellen Sie die MSBuild-Projektdatei

1. Mithilfe eines Texteditors um eine Projektdatei zu erstellen, mit dem Namen `myproject.vcxproj`, und fügen Sie dann den folgenden Stamm \<Projekt > Element. Fügen Sie die Elemente in den folgenden Verfahrensschritten zwischen den Stamm \<Projekt > Tags:

    ```xml
    <Project DefaultTargets="Build" ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    </Project>
    ```

2. Fügen Sie die folgenden beiden \<ProjectConfiguration > untergeordnete Elemente in einem \<ItemGroup >-Element. Das untergeordnete Element gibt Debug- und Releasekonfigurationen für ein 32-Bit-Windows-Betriebssystem an:

    ```xml
    <ItemGroup>
      <ProjectConfiguration Include="Debug|Win32">
        <Configuration>Debug</Configuration>
        <Platform>Win32</Platform>
      </ProjectConfiguration>
      <ProjectConfiguration Include="Release|Win32">
        <Configuration>Release</Configuration>
        <Platform>Win32</Platform>
      </ProjectConfiguration>
    </ItemGroup>
    ```

3. Fügen Sie die folgenden \<Import / >-Element, das den Pfad der standardmäßigen C++-Einstellungen für dieses Projekt angibt:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
    ```

4. Fügen Sie das folgende Eigenschaftengruppenelement (\<PropertyGroup >), das zwei Projekteigenschaften angibt:

    ```xml
    <PropertyGroup>
      <ConfigurationType>Application</ConfigurationType>
      <PlatformToolset>v141</PlatformToolset>
    </PropertyGroup>
    ```

5. Fügen Sie die folgenden \<Import / >-Element, das den Pfad der aktuellen C++-Einstellungen für dieses Projekt angibt:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
    ```

6. Fügen Sie die folgenden \<ClCompile > untergeordnete Element in einer \<ItemGroup >-Element. Das untergeordnete Element gibt den Namen der zu kompilierenden C/C++-Quelldatei an:

    ```xml
    <ItemGroup>
      <ClCompile Include="main.cpp" />
    </ItemGroup>
    ```

   > [!NOTE]
   > \<ClCompile > ist eine *Buildziel* und in der **VCTargets** Verzeichnis.

7. Fügen Sie die folgenden \<ClInclude > untergeordnete Element in einer \<ItemGroup >-Element. Das untergeordnete Element gibt den Namen der Headerdatei für die C/C++-Quelldatei an:

    ```xml
    <ItemGroup>
      <ClInclude Include="main.h" />
    </ItemGroup>
    ```

8. Fügen Sie die folgenden \<Import >-Element, das den Pfad der Datei angibt, die das Ziel für dieses Projekt definiert:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />
    ```

### <a name="complete-project-file"></a>Vollständige Projektdatei

Im folgenden Code wird die zuvor erstellte vollständige Projektdatei dargestellt.

```xml
<Project DefaultTargets="Build" ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ItemGroup>
    <ProjectConfiguration Include="Debug|Win32">
      <Configuration>Debug</Configuration>
      <Platform>Win32</Platform>
    </ProjectConfiguration>
    <ProjectConfiguration Include="Release|Win32">
      <Configuration>Release</Configuration>
      <Platform>Win32</Platform>
    </ProjectConfiguration>
  </ItemGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
  <PropertyGroup>
    <ConfigurationType>Application</ConfigurationType>
    <PlatformToolset>v141</PlatformToolset>
  </PropertyGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
  <ItemGroup>
    <ClCompile Include="main.cpp" />
  </ItemGroup>
  <ItemGroup>
    <ClInclude Include="main.h" />
  </ItemGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />
</Project>
```

## <a name="using-msbuild-to-build-your-project"></a>Verwenden von MSBuild für die Projekterstellung

Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, um die Konsolenanwendung zu erstellen:

`msbuild myproject.vcxproj /p:configuration=debug`

MSBuild erstellt ein Verzeichnis für Ausgabedateien, und klicken Sie dann kompiliert und verknüpft das Projekt, um das Programm Myproject.exe zu generieren. Nachdem der Buildprozess beendet wurde, verwenden Sie den folgenden Befehl, um die Anwendung auszuführen:

`myproject`

Die Anwendung sollte "Hello, from MSBuild!" angezeigt werden. im Konsolenfenster anzuzeigen.

## <a name="customizing-your-project"></a>Anpassen des Projekts

MSBuild können Sie zum Ausführen von vordefinierten Buildzielen, Anwenden von benutzerdefinierten Eigenschaften, und Verwenden benutzerdefinierter Tools, Ereignisse und Buildschritte. In diesem Abschnitt werden die folgenden Aufgaben veranschaulicht:

- Verwenden von MSBuild mit Buildzielen.

- Verwenden von MSBuild mit Buildeigenschaften.

- Verwenden von MSBuild mit dem 64-Bit-Compiler und Tools.

- Verwenden von MSBuild mit unterschiedlichen Toolsets.

- Hinzufügen von MSBuild-Anpassungen.

### <a name="using-msbuild-with-build-targets"></a>Verwenden von MSBuild mit Buildzielen

Ein *Buildziel* ist ein benannter Satz von vordefinierten oder benutzerdefinierten Befehlen, die während des Builds ausgeführt werden kann. Verwenden Sie die Zielbefehlszeilenoption (**/t /**) um ein Buildziel anzugeben. Im Fall von der `myproject` -Beispielprojekts werden die vordefinierten **Bereinigen** Ziel löscht alle Dateien im Ordner "Debug" und eine neue Protokolldatei erstellt.

Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, um `myproject` zu bereinigen.

`msbuild myproject.vcxproj /t:clean`

### <a name="using-msbuild-with-build-properties"></a>Verwenden von MSBuild mit Buildeigenschaften

Die Eigenschaften-Befehlszeilenoption (**/p**) können Sie eine Eigenschaft in der Projektbuilddatei zu überschreiben. Im `myproject`- Beispielprojekt wird die Release- oder Debugbuildkonfiguration durch die `Configuration`-Eigenschaft angegeben. Das Betriebssystem, das für die Ausführung der erstellten Anwendung vorgesehen ist, wird durch die `Platform`-Eigenschaft angegeben.

Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, um einen Debugbuild der `myproject`-Anwendung zu erstellen, die für die Ausführung unter Windows (32 Bit) vorgesehen ist.

`msbuild myproject.vcxproj /p:configuration=debug /p:platform=win32`

Angenommen, durch das `myproject`-Beispielprojekt wird auch eine Konfiguration für Windows (64 Bit) und eine andere Konfiguration für ein benutzerdefiniertes Betriebssystem mit dem Namen `myplatform` definiert.

Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, um einen Releasebuild zu erstellen, der unter Windows (64 Bit) ausgeführt wird.

`msbuild myproject.vcxproj /p:configuration=release /p:platform=x64`

Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, um einen Releasebuild für `myplatform` anzuzeigen:

`msbuild myproject.vcxproj /p:configuration=release /p:platform=myplatform`

### <a name="using-msbuild-with-the-64-bit-compiler-and-tools"></a>Verwenden von MSBuild mit dem 64-Bit-Compiler und Tools

Wenn Sie Visual C++ für 64-Bit-Windows werden standardmäßig installiert haben, werden die 64-Bit-X64 systemeigene und cross-Tools installiert. Sie können konfigurieren, dass MSBuild für die 64-Bit-Compiler und Tools zu verwenden, um die Erstellung Ihrer Anwendung durch Festlegen der `PreferredToolArchitecture` Eigenschaft. Diese Eigenschaft beeinflusst nicht die Projektkonfigurations- oder Plattformeigenschaften. Standardmäßig wird die 32-Bit-Version des Tools verwendet. Zum Angeben der 64-Bit-Version des Compilers und der Tools fügen Sie das folgende Eigenschaftengruppenelement der Projektdatei "MyProject.vcxproj" nach der `Microsoft.Cpp.default.props` \<Import / >-Element:

```xml
<PropertyGroup>
    <PreferredToolArchitecture>x64</PreferredToolArchitecture>
</PropertyGroup>
```

Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, um die 64-Bit-Tools zur Erstellung Ihrer Anwendung zu verwenden.

`msbuild myproject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="using-msbuild-with-a-different-toolset"></a>Verwenden von MSBuild mit einem anderen toolset

Wenn Sie die Toolsets- und -Bibliotheken für andere Versionen von Visual C++ installiert haben, kann MSBuild Anwendungen, die für die aktuelle Visual C++ Version oder anderen installierten Versionen erstellen. Z. B. bei Installation von Visual Studio 2012, um anzugeben, das Visual C++ 11.0 Toolset für Windows XP, fügen Sie das folgende Eigenschaftengruppenelement der Projektdatei "MyProject.vcxproj" nach der Microsoft.Cpp.props `<Import />` Element:

```xml
<PropertyGroup>
    <PlatformToolset>v110_xp</PlatformToolset>
</PropertyGroup>
```

Geben Sie einen der folgenden Befehle, um Ihr Projekt mit Visual C++ 11.0 Windows XP-Toolset neu zu erstellen:

`msbuild myproject.vcxproj /p:PlatformToolset=v110_xp /t:rebuild`

`msbuild myproject.vcxproj /t:rebuild`

### <a name="adding-msbuild-customizations"></a>Hinzufügen von MSBuild-Anpassungen

MSBuild bietet verschiedene Möglichkeiten zum Anpassen des Buildprozesses. Die folgenden Themen zeigen, wie das MSBuild-Projekt benutzerdefinierte Buildschritte, Tools und Ereignisse hinzugefügt wird:

- [Vorgehensweise: Hinzufügen eines benutzerdefinierten Buildschritts zu MSBuild-Projekten](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)

- [Vorgehensweise: Hinzufügen von benutzerdefinierten Buildtools zu MSBuild-Projekten](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)

- [Vorgehensweise: Verwenden von Buildereignissen in MSBuild-Projekten](../build/how-to-use-build-events-in-msbuild-projects.md)
