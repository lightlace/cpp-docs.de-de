---
title: VCXPROJ und props-Dateistruktur | Microsoft Docs
ms.custom: 
ms.date: 04/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: .vcxproj file structure
ms.assetid: 14d0c552-29db-480e-80c1-7ea89d6d8e9c
caps.latest.revision: "1"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d48b16d9a4250de8c8c3dfef62fdcfb5c1434960
ms.sourcegitcommit: 6f40bba1772a09ff0e3843d5f70b553e1a15ab50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="vcxproj-and-props-file-structure"></a>VCXPROJ und PROPS-Datei-Struktur

MSBuild ist das Standard-Projektsystem in Visual Studio. Bei Auswahl **Datei | Neues Projekt** in Visual C++, die Sie Erstellen eines MSBuild-Projekts, deren Einstellungen werden gespeichert, in eine XML-Projektdatei mit der Erweiterung `.vcxproj`. Die Projektdatei kann auch importieren, props- und TARGETS-Dateien, in denen Einstellungen gespeichert werden können. In den meisten Fällen müssen Sie niemals die Projektdatei manuell bearbeiten, und in der Tat Sie sollte nicht manuell bearbeiten, wenn Sie ein gutes Verständnis von MSBuild verfügen. Nach Möglichkeit sollten Sie die Eigenschaftenseiten für Visual Studio verwenden, um die projekteinstellungen ändern (siehe [arbeiten mit Projekteigenschaften](working-with-project-properties.md). In einigen Fällen müssen Sie jedoch einem Projekt Datei oder ein Eigenschaftenblatt manuell ändern. Für die Fälle enthält in diesem Artikel grundlegende Informationen zur Struktur der Datei.

**Wichtig:**

Bei Auswahl eine .vcxproj-Datei manuell bearbeiten, achten Sie darauf, dass Sie diese Fakten:

1. Die Struktur der Datei muss eine vorgeschriebenen Form folgen, die in diesem Artikel beschrieben wird.

1. Das Visual C++-Projektsystem unterstützt derzeit keine Platzhalter in Projektelementen. Dies wird z. B. nicht unterstützt:

   ```xml
   <ClCompile Include="*.cpp"/>
   ```

1. Das Visual C++-Projektsystem unterstützt derzeit nicht Makros in Project Item Pfaden. Dies wird z. B. nicht unterstützt:

   ```xml
   <ClCompile Include="$(IntDir)\generated.cpp"/>
   ```

1. Um Projekteigenschaften ordnungsgemäß hinzugefügt, entfernt oder geändert werden, wenn im bearbeitet haben die **Projekteigenschaften** im Dialogfeld die Datei muss getrennte Gruppen für jede Projektkonfiguration enthalten, und die Bedingungen in dieser Form sein:

   ```xml
   Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'"
   ```

1. Jede Eigenschaft muss in der Gruppe mit den richtigen Bezeichnung, entsprechend den Angaben in der Regel Eigenschaftendatei angegeben werden. Weitere Informationen finden Sie unter [Eigenschaft Auslagerungsdateien XML-Regel](property-page-xml-files.md).

## <a name="vcxproj-file-elements"></a>die Elemente der VCXPROJ-Datei

Sie können den Inhalt der VCXPROJ-Datei mit einem beliebigen Text oder XML-Editor prüfen. Sie können es in Visual Studio anzeigen, indem Sie mit der rechten Maustaste auf das Projekt im Projektmappen-Explorer auswählen **Projekt entladen** auswählen und dann **Foo.vcxproj bearbeiten**.

Als erstes beachtet wird, dass die Elemente der obersten Ebene in einer bestimmten Reihenfolge angezeigt werden. Beispiel:

- Die meisten Eigenschaftengruppen und Elementdefinitionsgruppen werden nach dem Import für Microsoft.Cpp.Default.props auftreten.
- alle Ziele werden am Ende der Datei importiert.
- Es gibt mehrere Eigenschaftengruppen, jeweils über eine eindeutige Bezeichnung, und sie in einer bestimmten Reihenfolge auftreten.

Die Reihenfolge der Elemente in der Projektdatei ist sehr wichtig, weil MSBuild für ein Modell für die sequenzielle Auswertung basiert.  Wenn mehrere Definitionen einer Eigenschaft der Projektdatei, einschließlich aller importierten props und TARGETS-Dateien besteht, überschreibt die letzte Definition die vorherigen Konfigurationen an. Im folgenden Beispiel wird der Wert "Xyz" während der Kompilierung festgelegt werden, da die MSBUild-engine-stößt er zuletzt bei der Auswertung.

```xml
  <MyProperty>abc</MyProperty>
  <MyProperty>xyz</MyProperty>
```

Der folgende Codeausschnitt zeigt eine minimale VCXPROJ-Datei. Alle VCXPROJ-Datei, die von Visual Studio generiert diese MSBuild-Elemente der obersten Ebene enthält, und sie in dieser Reihenfolge angezeigt werden (obwohl sie mehrere Kopien jeder solche Element der obersten Ebene enthalten können). Beachten Sie, dass `Label` Attribute sind beliebige Tags, die nur von Visual Studio als Signposts für die Bearbeitung verwendet werden; sie haben keine anderen Funktion.

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

In den folgenden Abschnitten wird beschrieben, den Zweck jedes dieser Elemente und warum sie auf diese Weise angeordnet sind:

### <a name="project-element"></a>Project-element

```xml
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns='http://schemas.microsoft.com/developer/msbuild/2003' >
```

`Project`ist der Stammknoten. Gibt die MSBuild-Version verwendet und auch das Standardziel, der ausgeführt werden, wenn diese Datei an MSBuild.exe übergeben wird.

### <a name="projectconfigurations-itemgroup-element"></a>ProjectConfigurations ItemGroup-element

```xml
<ItemGroup Label="ProjectConfigurations" />
```

`ProjectConfigurations`enthält die Beschreibung der Projekt-Konfiguration. Beispiele sind Debug | Win32, Version | Win32, Debug | ARM und So weiter. Viele Einstellungen für Projektdateien sind spezifisch für eine bestimmte Konfiguration. Beispielsweise werden Sie wahrscheinlich Optimierung Eigenschaften für ein Releasebuild erstellt werden, aber nicht in einem Debugbuild festlegen möchten.

Die `ProjectConfigurations` Elementgruppe dient nicht zur Buildzeit. Der Visual Studio-IDE erfordert es, um das Projekt zu laden. Diese Elementgruppe werden in eine PROPS-Datei verschoben und in der VCXPROJ-Datei importiert. Allerdings in diesem Fall, müssen wenn Sie müssen zum Hinzufügen oder Entfernen von Konfigurationen, Sie manuell PROPS-Datei bearbeiten; Sie können keine die IDE.

### <a name="projectconfiguration-elements"></a>ProjectConfiguration Elemente

Der folgende Codeausschnitt zeigt eine Projektkonfiguration. In diesem Beispiel "Debug | X 64' ist der Konfigurationsname. Den Namen der Projektkonfiguration muss in das Format $(Configuration)|$(Platform). sein. Ein Projektkonfiguration-Knoten kann zwei Eigenschaften haben: Konfiguration und Plattform. Diese Eigenschaften werden automatisch festgelegt werden, mit den Werten, die hier angegeben werden, wenn die Konfiguration aktiv ist.

   ```xml
   <ProjectConfiguration Include="Debug|x64">
     <Configuration>Debug</Configuration>
     <Platform>x64</Platform>
   </ProjectConfiguration>
   ```

Die IDE davon ausgeht, eine Projektkonfiguration für eine beliebige Kombination der Werte für Konfiguration und Plattform in alle ProjectConfiguration Elemente verwendet. Dies bedeutet häufig, dass ein Projekt bedeutungslos Projektkonfigurationen, um diese Anforderung zu erfüllen haben kann. Z. B. wenn ein Projekt mit diesen Konfigurationen enthält:

- Debuggen | Win32
- Retail | Win32
- Spezielle 32-Bit-Optimierung | Win32

dann muss es auch diese Konfigurationen aufweisen, obwohl "Besondere 32-Bit-Optimierung" ohne Bedeutung für X64 ist:

- Debuggen|x64
- Retail|x64
- Spezielle 32-Bit-Optimierung | X64

Sie deaktivieren den Build erstellen und Bereitstellen von Befehle für jede Konfiguration in der **Solution Configuration Manager**.

### <a name="globals-propertygroup-element"></a>Globals PropertyGroup-element

```xml
 <PropertyGroup Label="Globals" />
```

`Globals`enthält Einstellungen wie z. B. ProjectGuid RootNamespace und Anwendungstyp für Projekt / "applicationtyperevision". Die letzten zwei definieren häufig Zielbetriebssystem. Ein Projekt kann nur eine einzelne OS abzielen, Verweise und Projektelementen derzeit Bedingungen haben können. Diese Eigenschaften werden in der Regel nicht an anderer Stelle in der Projektdatei überschrieben. Diese Gruppe ist nicht die konfigurationsabhängigen daher in der Regel nur ein Globals vorhanden ist und in der Projektdatei.

### <a name="microsoftcppdefaultprops-import-element"></a>Import von Microsoft.Cpp.default.props-element

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
```

Die **Microsoft.Cpp.default.props** Eigenschaftenblatt im Lieferumfang von Visual Studio und kann nicht geändert werden. Es enthält die Standardeinstellungen für das Projekt. Die Standardwerte variieren abhängig von den Anwendungstyp für.

### <a name="configuration-propertygroup-elements"></a>PropertyGroup-Konfigurationselemente

```xml
<PropertyGroup Label="Configuration" />
```

Ein `Configuration` Eigenschaftengruppe weist eine Bedingung auf angefügten Konfiguration (z. B. `Condition=”'$(Configuration)|$(Platform)'=='Debug|Win32'”`) und mehrere Kopien einer Konfiguration pro eingeht. Dieser Eigenschaftengruppe hostet die Eigenschaften, die für eine bestimmte Konfiguration festgelegt werden. Konfigurationseigenschaften PlatformToolset enthalten und auch steuern, die Aufnahme der Eigenschaftenblätter im System **Element "Microsoft.cpp.props"**. Angenommen, Sie definieren, dass die Eigenschaft `<CharacterSet>Unicode</CharacterSet>`, klicken Sie dann das Systemeigenschaftenblatt **Microsoft. Cpp.unicodesupport.props** einbezogen. Wenn Sie überprüfen **Element "Microsoft.cpp.props"**, sehen Sie die Zeile: `<Import Condition=”'$(CharacterSet)' == 'Unicode'”   Project=”$(VCTargetsPath)\microsoft.Cpp.unicodesupport.props”/>`.

### <a name="microsoftcppprops-import-element"></a>Element "Microsoft.cpp.props" Import-element

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
```

Die **Element "Microsoft.cpp.props"** Eigenschaftenblatt (direkt oder über Importe) die Standardwerte für viele toolspezifische Eigenschaften wie der Compiler, Optimierung und Warnstufe Eigenschaften, die MIDL-Tool TypeLibraryName definiert. Eigenschaft, und So weiter. Er importiert auch verschiedene System Eigenschaftenblätter basierend auf der Konfigurationseigenschaften in der Eigenschaftengruppe direkt oberhalb definiert sind.

### <a name="extensionsettings-importgroup-element"></a>ExtensionSettings ImportGroup-element

```xml
<ImportGroup Label="ExtensionSettings" />
```

Die `ExtensionSettings` Gruppe enthält Importe für die Eigenschaftenseiten, die Bestandteil von Anpassungen zu erstellen sind. Eine Buildanpassung wird definiert, indem bis zu drei Dateien: einer TARGETS-Datei, eine PROPS-Datei und einer XML-Datei. Dieser Importgruppe enthält die Importe PROPS-Datei.

### <a name="propertysheets-importgroup-elements"></a>PropertySheets ImportGroup-Elemente

```xml
<ImportGroup Label="PropertySheets" />
```

Die `PropertySheets` Gruppe enthält die Importe für Benutzereigenschaftenblätter. Hierbei handelt es sich um die Eigenschaftenseiten, die Sie über die Eigenschaften-Manager-Sicht in Visual Studio hinzufügen. Die Reihenfolge, in der diese Importe aufgeführt sind, ist wichtig, und im Eigenschaften-Manager wiedergegeben. Die Projektdatei enthält in der Regel mehrere Instanzen dieser Art von Importgruppe, eine für jede Projektkonfiguration.

### <a name="usermacros-propertygroup-element"></a>UserMacros PropertyGroup-element

```xml
<PropertyGroup Label="UserMacros" />
```

`UserMacros`enthält Eigenschaften, die Sie erstellen, wie Variablen, die zum Anpassen des Buildprozesses verwendet werden. Beispielsweise können Sie ein Benutzermakro für Ihrer benutzerdefinierten Ausgabepfad als $(CustomOutputPath) definieren und verwenden, um andere Variablen definieren, definieren. Diese Eigenschaftengruppe enthält diese Eigenschaften. Beachten Sie, dass in Visual Studio diese Gruppe nicht in der Projektdatei aufgefüllt wird, da Visual C++ Benutzermakros für Konfigurationen nicht unterstützt. Benutzermakros werden in Eigenschaftenblätter unterstützt.

### <a name="per-configuration-propertygroup-elements"></a>PropertyGroup-Elementen pro-Konfiguration

```xml
<PropertyGroup />
```

Es gibt mehrere Instanzen dieser Eigenschaftengruppe, einen pro-Konfiguration für alle Projektkonfigurationen. Jede Eigenschaftsgruppe muss eine einzige Konfiguration Bedingung angefügt haben. Wenn alle Konfigurationen fehlen, werden die **Projekteigenschaften** Dialogfeld funktioniert nicht ordnungsgemäß. Im Gegensatz zu den oben genannten Eigenschaftengruppen muss hierbei keine Bezeichnung. Diese Gruppe enthält Einstellungen für Projektdateien Konfigurationsebene an. Diese Einstellungen gelten für alle Dateien, die Teil der angegebenen Elementgruppe festgelegt sind. Anpassung Element Builddefinition Metadaten hier initialisiert wird.

Diese PropertyGroup muss nach stammen `<Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />` und es muss keine andere PropertyGroup ohne Bezeichnung davor (andernfalls Projekteigenschaften bearbeiten funktioniert nicht ordnungsgemäß).

### <a name="per-configuration-itemdefinitiongroup-elements"></a>Konfigurationsspezifischen ItemDefinitionGroup-Elemente

```xml
 <ItemDefinitionGroup />
```

Enthält die Elementdefinitionen. Diese müssen es sich um den gleichen Bedingungen Regeln als Bezeichnung weniger konfigurationsspezifischen PropertyGroup-Elementen entsprechen.

### <a name="itemgroup-elements"></a>ItemGroup-Elementen

```xml
<ItemGroup />
```

Enthält die Elemente im Projekt (Quelldateien usw.). Bedingungen werden nicht unterstützt, für die Projektelemente (d. h. Elementtypen wie Projektelemente durch Regeln Definitionen behandelt werden).

Die Metadaten sollten Configuration-Bedingungen für jede Konfiguration verfügen, auch wenn sie alle identisch sind. Beispiel:

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

Das Visual C++-Projektsystem unterstützt derzeit nicht Makros in Projektelementen.

   ```xml
   <ItemGroup>
     <ClCompile Include="$(IntDir)\generated.cpp"> <!--not guaranteed to work in all scenarios-->
   </ItemGroup>
   ```

Verweise in einem ItemGroup-Element angegeben werden, und sie weisen diese Einschränkungen:

- Bedingungen unterstützt Verweise nicht.
- Verweist auf Metadaten Bedingungen nicht unterstützt.

### <a name="microsoftcpptargets-import-element"></a>Microsoft.Cpp.targets Import-element

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
```

Definiert (direkt oder über Importe) Visual C++-Ziele, wie z. B. erstellen, fehlerfreien usw.

### <a name="extensiontargets-importgroup-element"></a>ExtensionTargets ImportGroup-element

```xml
<ImportGroup Label="ExtensionTargets" />
```

Diese Gruppe enthält Importe für die Buildanpassung TARGETS-Dateien.

## <a name="impact-of-incorrect-ordering"></a>Auswirkungen der falschen Reihenfolge

Der Visual Studio-IDE, hängt davon ab, der Project Datei having, die die Reihenfolge, die oben beschrieben. Wenn Sie einen Eigenschaftswert auf den Eigenschaftenseiten definieren, wird z. B. die Eigenschaftsdefinition von die IDE in der Regel in der Eigenschaftengruppe mit der Bezeichnung leer platzieren. Dadurch wird sichergestellt, dass die Standardwerte in den Eigenschaftenblättern System geschaltet von benutzerdefinierten Werten überschrieben werden. Auf ähnliche Weise werden die Zieldateien am Ende importiert, da sie die zuvor definierten Eigenschaften zu nutzen, und sie in der Regel keine Eigenschaften selbst definieren. Ebenso werden Benutzereigenschaftenblätter nach System-Eigenschaftenblätter importiert (über enthalten **Element "Microsoft.cpp.props"**). Dadurch wird sichergestellt, dass der Benutzer alle Standardwerte, die durch das System Eigenschaftenblätter geschaltet überschreiben kann.

Wenn VCXPROJ-Datei keine dieses Layout befolgt, die Buildergebnissen möglicherweise nicht Ihren Erwartungen. Wenn Sie versehentlich ein Systemeigenschaftenblatt nach der vom Benutzer definierten Eigenschaftenblätter importiert haben, werden z. B. die benutzereinstellungen durch den System-Eigenschaftenblätter überschrieben werden.

Auch die IDE entwurfszeitumgebung hängt zum Teil auf richtige Reihenfolge der Elemente. Beispielsweise verfügt die VCXPROJ-Datei nicht das `PropertySheets` Gruppe importieren, die IDE möglicherweise nicht in der Lage, platzieren Sie ein neues Eigenschaftenblatt zu bestimmen, die der Benutzer, in erstellt hat **Eigenschaften-Manager**. Dies kann zu einem Benutzer Blatt wird außer Kraft gesetzte durch ein Blatt System führen. Obwohl die Heuristik, die von der IDE verwendeten kleinere Inkonsistenzen in das Layout der VCXPROJ-Datei tolerieren kann, wird dringend empfohlen, nicht aus der Struktur, die weiter oben in diesem Artikel angezeigten abweichen.

## <a name="how-the-ide-uses-element-labels"></a>Verwendungsweise von Element Bezeichnungen in die IDE

In der IDE beim Festlegen der **UseOfAtl** -Eigenschaft in der Eigenschaftenseite Allgemein, er bezieht sich auf die Konfigurationsgruppe für die Eigenschaft in der Projektdatei, während die **TargetName** Eigenschaft in der gleichen Eigenschaftenseite wird in der Eigenschaftengruppe Bezeichnung weniger konfigurationsspezifischen geschrieben. Visual Studio sucht auf der Eigenschaftenseite XML-Datei für die Informationen dazu, wo jede Eigenschaft schreiben. Für die **allgemeine** Eigenschaftenseite (vorausgesetzt, Sie haben eine englischsprachige Version von Visual Studio Enterprise Edition), wird diese Datei `%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033\general.xml`. Die XML-Regel-Datei definiert die statische Informationen zu einer Regel, und alle zugehörigen Eigenschaften. Ein Teil der Informationen ist die bevorzugte Position der einer Regeleigenschaft in der Zieldatei (die Datei, in dem der Wert geschrieben wird). Die bevorzugte Position wird durch das Attribut "Bezeichnung" für die Elemente der Projekt-Datei angegeben.

## <a name="property-sheet-layout"></a>Eigenschaftenblatt layout

Der folgende XML-Ausschnitt ist eine minimale Layout der Eigenschaftenblattdatei (props-Format). Sie ähnelt damit VCXPROJ-Datei, und die Funktionalität der props-Elemente aus der früheren Diskussion abgeleitet werden kann.

```xml
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ImportGroup Label="PropertySheets" />
  <PropertyGroup Label="UserMacros" />
  <PropertyGroup />
  <ItemDefinitionGroup />
  <ItemGroup />
</Project>
```

Um eine eigene Eigenschaftenblatt zu machen, kopieren Sie den PROPS-Dateien im Ordner "VCTargets", und ändern Sie ihn für Ihre Zwecke. Für Visual Studio 2017 Enterprise Edition verwendet wird, ist der Standardpfad für die VCTargets `%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets`.

## <a name="see-also"></a>Siehe auch

[Arbeiten mit Projekteigenschaften](working-with-project-properties.md)  
[Eigenschaftenseite: XML-Dateien](property-page-xml-files.md)  
