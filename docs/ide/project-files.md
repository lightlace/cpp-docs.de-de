---
title: Projektdateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- .vcproj files
- Visual C++ projects, project file format
- VCPROJ (Visual C++ project file) format
- project files [C++], .vcproj file format
ms.assetid: 5261cf45-3136-40a6-899e-dc1339551401
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e66d6e94e4938c72adc5aea1a478ce6c0658e56e
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "33327228"
---
# <a name="project-files"></a>Projektdateien
Eine Visual C++-Projektdatei ist eine XML-basierte Datei, die über die Erweiterung „VCXPROJ“ verfügt und Informationen enthält, die zum Erstellen eines Visual C++-Projekts erforderlich sind.  
  
## <a name="example"></a>Beispiel  
 Die folgende VCXPROJ-Beispieldatei wurde erstellt, indem eine **Win32-Konsolenanwendung** im Dialogfeld **Neues Projekt** angegeben wurde. Verwenden Sie zum Verarbeiten einer Projektdatei entweder das Tool „msbuild.exe“ in der Befehlszeile oder den Befehl **Build** in [!INCLUDE[TLA2#tla_ide](../build/includes/tla2sharptla_ide_md.md)]. (Dieses Beispiel kann nicht verarbeitet werden, da die erforderlichen Quell- und Headerdateien nicht bereitgestellt werden.) Weitere Informationen über die XML-Elemente in einer Projektdatei finden Sie unter [Referenz zum Projektdateischema](/visualstudio/msbuild/msbuild-project-file-schema-reference).  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <ItemGroup Label="ProjectConfigurations">  
    <ProjectConfiguration Include="Debug|Win32">  
      <Configuration>Debug</Configuration>  
      <Platform>Win32</Platform>  
    </ProjectConfiguration>  
    <ProjectConfiguration Include="Release|Win32">  
      <Configuration>Release</Configuration>  
      <Platform>Win32</Platform>  
    </ProjectConfiguration>  
  </ItemGroup>  
  <PropertyGroup Label="Globals">  
    <ProjectGuid>{96F21549-A7BF-4695-A1B1-B43625B91A14}</ProjectGuid>  
    <Keyword>Win32Proj</Keyword>  
    <RootNamespace>SomeProjName</RootNamespace>  
  </PropertyGroup>  
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Default.props" />  
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'" Label="Configuration">  
    <ConfigurationType>Application</ConfigurationType>  
    <CharacterSet>Unicode</CharacterSet>  
  </PropertyGroup>  
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'" Label="Configuration">  
    <ConfigurationType>Application</ConfigurationType>  
    <WholeProgramOptimization>true</WholeProgramOptimization>  
    <CharacterSet>Unicode</CharacterSet>  
  </PropertyGroup>  
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />  
  <ImportGroup Label="ExtensionSettings">  
  </ImportGroup>  
  <ImportGroup Label="PropertySheets" Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">  
    <Import Project="$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props" Condition="exists('$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props')" Label="LocalAppDataPlatform" />  
  </ImportGroup>  
  <ImportGroup Label="PropertySheets" Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">  
    <Import Project="$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props" Condition="exists('$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props')" Label="LocalAppDataPlatform" />  
  </ImportGroup>  
  <PropertyGroup Label="UserMacros" />  
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">  
    <LinkIncremental>true</LinkIncremental>  
  </PropertyGroup>  
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">  
    <LinkIncremental>false</LinkIncremental>  
  </PropertyGroup>  
  <ItemDefinitionGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">  
    <ClCompile>  
      <PrecompiledHeader>Use</PrecompiledHeader>  
      <WarningLevel>Level3</WarningLevel>  
      <MinimalRebuild>true</MinimalRebuild>  
      <DebugInformationFormat>EditAndContinue</DebugInformationFormat>  
      <Optimization>Disabled</Optimization>  
      <BasicRuntimeChecks>EnableFastChecks</BasicRuntimeChecks>  
      <RuntimeLibrary>MultiThreadedDebugDLL</RuntimeLibrary>  
      <PreprocessorDefinitions>WIN32;_DEBUG;_CONSOLE;%(PreprocessorDefinitions)</PreprocessorDefinitions>  
    </ClCompile>  
    <Link>  
      <SubSystem>Console</SubSystem>  
      <GenerateDebugInformation>true</GenerateDebugInformation>  
    </Link>  
  </ItemDefinitionGroup>  
  <ItemDefinitionGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">  
    <ClCompile>  
      <WarningLevel>Level3</WarningLevel>  
      <PrecompiledHeader>Use</PrecompiledHeader>  
      <DebugInformationFormat>ProgramDatabase</DebugInformationFormat>  
      <Optimization>MaxSpeed</Optimization>  
      <RuntimeLibrary>MultiThreadedDLL</RuntimeLibrary>  
      <FunctionLevelLinking>true</FunctionLevelLinking>  
      <IntrinsicFunctions>true</IntrinsicFunctions>  
      <PreprocessorDefinitions>WIN32;NDEBUG;_CONSOLE;%(PreprocessorDefinitions)</PreprocessorDefinitions>  
    </ClCompile>  
    <Link>  
      <SubSystem>Console</SubSystem>  
      <GenerateDebugInformation>true</GenerateDebugInformation>  
      <EnableCOMDATFolding>true</EnableCOMDATFolding>  
      <OptimizeReferences>true</OptimizeReferences>  
    </Link>  
  </ItemDefinitionGroup>  
  <ItemGroup>  
    <None Include="ReadMe.txt" />  
  </ItemGroup>  
  <ItemGroup>  
    <ClInclude Include="stdafx.h" />  
    <ClInclude Include="targetver.h" />  
  </ItemGroup>  
  <ItemGroup>  
    <ClCompile Include="SomeProjName.cpp" />  
    <ClCompile Include="stdafx.cpp">  
      <PrecompiledHeader Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">Create</PrecompiledHeader>  
      <PrecompiledHeader Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">Create</PrecompiledHeader>  
    </ClCompile>  
  </ItemGroup>  
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />  
  <ImportGroup Label="ExtensionTargets">  
  </ImportGroup>  
</Project>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Building C++ Projects in Visual Studio (Erstellen von C++-Projekten in Visual Studio)](../ide/building-cpp-projects-in-visual-studio.md)   
 [Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md)