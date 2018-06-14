---
title: VCXPROJ- und PROPS-Dateistruktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- .vcxproj file structure
ms.assetid: 14d0c552-29db-480e-80c1-7ea89d6d8e9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe466ff9250543a61fde8da41900b152a9874e09
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33337349"
---
# <a name="vcxproj-and-props-file-structure"></a>VCXPROJ- und PROPS-Dateistruktur

MSBuild ist das Standardprojektsystem in Visual Studio. Wenn Sie in Visual C++ auf **Datei > Neues Projekt** klicken, erstellen Sie ein MSBuild-Projekt, dessen Einstellungen in einer XML-Projektdatei mit der Erweiterung `.vcxproj` gespeichert werden. Die Projektdatei kann ebenfalls PROPS- und TARGETS-Dateien importieren, in denen Einstellungen gespeichert werden können. In den meisten Fällen müssen Sie die Projektdatei nicht bearbeiten. Sie sollten sogar davon absehen, sie manuell zu bearbeiten, sofern Sie nicht über gute Kenntnisse über MSBuild verfügen. Nach Möglichkeit sollten Sie die Visual Studio-Eigenschaftenseiten verwenden, um Projekteinstellungen zu bearbeiten. Weitere Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](working-with-project-properties.md). In manchen Fällen müssen Sie eine Projektdatei oder ein Eigenschaftenblatt jedoch manuell bearbeiten. Für diese Szenarios enthält dieser Artikel grundlegende Informationen zur Struktur der Datei.

**Wichtig:**

Wenn Sie eine VCXPROJ-Datei manuell bearbeiten, sollten Sie Folgendes beachten:

1. Die Struktur der Datei muss einer vorgeschriebenen Form folgen, die in diesem Artikel beschrieben wird.

1. Das Visual C++-Projektsystem unterstützt derzeit keine Platzhalter in Projektelementen. Folgendes wird beispielsweise nicht unterstützt:

   ```xml
   <ClCompile Include="*.cpp"/>
   ```

1. Das Visual C++-Projektsystem unterstützt derzeit keine Makros in Pfaden von Projektelementen. Folgendes wird beispielsweise nicht unterstützt:

   ```xml
   <ClCompile Include="$(IntDir)\generated.cpp"/>
   ```

1. Damit die Projekteigenschaften ordnungsgemäß hinzugefügt, entfernt oder geändert werden, wenn sie im Dialogfeld **Projekteigenschaften** bearbeitet werden, muss die Datei separate Gruppen für jede Projektkonfiguration enthalten, und die Bedingungen müssen folgende Form aufweisen:

   ```xml
   Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'"
   ```

1. Jede Eigenschaft muss in der Gruppe mit der richtigen Bezeichnung, die auch in der Regeldatei der Eigenschaft angegeben ist, angegeben sein. Weitere Informationen finden Sie unter [Property page xml rule files (XML-Regeldateien für Eigenschaftenseiten)](property-page-xml-files.md).

## <a name="vcxproj-file-elements"></a>VCXPROJ-Dateielemente

Sie können die Inhalte einer VCXPROJ-Datei überprüfen, indem Sie einen Text- oder XML-Editor verwenden. Sie können sie in Visual Studio anzeigen, indem Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt klicken und anschließend **Projekt entladen** > **Foo.vcxproj bearbeiten** auswählen.

Zunächst werden Sie feststellen, dass die Elemente auf oberster Ebene in einer bestimmten Reihenfolge angezeigt werden. Zum Beispiel:

- Die meisten Eigenschaftengruppen und Elementdefinitionsgruppen werden nach dem Import für „Microsoft.Cpp.Default.props“ angezeigt.
- Alle Ziele werden am Ende der Datei importiert.
- Es gibt mehrere Eigenschaftengruppen, die jeweils eine eindeutige Bezeichnung besitzen und in einer bestimmten Reihenfolge auftreten.

Die Reihenfolge der Elemente in der Projektdatei ist wichtig, da MSBuild auf einem sequenziellen Evaluierungsmodell basiert.  Wenn Ihre Projektdatei (einschließlich aller importierten PROPS- und TARGETS-Dateien) aus mehreren Definitionen einer Eigenschaft besteht, überschreibt die letzte Definition die vorherigen. Im folgenden Beispiel wird der Wert „xyz“ während der Kompilierung festgelegt, da die MSBuild-Engine diesen bei der Auswertung zuletzt findet.

```xml
  <MyProperty>abc</MyProperty>
  <MyProperty>xyz</MyProperty>
```

Im folgenden Codeausschnitt wird eine minimale VCXPROJ-Datei dargestellt. Jede VCXPROJ-Datei, die von Visual Studio generiert wurde, enthält diese MSBuild-Elemente auf oberster Ebene, die in dieser Reihenfolge angezeigt werden (obwohl sie mehrere Kopien solcher Elemente auf oberster Ebene enthalten können). Beachten Sie, dass es sich bei `Label`-Attributen um beliebige Tags handelt, die nur von Visual Studio als Signposts für die Bearbeitung verwendet werden. Abgesehen davon haben sie keine weitere Funktion.

```xml
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns='http://schemas.microsoft.com/developer/msbuild/2003'>
   <ItemGroup Label="ProjectConfigurations" />
   <PropertyGroup Label="Globals" />
   <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
   <PropertyGroup Label="Configuration" />
   <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
   <ImportGroup Label="ExtensionSettings" />
   <ImportGroup Label="PropertySheets" />
   <PropertyGroup Label="UserMacros" />
   <PropertyGroup />
   <ItemDefinitionGroup />
   <ItemGroup />
   <Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
   <ImportGroup Label="ExtensionTargets" />
 </Project>
```

Im folgenden Abschnitt werden der Zweck jedes Elements sowie der Grund ihrer Reihenfolge beschrieben:

### <a name="project-element"></a>Project-Element

```xml
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns='http://schemas.microsoft.com/developer/msbuild/2003' >
```

`Project` ist der Stammknoten. Dieser gibt die zu verwendende MSBuild-Version und das Standardziel an, das ausgeführt werden soll, wenn die Datei an „MSBuild.exe“ übergeben wird.

### <a name="projectconfigurations-itemgroup-element"></a>ItemGroup-Element „ProjectConfigurations“

```xml
<ItemGroup Label="ProjectConfigurations" />
```

`ProjectConfigurations` enthält die Beschreibung der Projektkonfiguration. Beispiele dafür sind „Debug|Win32“, „Release|Win32“ und „Debug|ARM“. Viele Projekteigenschaften sind für eine bestimmte Konfiguration spezifisch. Sie legen beispielsweise Optimierungseigenschaften für einen Releasebuild, jedoch nicht für einen Debugbuild fest.

Die Elementgruppe `ProjectConfigurations` wird nicht zur Buildzeit verwendet. Die Visual Studio-IDE erfordert diese, um das Projekt zu laden. Diese Elementgruppe kann in eine PROPS-Datei verschoben und in die VCXPROJ-Datei importiert werden. In diesem Fall müssen Sie die PROPS-Datei jedoch manuell bearbeiten, wenn Sie Konfigurationen hinzufügen oder entfernen möchten. Sie können die IDE nicht verwenden.

### <a name="projectconfiguration-elements"></a>ProjectConfiguration-Elemente

In folgendem Codeausschnitt wird eine Projektkonfiguration dargestellt. In diesem Beispiel entspricht „Debug|x64“ dem Konfigurationsnamen. Der Konfigurationsname des Projekts muss im Format „$(Configuration)|$(Platform)“ vorliegen. Ein ProjectConfiguration-Knoten kann zwei Eigenschaften enthalten: Configuration und Platform. Diese Eigenschaften werden automatisch auf die hier angegebenen Werte festgelegt, wenn die Konfiguration aktiv ist.

   ```xml
   <ProjectConfiguration Include="Debug|x64">
     <Configuration>Debug</Configuration>
     <Platform>x64</Platform>
   </ProjectConfiguration>
   ```

Die IDE erwartet, eine Projektkonfiguration für eine beliebige Kombination der Werte von „Configuration“ und „Platform“ zu finden, die in allen ProjectConfiguration-Elementen verwendet werden. Dies bedeutet häufig, dass ein Projekt über bedeutungslose Projektkonfigurationen verfügt, um diese Anforderung zu erfüllen. Gehen Sie von einem Projekt mit folgenden Konfigurationen aus:

- Debug|Win32
- Retail|Win32
- Special 32-bit Optimization|Win32

Das Projekt muss dann ebenfalls diese Konfigurationen enthalten, obwohl „Special 32-bit Optimization“ für x64 nicht von Bedeutung ist:

- Debug|x64
- Retail|x64
- Special 32-bit Optimization|x64

Sie können die Build- und Bereitstellungsbefehle für alle Konfigurationen im **Konfigurations-Manager für Projektmappen** deaktivieren.

### <a name="globals-propertygroup-element"></a>PropertyGroup-Element „Globals“

```xml
 <PropertyGroup Label="Globals" />
```

`Globals` enthält Einstellungen auf Projektebene, z.B. „ProjectGuid“, „RootNamespace“ und „ApplicationType“ bzw. „ApplicationTypeRevision“. Die letzten beiden definieren häufig das Zielbetriebssystem. Ein Projekt kann nur ein einziges Betriebssystem anzielen, da Verweise und Projektelemente derzeit nicht mit Bedingungen versehen werden können. Diese Eigenschaften werden üblicherweise nicht an anderer Stelle in der Projektdatei überschrieben. Diese Gruppe ist nicht konfigurationsabhängig. Deshalb ist üblicherweise nur eine Globals-Gruppe in der Projektdatei vorhanden.

### <a name="microsoftcppdefaultprops-import-element"></a>Import-Element „Microsoft.Cpp.default.props“

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
```

Das Eigenschaftenblatt **Microsoft.Cpp.default.props** ist in Visual Studio enthalten und kann nicht geändert werden. Es enthält die Standardeinstellungen für das Projekt. Die Standardwerte hängen von „ApplicationType“ ab.

### <a name="configuration-propertygroup-elements"></a>PropertyGroup-Element „Configuration“

```xml
<PropertyGroup Label="Configuration" />
```

Eine `Configuration`-Eigenschaftengruppe besitzt eine angefügte Konfigurationsbedingung (z.B. `Condition=”'$(Configuration)|$(Platform)'=='Debug|Win32'”`) und liegt in mehreren Kopien (eine pro Konfiguration) vor. Diese Eigenschaftengruppe hostet die Eigenschaften, die für eine bestimmte Konfiguration festgelegt sind. Zu den Konfigurationseigenschaften zählt „PlatformToolset“. Außerdem steuern diese das Einschließen von Systemeigenschaftenblättern in **Microsoft.Cpp.props**. Wenn Sie beispielsweise die Eigenschaft `<CharacterSet>Unicode</CharacterSet>` definieren, wird das Systemeigenschaftenblatt **microsoft.Cpp.unicodesupport.props** eingeschlossen. Wenn Sie **Microsoft.Cpp.props** überprüfen, wird folgende Zeile angezeigt: `<Import Condition=”'$(CharacterSet)' == 'Unicode'”   Project=”$(VCTargetsPath)\microsoft.Cpp.unicodesupport.props”/>`

### <a name="microsoftcppprops-import-element"></a>Import-Element „Microsoft.Cpp.props“

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
```

Das Eigenschaftenblatt **Microsoft.Cpp.props** definiert die Standardwerte für viele toolspezifische Eigenschaften (direkt oder über Import), z.B. die Compilereigenschaften für die Optimierung oder Warnstufe oder die Eigenschaft „TypeLibraryName“ des MIDL-Tools. Außerdem werden je nachdem, welche Konfigurationseigenschaften in der Eigenschaftengruppe direkt oberhalb definiert sind, verschiedene Systemeigenschaftenblätter importiert.

### <a name="extensionsettings-importgroup-element"></a>ImportGroup-Element „ExtensionSettings“

```xml
<ImportGroup Label="ExtensionSettings" />
```

Die `ExtensionSettings`-Gruppe enthält Importe für die Eigenschaftenblätter, die Teil der Buildanpassungen sind. Eine Buildanpassung wird von bis zu drei Dateien definiert: einer TARGETS-Datei, einer PROPS-Datei und einer XML-Datei. Diese Importgruppe enthält die Importe für die PROPS-Datei.

### <a name="propertysheets-importgroup-elements"></a>ImportGroup-Element „PropertySheets“

```xml
<ImportGroup Label="PropertySheets" />
```

Die `PropertySheets`-Gruppe enthält die Importe für Benutzereigenschaftenblätter. Dabei handelt es sich um die Eigenschaftenblätter, die Sie über den Eigenschaften-Manager in Visual Studio hinzufügen. Die Reihenfolge, in der diese Importe aufgeführt werden, ist wichtig und wird im Eigenschaften-Manager dargestellt. Die Projektdatei enthält normalerweise mehrere Instanzen von dieser Art von Importgruppe (eine pro Projektkonfigurationen).

### <a name="usermacros-propertygroup-element"></a>PropertyGroup-Element „UserMacros“

```xml
<PropertyGroup Label="UserMacros" />
```

`UserMacros` enthält Eigenschaften, die Sie als Variablen erstellen, die zum Anpassen des Buildprozesses verwendet werden. Sie können beispielsweise ein Benutzermakro definieren, um den benutzerdefinierten Ausgabepfad als „$(CustomOutputPath)“ zu definieren und diesen dafür verwenden, andere Variablen zu definieren. Diese Eigenschaftengruppe enthält diese Eigenschaften. Beachten Sie, dass diese Gruppe in Visual Studio nicht in der Projektdatei aufgefüllt wird, da Visual C++ keine Benutzermakros unterstützt. Benutzermakros werden in Eigenschaftenblättern unterstützt.

### <a name="per-configuration-propertygroup-elements"></a>PropertyGroup-Elemente pro Konfiguration

```xml
<PropertyGroup />
```

Es gibt mehrere Instanzen dieser Eigenschaftengruppe: eine pro Konfiguration für alle Projektkonfigurationen. Jeder Eigenschaftengruppe muss eine Konfigurationsbedingung angefügt sein. Wenn eine Konfiguration fehlt, funktioniert das Dialogfeld **Projekteigenschaften** nicht ordnungsgemäß. Im Gegensatz zu den oben erwähnten Eigenschaftengruppen besitzt diese keine Bezeichnung. Diese Gruppe enthält Einstellungen auf Projektkonfigurationsebene. Diese Eigenschaften gelten für alle Dateien, die Teil der angegebenen Elementgruppe sind. Elementdefinitionsmetadaten für die Buildanpassung werden hier initialisiert.

Dieses PropertyGroup-Element muss nach `<Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />` stehen, außerdem darf kein anderes PropertyGroup-Element ohne Bezeichnung davor stehen (andernfalls funktioniert das Bearbeiten von Projekteigenschaften nicht ordnungsgemäß).

### <a name="per-configuration-itemdefinitiongroup-elements"></a>ItemDefinitionGroup-Elemente pro Konfiguration

```xml
 <ItemDefinitionGroup />
```

Enthält Elementdefinitionen. Diese müssen die gleichen Bedingungsregeln wie die PropertyGroup-Elemente pro Konfiguration ohne Bezeichnung befolgen.

### <a name="itemgroup-elements"></a>ItemGroup-Elemente

```xml
<ItemGroup />
```

Enthält die Elemente (z.B. Quelldateien) des Projekts. Für Projektelemente werden keine Bedingungen unterstützt (d.h. für Elementtypen, die durch Regeldefinitionen als Projektelemente behandelt werden).

Die Metadaten sollten Konfigurationsbedingungen für jede Konfiguration enthalten, auch wenn sie alle identisch sind. Zum Beispiel:

   ```xml
   <ItemGroup>
     <ClCompile Include="stdafx.cpp">
       <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">true</TreatWarningAsError>
       <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|x64’">true</TreatWarningAsError>
     </ClCompile>
   </ItemGroup>
   ```

Das Visual C++-Projektsystem unterstützt derzeit keine Platzhalter in Projektelementen.

   ```xml
   <ItemGroup>
     <ClCompile Include="*.cpp"> <!--Error-->
   </ItemGroup>
   ```

Das Visual C++-Projektsystem unterstützt derzeit keine Makros in Projektelementen.

   ```xml
   <ItemGroup>
     <ClCompile Include="$(IntDir)\generated.cpp"> <!--not guaranteed to work in all scenarios-->
   </ItemGroup>
   ```

Verweise werden in einem ItemGroup-Element angegeben und haben folgende Einschränkungen:

- Verweise unterstützten keine Bedingungen.
- Verweismetadaten unterstützten keine Bedingungen.

### <a name="microsoftcpptargets-import-element"></a>Import-Element „Microsoft.Cpp.targets“

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
```

Definiert Visual C++-Ziele (direkt oder über Importe), z.B. für das Erstellen oder Bereinigen.

### <a name="extensiontargets-importgroup-element"></a>ImportGroup-Element „ExtensionTargets“

```xml
<ImportGroup Label="ExtensionTargets" />
```

Diese Gruppe enthält Importe für die Zieldateien der Buildanpassung.

## <a name="impact-of-incorrect-ordering"></a>Auswirkungen einer falschen Reihenfolge

Die Visual Studio-IDE hängt von der Projektdatei ab, die die oben beschriebene Reihenfolge enthält. Wenn Sie beispielsweise einen Eigenschaftswert auf den Eigenschaftenseiten definieren, platziert die IDE die Eigenschaftsdefinition generell in der Eigenschaftengruppe mit der leeren Bezeichnung. Dadurch wird sichergestellt, dass die Standardwerte in Systemeigenschaftenblättern durch benutzerdefinierte Werte überschrieben werden. Auf ähnliche Weise werde Zieldateien am Ende importiert, da diese die Eigenschaftendefinitionen über ihnen verwenden und in der Regel keine Eigenschaften definieren. Ebenso werden Benutzereigenschaftenblätter nach den Systemeigenschaftenblättern importiert (über **Microsoft.Cpp.props**). Dadurch wird sichergestellt, dass der Benutzer alle Standardwerte in den Systemeigenschaftenblättern überschreiben kann.

Wenn die VCXPROJ-Datei nicht diesem Layout entspricht, entsprechen die Buildergebnisse möglicherweise nicht Ihren Erwartungen. Wenn Sie beispielsweise versehentlich ein Systemeigenschaftenblatt nach dem Benutzereigenschaftenblatt importieren, werden die Benutzereinstellungen von den Systemeigenschaftenblättern überschrieben.

Auch die Entwurfszeitumgebung der IDE hängt teilweise von der richtigen Reihenfolge der Elemente ab. Wenn Ihre VCXPROJ-Datei beispielsweise nicht die Importgruppe `PropertySheets` enthält, kann die IDE möglicherweise nicht bestimmen, wo das neue Eigenschaftenblatt platziert werden soll, das der Benutzer im **Eigenschaften-Manager** erstellt hat. Dies kann dazu führen, dass ein Benutzereigenschaftenblatt von einem Systemeigenschaftenblatt überschrieben wird. Die Heuristik, die von der IDE verwendet wird, toleriert kleinere Inkonsistenzen im Layout der VCXPROJ-Datei. Es wird jedoch dringend empfohlen, nicht von der Struktur abzuweichen, die in diesem Artikel erläutert wurde.

## <a name="how-the-ide-uses-element-labels"></a>Verwendung von Elementbezeichnungen durch die IDE

Wenn Sie in der IDE die Eigenschaft **UseOfAtl** auf der allgemeinen Eigenschaftenseite festlegen, wird diese in die Eigenschaftengruppe „Configuration“ in der Projektdatei geschrieben, während die Eigenschaft **TargetName** auf derselben Eigenschaftenseite in die Eigenschaftengruppe ohne Bezeichnung, die pro Konfiguration gilt, geschrieben wird. Visual Studio sucht in der XML-Datei der Eigenschaftenseite nach Informationen dazu, wohin jede Eigenschaft geschrieben werden soll. Für die Eigenschaftenseite **General** (Allgemein) (wenn Sie die englischsprachige Version von Visual Studio Enterprise Edition verwenden) entspricht diese Datei `%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033\general.xml`. Die XML-Regeldatei der Eigenschaftenseite definiert die statischen Informationen einer Regel und deren Eigenschaften. Eine dieser Informationen ist die bevorzugte Position einer Regeleigenschaft in der Zieldatei (die Datei, in die deren Wert geschrieben wird). Die bevorzugte Position wird vom Label-Attribut in den Elementen der Projektdatei angegeben.

## <a name="property-sheet-layout"></a>Layout von Eigenschaftenblättern

Der folgende XML-Codeausschnitt stellt das minimale Layout einer Eigenschaftenblattdatei (.props) dar. Es ähnelt dem einer VCXPROJ-Datei, und die Funktionalität der PROPS-Elemente wurde zuvor erläutert.

```xml
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ImportGroup Label="PropertySheets" />
  <PropertyGroup Label="UserMacros" />
  <PropertyGroup />
  <ItemDefinitionGroup />
  <ItemGroup />
</Project>
```

Kopieren Sie eine der PROPS-Dateien in den Ordner „VCTargets“, und passen Sie diese an Ihre Anforderungen an, um ein eigenes Eigenschaftenblatt zu erstellen. Für Visual Studio 2017 Enterprise Edition ist der Standardpfad von VCTargets `%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets`.

## <a name="see-also"></a>Siehe auch

[Arbeiten mit Projekteigenschaften](working-with-project-properties.md)  
[Eigenschaftenseite: XML-Dateien](property-page-xml-files.md)  
