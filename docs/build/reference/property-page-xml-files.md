---
title: XML-Regeldateien für Eigenschaftenseiten
ms.date: 05/06/2019
helpviewer_keywords:
- property page XML files
ms.assetid: dd9d9734-4387-4098-8ba6-85b93507731d
ms.openlocfilehash: 76378dc5ef9d7443045c329579cfa3c410dc262f
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630746"
---
# <a name="property-page-xml-rule-files"></a>XML-Regeldateien für Eigenschaftenseiten

Die Eigenschaftenseiten eines Projekts in der IDE werden durch XML-Dateien im Ordner „VCTargets“ konfiguriert. Der genaue Pfad hängt davon ab, welche Edition(en) von Visual Studio installiert ist bzw. sind und welche Produktsprache verwendet wird. Wenn Visual Studio 2019 Enterprise Edition auf Englisch verwendet wird, entspricht der Pfad `%ProgramFiles%\Microsoft Visual Studio\2019\Enterprise\Common7\IDE\VC\VCTargets\1033`. Die XML-Datei beschreibt die Namen der Regeln, Kategorien und der einzelnen Eigenschaften sowie deren Datentyp, Standardwerte und wie sie angezeigt werden sollen. Wenn Sie eine Eigenschaft in der IDE festlegen, wird der neue Wert in der Projektdatei gespeichert.

Die einzigen Szenarios, für die Sie die interne Funktionsweise dieser Dateien und der Visual Studio-IDE kennen müssen, sind das Erstellen einer benutzerdefinierten Eigenschaftenseite oder das Anpassen von Projekteigenschaften auf andere Art als über die Visual Studio-IDE.

Öffnen Sie zunächst die Eigenschaftenseiten eines Projekts. Klicken Sie hierzu mit der rechten Maustaste auf den Projektknoten im **Projektmappen-Explorer**, und wählen Sie „Eigenschaften“ aus.

![Visual Studio C++-Projekteigenschaften](../media/cpp-property-page-2017.png)

Jeder Knoten unter **Konfigurationseigenschaften** wird als „Regel“ bezeichnet. Eine Regel stellt manchmal ein einzelnes Tool (z.B. den Compiler) dar. Im Allgemeinen bezieht sich der Begriff jedoch darauf, dass ein Element über Eigenschaften verfügt, ausgeführt werden und Ausgaben erzeugen kann. Jede Regel wird über eine XML-Datei im Ordner „VCTargets“ aufgefüllt. Die angezeigte C/C++-Regel wird beispielsweise über „cl.xml“ aufgefüllt.

Wie zuvor erwähnt besitzt jede Regel mehrere Eigenschaften, die in Kategorien organisiert sind. Jeder Unterknoten einer Regel stellt eine Kategorie dar. Der Knoten „Optimierung“ unter „C/C++“ enthält beispielsweise alle Eigenschaften des Compilertools, mit denen Optimierungen vorgenommen werden können. Die Eigenschaften und deren Werte werden in einem Rasterformat im rechten Bereich gerendert.

Sie können „cl.xml“ im Editor oder in einem beliebigen XML-Editor (siehe Screenshot) öffnen. Es wird ein Stammknoten namens „Rule“ (Regel) angezeigt, der die gleiche Liste von definierten Eigenschaften enthält, die auch auf der Benutzeroberfläche angezeigt wird, jedoch mit zusätzlichen Metadaten.

```xml
<?xml version="1.0" encoding="utf-8"?>
<!--Copyright, Microsoft Corporation, All rights reserved.-->
<Rule Name="CL" PageTemplate="tool" DisplayName="C/C++" SwitchPrefix="/" Order="10" xmlns="http://schemas.microsoft.com/build/2009/properties" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <Rule.Categories>
    <Category Name="General" DisplayName="General" />
    <Category Name="Optimization" DisplayName="Optimization" />
    <Category Name="Preprocessor" DisplayName="Preprocessor" />
    <Category Name="Code Generation" DisplayName="Code Generation" />
    <Category Name="Language" DisplayName="Language" />
    <Category Name="Precompiled Headers" DisplayName="Precompiled Headers" />
    <Category Name="Output Files" DisplayName="Output Files" />
    <Category Name="Browse Information" DisplayName="Browse Information" />
    <Category Name="Advanced" DisplayName="Advanced" />
    <Category Name="All Options" DisplayName="All Options" Subtype="Search" />
    <Category Name="Command Line" DisplayName="Command Line" Subtype="CommandLine" />
  </Rule.Categories>
...
```

Jedem Knoten unter „Konfigurationseigenschaften“ auf der Benutzeroberfläche der Eigenschaftenseiten ist eine XML-Datei zugeordnet. Sie können Regeln über die Benutzeroberfläche hinzufügen oder entfernen, indem Sie Speicherorte zu den entsprechenden XML-Dateien im Projekt hinzufügen oder aus diesen entfernen. So fügt „Microsoft.CppBuild.targets“ (eine Ebene über dem Ordner „1033“) die Datei „cl.xml“ ein:

```xml
<PropertyPageSchema Condition="'$(ConfigurationType)' != 'Utility'" Include="$(VCTargetsPath)$(LangID)\cl.xml"/>
```

Wenn Sie alle Daten aus „cl.xml“ entfernen, verbleibt folgendes Gerüst:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Rule>
  <Rule.DataSource />
  <Rule.Categories>
    <Category />
        ...
  </Rule.Categories>
  <BoolProperty />
  <EnumProperty />
  <IntProperty />
  <StringProperty />
  <StringListProperty />
</Rule>
```

Im folgenden Abschnitt werden die Hauptelemente und einige der Metadaten beschrieben, die an diese angefügt werden können.

1. **Rule:**  Bei „Rule“ handelt es sich im Allgemeinen um den Stammknoten der XML-Datei. Dieser kann mehrere Attribute enthalten:

    ```xml
    <Rule Name="CL" PageTemplate="tool" SwitchPrefix="/" Order="10"
              xmlns="http://schemas.microsoft.com/build/2009/properties"
              xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
              xmlns:sys="clr-namespace:System;assembly=mscorlib">
      <Rule.DisplayName>
        <sys:String>C/C++</sys:String>
      </Rule.DisplayName>
    ```

   a. **Name:** Das Name-Attribut ist eine ID für die Regel. Es muss in allen XML-Dateien der Projektseiten eines Projekts eindeutig sein.

   b. **PageTemplate:** Der Wert dieses Attributs wird von der Benutzeroberfläche verwendet, um eine Auswahl aus mehreren Vorlagen für die Benutzeroberfläche zu treffen. Die Vorlage „tool“ rendert die Eigenschaften in einem Standardrasterformat. Weitere integrierte Werte für dieses Attribut sind „debugger“ und „generic“. Betrachten Sie die Knoten „Debuggen“ und „Allgemein“, um zu sehen, welches Format sich für die Benutzeroberfläche ergibt, wenn Sie diese Werte festlegen. Die Benutzeroberfläche für die Seitenvorlage „Debugger“ verwendet ein Dropdownfeld, um zwischen den Eigenschaften von verschiedenen Debuggern zu wechseln, während die Vorlage „generic“ verschiedene Eigenschaftenkategorien auf einer Seite anzeigt, statt mehrere Kategorien in den Unterknoten der Regel anzuzeigen. Bei diesem Attribut handelt es sich lediglich um einen Vorschlag für die Benutzeroberfläche. Die XML-Datei wurde dafür entworfen, unabhängig von der Benutzeroberfläche zu sein. Eine andere Benutzeroberfläche verwendet dieses Attribut möglicherweise für andere Zwecke.

   c. **SwitchPrefix:** Dieses Präfix wird in der Befehlszeile für die Parameter verwendet. Ein Wert von „/“ ergibt Parameter wie „/ZI“, „/nologo“ oder „/W3“.

   d. **Order:** Hierbei handelt es sich um einen Vorschlag für einen möglichen Benutzeroberflächenclient am relativen Speicherort dieser Regel im Vergleich mit allen anderen Regeln im System.

   e. **xmlns:** Hierbei handelt es sich um ein XAML-Standardelement. Drei Namespaces werden aufgeführt. Diese entsprechen den Namespaces für die XAML-Deserialisierungsklassen, das XAML-Schema und insbesondere den XAML-Systemnamespace.

   f. **DisplayName:** Dieser Name wird auf der Benutzeroberfläche der Eigenschaftenseite des Knotens „Rule“ (Regel) angezeigt. Dieser Wert wird lokalisiert. „DisplayName“ wurde aufgrund der internen Anforderungen von Lokalisierungstools als untergeordnetes Element von „Rule“ statt als Attribut erstellt (wie „Name“ oder „SwitchPrefix“). Für XAML sind diese gleichwertig. Sie können deshalb ein Attribut daraus erstellen, um die Übersichtlichkeit zu verbessern, oder keine Änderung vornehmen.

   g. **DataSource:** Diese Eigenschaft ist sehr wichtig, da Sie dem Projektsystem mitteilt, an welchem Speicherort der Projektwert gelesen und gespeichert werden soll und wie dieser gruppiert wird. Dies wird im Folgenden erläutert. Für „cl.xml“ sind diese Werte Folgende:

      ```xml
      <DataSource Persistence="ProjectFile" ItemType="ClCompile" Label="" HasConfigurationCondition="true" />
      ```

   - `Persistence="ProjectFile` teilt dem Projektsystem mit, dass alle Eigenschaften von „Rule“ in die Projektdatei oder in die Eigenschaftenblattdatei (je nachdem, welcher Knoten zum Erzeugen der Eigenschaftenseiten verwendet wurde) geschrieben werden sollen. Ein weiterer möglicher Wert ist „UserFile“. Dieser schreibt den Wert in die USER-Datei.

   - `ItemType="ClCompile"` gibt an, dass die Eigenschaften als ItemDefinition-Metadaten oder als Elementmetadaten (nur, wenn die Eigenschaftenseiten aus einem Dateiknoten im Projektmappen-Explorer erzeugt wurden) dieses Elementtyps gespeichert werden. Wenn dieses Feld nicht festgelegt ist, wird die Eigenschaft als allgemeine Eigenschaft in ein PropertyGroup-Element geschrieben.

   - `Label=""` gibt an, dass die Bezeichnung des übergeordneten Elements „ItemDefinitionGroup“ leer ist (jedes MSBuild-Element kann eine Bezeichnung besitzen), wenn die Eigenschaften als `ItemDefinition`-Metadaten geschrieben werden. Visual Studio 2017 und höher verwendet Gruppen mit Bezeichnung, um in der VCXPROJ-Projektdatei zu navigieren. Beachten Sie, dass die Gruppen, die die meisten Rule-Eigenschaften enthalten, über eine leere Zeichenfolge als Bezeichner verfügen.

   - `HasConfigurationCondition="true"` weist das Projektsystem an, eine Konfigurationsbedingung an den Wert anzufügen, damit dieser nur für die aktuelle Projektkonfiguration wirksam ist. Die Konfiguration kann an die übergeordnete Gruppe oder an den Wert angefügt werden. Öffnen Sie beispielsweise die Projektseiten über den Projektknoten, und legen Sie den Wert der Eigenschaft **Warnungen als Fehler behandeln** unter **Konfigurationseigenschaften > C/C++ > Allgemein** auf „Ja“ fest. Der folgende Wert wird in die Projektdatei geschrieben. Beachten Sie die Konfigurationsbedingung, die an das übergeordnete Element „ItemDefinitionGroup“ angefügt ist.

      ```xml
      <ItemDefinitionGroup Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">
        <ClCompile>
          <TreatWarningAsError>true</TreatWarningAsError>
        </ClCompile>
      </ItemDefinitionGroup>
      ```

      Wenn dieser Wert auf der Eigenschaften Seite für eine bestimmte Datei, wie z. b. stdafx. cpp, festgelegt wurde, wird der Eigenschafts Wert unter dem Element *stdafx. cpp* in der Projektdatei geschrieben, wie unten gezeigt. Sie werden feststellen, dass die Konfigurationsbedingung direkt an die Metadaten angefügt wurde.

      ```xml
      <ItemGroup>
        <ClCompile Include="stdafx.cpp">
          <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">true</TreatWarningAsError>
        </ClCompile>
      </ItemGroup>
      ```

   Ein weiteres Attribut von **DataSource**, das zuvor nicht aufgelistet wurde, ist **PersistedName**. Sie können dieses Attribut verwenden, um eine Eigenschaft in der Projektdatei mit einem anderen Namen darzustellen. Standardmäßig ist dieses Attribut auf den **Namen** der Eigenschaft festgelegt.

   Eine einzelne Eigenschaft kann den DataSource-Wert des übergeordneten Rule-Elements überschreiben. In diesem Fall unterscheidet sich der Speicherort des Werts der Eigenschaft von dem anderer Eigenschaften in dieser Regel.

   h. Es gibt weitere Attribute von „Rule“, einschließlich „Description“ und „SupportsFileBatching“. Diese werden hier nicht dargestellt. Alle Attribute, die auf „Rule“ oder ein anderes Element angewendet werden können, finden Sie in der Dokumentation für diese Typen. Alternativ können Sie die öffentlichen Eigenschaften von Typen im `Microsoft.Build.Framework.XamlTypes`-Namespace der `Microsoft.Build.Framework .dll`-Assembly überprüfen.

   i. **DisplayName**, **PageTemplate** und **Order** sind auf die Benutzeroberfläche bezogene Eigenschaften, die in diesem Datenmodell vorhanden sind, das ansonsten von der Benutzeroberfläche unabhängig ist. Diese Eigenschaften werden meistens von allen Benutzeroberflächen verwendet, die zum Anzeigen von Eigenschaftenseiten verwendet werden. Die Eigenschaften **DisplayName** und **Description** sind in fast allen Elementen der XML-Datei vorhanden. Nur diese beiden Eigenschaften werden lokalisiert. Die Lokalisierung dieser Zeichenfolgen wird in einem späteren Beitrag erläutert.

1. **Kategorie**: Eine Regel kann mehrere Kategorien aufweisen. Bei der Reihenfolge, in der diese Kategorien in der XML-Datei aufgeführt werden, handelt es sich um einen Vorschlag für die Benutzeroberfläche, damit diese in der gleichen Reihenfolge angezeigt werden. Die Reihenfolge der Kategorien im Knoten „C/C++“, die auf der Benutzeroberfläche angezeigt wird (Allgemein, Optimierung, Präprozessor, ...),  entspricht beispielsweise der in „cl.xml“. Eine Beispielkategorie sieht folgendermaßen aus:

    ```xml
    <Category Name="Optimization">
      <Category.DisplayName>
        <sys:String>Optimization</sys:String>
      </Category.DisplayName>
    </Category>
    ```

   Der obige Codeausschnitt zeigt die Attribute **Name** und **DisplayName**, die zuvor beschrieben wurden. Auch für **Category** gibt es weitere Attribute, die oben nicht verwendet wurden. Sie können mehr über diese erfahren, indem Sie die Dokumentation lesen oder die Assemblys mithilfe von „ildasm.exe“ überprüfen.

1. **Properties:** Dies ist der Hauptbestandteil der XML-Datei, in dem eine Liste aller Eigenschaften der Regel enthalten ist. Jede Eigenschaft kann einen von fünf möglichen Typen aufweisen, die zuvor im XAML-Gerüst dargestellt wurden. In Ihrer Datei können jedoch nur einige dieser Typen vorhanden sein. Eine Eigenschaft besitzt mehrere Attribute, mit denen Sie ausführlich beschrieben werden kann. Hier wird nur **StringProperty** erläutert. Die übrigen Attribute sind jedoch ähnlich.

    ```xml
    <StringProperty Subtype="file" Name="ObjectFileName" Category="Output Files" Switch="Fo">
      <StringProperty.DisplayName>
        <sys:String>Object File Name</sys:String>
      </StringProperty.DisplayName>
      <StringProperty.Description>
        <sys:String>Specifies a name to override the default object file name; can be file or directory name.(/Fo[name])</sys:String>
      </StringProperty.Description>
    </StringProperty>
    ```

   Die meisten Attribute im Codeausschnitt wurden zuvor bereits beschrieben. Neu sind „Subtype“, „Category“ and „Switch“.

   a. **Subtype** ist ein Attribut, das nur für **StringProperty** und **StringListProperty** verfügbar ist und Kontextinformationen enthält. Der Wert von „file“ gibt beispielsweise an, dass die Eigenschaft einen Dateipfad darstellt. Solche Kontextinformationen werden verwendet, um die Bearbeitungsoberfläche zu verbessern, indem ein Windows-Explorer als Editor für die Eigenschaft bereitgestellt wird, mit dem der Benutzer die Datei visuell auswählen kann.

   b. **Kategorie**: Hierdurch wird die Kategorie der Eigenschaft deklariert. Suchen Sie diese Eigenschaft in der Kategorie **Ausgabedateien** auf der Benutzeroberfläche.

   c. **Switch:** Wenn eine Regel ein Tool darstellt (in diesem Fall z.B. ein Compilertool), werden die meisten Eigenschaften der Regel während der Buildzeit als Parameter an das ausführbare Tool übergeben. Der Wert dieses Attributs gibt das Parameterliteral an, das verwendet werden soll. Die oben genannte Eigenschaft gibt an, dass der Parameter **Fo** sein sollte. In Kombination mit dem **SwitchPrefix**-Attribut des übergeordneten Rule-Elements wird diese Eigenschaft an die ausführbare Datei als **/Fo"Debug\"** übergeben. Dies wird in der Befehlszeile für C/C++ auf der Benutzeroberfläche der Eigenschaftenseite angezeigt.

   Folgende weitere Eigenschaftenattribute sind vorhanden:

   d. **Visible:** Wenn Sie aus irgendeinem Grund nicht möchten, dass die Eigenschaft auf der Eigenschaftenseite angezeigt wird (aber zur Buildzeit trotzdem verfügbar ist), legen Sie dieses Attribut auf FALSE fest.

   e. **ReadOnly:** Wenn Sie eine schreibgeschützte Ansicht dieses Eigenschaftswerts auf den Eigenschaftenseiten bereitstellen möchten, legen Sie dieses Attribut auf TRUE fest.

   f. **IncludeInCommandLine:** Einige Eigenschaften müssen während der Buildzeit möglicherweise nicht an ein Tool übergeben werden. Wenn Sie dieses Attribut auf FALSE festlegen, wird es nicht übergeben.
