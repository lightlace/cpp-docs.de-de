---
title: "Exemplarische Vorgehensweise: Verwenden von MSBuild zum Erstellen eines Visual C++-Projekts"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "msbuild.cpp.walkthrough.createproject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MSBuild (C++), Exemplarische Vorgehensweise: Erstellen eines Projekts"
ms.assetid: 52350d1c-c373-4868-923c-5e8be6f67adb
caps.latest.revision: 27
caps.handback.revision: "27"
ms.author: "corob"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Verwenden von MSBuild zum Erstellen eines Visual C++-Projekts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese exemplarische Vorgehensweise veranschaulicht, wie mit [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] ein [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Projekt an einer Eingabeaufforderung erstellt wird.  Sie erfahren, wie die C\+\+\-Quelldateien und eine XML\-basierte Projektdatei für eine [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Konsolenanwendung erstellt werden.  Nach der Erstellung des Projekts erfahren Sie, wie der Buildprozess angepasst wird.  
  
 In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:  
  
-   Erstellen der C\+\+\-Quelldateien für das Projekt  
  
-   Erstellen der [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]\-XML\-Projektdatei  
  
-   Erstellen des Projekts mithilfe von [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]  
  
-   Anpassen des Projekts mithilfe von [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]  
  
## Vorbereitungsmaßnahmen  
 Für diese exemplarische Vorgehensweise wird Folgendes benötigt:  
  
-   [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)]  
  
-   Allgemeine Kenntnisse des [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]\-Systems.  
  
## Erstellen der C\+\+\-Quelldateien  
 In dieser exemplarischen Vorgehensweise erstellen Sie ein Projekt, das eine Quell\- und eine Headerdatei besitzt.  Die Quelldatei "main.cpp" enthält die Hauptfunktion für die Konsolenanwendung.  Die Headerdatei "main.h" enthält Code zum Einschließen der iostream\-Headerdatei.  Sie können diese C\+\+\-Dateien mit [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] oder einem Text\-Editor erstellen.  
  
#### So erstellen Sie die C\+\+\-Quelldateien für das Projekt  
  
1.  Erstellen Sie ein Verzeichnis für das Projekt.  
  
2.  Erstellen Sie eine Datei mit dem Namen "main.cpp", und fügen Sie der Datei den folgenden Code hinzu:  
  
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
  
3.  Erstellen Sie eine Datei mit dem Namen "main.h", und fügen Sie der Datei den folgenden Code hinzu:  
  
    ```hlsl  
    // main.h: the application header code.  
    /* Additional source code to include. */  
    ```  
  
## Erstellen der XML\-MSBuild\-Projektdatei  
 Eine [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]\-Projektdatei ist eine XML\-Datei, die ein Projektstammelement \(\<Project\>\) enthält.  Im folgenden Beispielprojekt enthält das \<Project\>\-Element sieben untergeordnete Elemente:  
  
-   Drei Elementgruppentags \(\<ItemGroup\>\), die Projektkonfiguration und Plattform sowie Quelldateiname und Headerdateiname angeben.  
  
-   Drei Importtags \(\<Import\>\), die den Speicherort von Microsoft [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Einstellungen angeben.  
  
-   Ein Eigenschaftsgruppentag \(\<PropertyGroup\>\), das Projekteinstellungen angibt.  
  
#### So erstellen Sie die MSBuild\-Projektdatei  
  
1.  Erstellen Sie mithilfe eines Text\-Editors eine Projektdatei mit dem Namen `myproject.vcxproj`, und fügen Sie anschließend das folgende \<Project\>\-Stammelement hinzu.  Fügen Sie die Elemente in den folgenden Verfahrensschritten zwischen den \<Project\>\-Stammtags ein:  
  
    ```xml  
    <Project DefaultTargets="Build" ToolsVersion="12.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    </Project>  
    ```  
  
2.  Fügen Sie die folgenden zwei untergeordneten \<ProjectConfiguration\>\-Elemente in einem \<ItemGroup\>\-Element hinzu.  Das untergeordnete Element gibt Debug\- und Releasekonfigurationen für ein 32\-Bit\-Windows\-Betriebssystem an:  
  
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
  
3.  Fügen Sie das folgende \<Import\/\>\-Element hinzu, das den Pfad der standardmäßigen C\+\+\-Einstellungen für dieses Projekt angibt:  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />  
  
    ```  
  
4.  Fügen Sie das folgende Eigenschaftengruppenelement \(\<PropertyGroup\>\) hinzu, das zwei Projekteigenschaften angibt:  
  
    ```xml  
    <PropertyGroup>  
      <ConfigurationType>Application</ConfigurationType>  
      <PlatformToolset>v120</PlatformToolset>  
    </PropertyGroup>  
    ```  
  
5.  Fügen Sie das folgende \<Import\/\>\-Element hinzu, das den Pfad der aktuellen C\+\+\-Einstellungen für dieses Projekt angibt:  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />  
    ```  
  
6.  Fügen Sie das folgende untergeordnete  \<ClCompile\>\-Element in einem \<ItemGroup\>\-Element hinzu.  Das untergeordnete Element gibt den Namen der zu kompilierenden C\/C\+\+\-Quelldatei an:  
  
    ```xml  
    <ItemGroup>  
      <ClCompile Include="main.cpp" />  
    </ItemGroup>  
    ```  
  
7.  Fügen Sie das folgende untergeordnete \<ClInclude\>\-Element in einem \<ItemGroup\>\-Element hinzu.  Das untergeordnete Element gibt den Namen der Headerdatei für die C\/C\+\+\-Quelldatei an:  
  
    ```xml  
    <ItemGroup>  
      <ClInclude Include="main.h" />  
    </ItemGroup>  
    ```  
  
8.  Fügen Sie das folgende \<Import\>\-Element hinzu, das den Pfad der Datei angibt, durch die das Ziel für dieses Projekt definiert wird:  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />  
  
    ```  
  
### Vollständige Projektdatei  
 Im folgenden Code wird die zuvor erstellte vollständige Projektdatei dargestellt.  
  
```xml  
<Project DefaultTargets="Build" ToolsVersion="12.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
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
    <PlatformToolset>v120</PlatformToolset>  
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
  
## Verwenden von MSBuild für die Projekterstellung  
 Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, um die Konsolenanwendung zu erstellen:  
  
```  
msbuild myproject.vcxproj /p:configuration=debug  
```  
  
 Von [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] wird ein Verzeichnis für die Ausgabedateien erstellt, und anschließend wird das Projekt kompiliert und verknüpft, um das Programm "Myproject.exe" zu generieren.  Nachdem der Buildprozess beendet wurde, verwenden Sie den folgenden Befehl, um die Anwendung auszuführen:  
  
```  
myproject  
```  
  
 In der Anwendung sollte "Hello, from MSBuild\!" im Konsolenfenster angezeigt werden.  
  
## Anpassen des Projekts  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] ermöglicht die Ausführung von vordefinierten Buildzielen, das Übernehmen von benutzerdefinierten Eigenschaften und das Verwenden benutzerdefinierter Tools, Ereignisse und Buildschritte.  In diesem Abschnitt werden die folgenden Aufgaben veranschaulicht:  
  
-   Verwenden von [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] mit Buildzielen  
  
-   Verwenden von [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] mit Buildeigenschaften  
  
-   Verwenden von [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] mit dem 64\-Bit\-Compiler und Tools.  
  
-   Verwenden von [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] mit unterschiedlichen Toolsets  
  
-   Hinzufügen von [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]\-Anpassungen  
  
### Verwenden von MSBuild mit Buildzielen  
 Ein *Buildziel* ist ein benannter Satz mit vordefinierten oder benutzerdefinierten Befehlen, die während der Builderstellung ausgeführt werden können.  Verwenden Sie die Zielbefehlszeilenoption \(**\/t**\), um ein Buildziel anzugeben.  Im Fall des `myproject`\-Beispielprojekts werden vom vordefinierten **clean**\-Ziel alle Dateien im Debugordner gelöscht, und eine neue Protokolldatei wird erstellt.  
  
 Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, um `myproject` zu bereinigen.  
  
 `msbuild myproject.vcxproj /t:clean`  
  
### Verwenden von MSBuild mit Buildeigenschaften  
 Die Eigenschaften\-Befehlszeilenoption \(**\/p**\) ermöglicht es Ihnen, eine Eigenschaft in der Projektbuilddatei zu überschreiben.  Im `myproject`\- Beispielprojekt wird die Release\- oder Debugbuildkonfiguration durch die `Configuration`\-Eigenschaft angegeben.  Das Betriebssystem, das für die Ausführung der erstellten Anwendung vorgesehen ist, wird durch die `Platform`\-Eigenschaft angegeben.  
  
 Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, um einen Debugbuild der `myproject`\-Anwendung zu erstellen, die für die Ausführung unter Windows \(32 Bit\) vorgesehen ist.  
  
 `msbuild myproject.vcxproj /p:configuration=debug /p:platform=win32`  
  
 Angenommen, durch das `myproject`\-Beispielprojekt wird auch eine Konfiguration für Windows \(64 Bit\) und eine andere Konfiguration für ein benutzerdefiniertes Betriebssystem mit dem Namen `myplatform` definiert.  
  
 Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, um einen Releasebuild zu erstellen, der unter Windows \(64 Bit\) ausgeführt wird.  
  
 `msbuild myproject.vcxproj /p:configuration=release /p:platform=x64`  
  
 Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, um einen Releasebuild für `myplatform` anzuzeigen:  
  
 `msbuild myproject.vcxproj /p:configuration=release /p:platform=myplatform`  
  
### Verwenden von MSBuild mit dem 64\-Bit\-Compiler und Tools  
 Wenn Sie [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] auf einer 64\-Bit\-Windows\-Version installiert haben, werden standardmäßig die systemeigenen Tools sowie Cross Tools für 64\-Bit x64 installiert.  Sie können [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] konfigurieren, um den 64\-Bit\-Compiler und die Tools zur Erstellung Ihrer Anwendung zu verwenden, indem Sie die `PreferredToolArchitecture`\-Eigenschaft festlegen.  Diese Eigenschaft beeinflusst nicht die Projektkonfigurations\- oder Plattformeigenschaften.  Standardmäßig wird die 32\-Bit\-Version des Tools verwendet.  Fügen Sie zum Angeben der 64\-Bit\-Versionen des Compilers und der Tools die folgenden Eigenschaftengruppenelemente der Projektdatei "Myproject.vcxproj" nach dem `Microsoft.Cpp.default.props` \<Import \/\>\-Element hinzu:  
  
```xml  
<PropertyGroup>  
    <PreferredToolArchitecture>x64</PreferredToolArchitecture>  
</PropertyGroup>  
```  
  
 Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, um die 64\-Bit\-Tools zur Erstellung Ihrer Anwendung zu verwenden.  
  
 `msbuild myproject.vcxproj /p:PreferredToolArchitecture=x64`  
  
### Verwenden von MSBuild mit einem anderen Toolset  
 Wenn Sie die Toolsets \-und Bibliotheken für andere Versionen von [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] installiert haben, kann [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] entweder Anwendungen für die aktuelle [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Version oder für die anderen installierten Versionen erstellen.  Wenn Sie beispielsweise [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] installiert haben, um das [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 11.0 Toolset für Windows XP anzugeben, fügen Sie das folgende Eigenschaftengruppenelement der Projektdatei "Myproject.vcxproj" nach dem Element "Microsoft.Cpp.props" `<Import />` hinzu:  
  
```xml  
<PropertyGroup>  
    <PlatformToolset>v110_xp</PlatformToolset>  
</PropertyGroup>  
```  
  
 Geben Sie einen der folgenden Befehle ein, um das Projekt mit dem [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 11.0 Toolset für Windows XP erneut zu erstellen:  
  
 `msbuild myproject.vcxproj /p:PlatformToolset=v110_xp /t:rebuild`  
  
 `msbuild myproject.vcxproj /t:rebuild`  
  
### Hinzufügen von MSBuild\-Anpassungen  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] bietet verschiedene Möglichkeiten zur Anpassung des Buildprozesses.  Die folgenden Themen zeigen, wie dem [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]\-Projekt benutzerdefinierte Buildschritte, Tools und Ereignisse hinzugefügt werden:  
  
-   [Gewusst wie: Hinzufügen eines benutzerdefinierten Buildschritts zu MSBuild\-Projekten](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)  
  
-   [Gewusst wie: Hinzufügen von benutzerdefinierten Buildtools zu MSBuild\-Projekten](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)  
  
-   [Gewusst wie: Verwenden von Buildereignissen in MSBuild\-Projekten](../build/how-to-use-build-events-in-msbuild-projects.md)