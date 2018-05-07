---
title: Eigenschaftendateien Page XML-Regel | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property page XML files
ms.assetid: dd9d9734-4387-4098-8ba6-85b93507731d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fcee2c416fba6a959785826781aefd96b0d06d75
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="property-page-xml-rule-files"></a>Eigenschaftendateien Page XML-Regel
Die Projekteigenschaftenseiten in der IDE werden vom XML-Dateien im Ordner "VCTargets" konfiguriert. Der genaue Pfad hängt davon ab, welche Versionen von Visual Studio installiert sind und die Produkt-Programmiersprache. Für Visual Studio 2017 Enterprise Edition, auf Englisch, der Pfad ist `%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033`. Die XML-Dateien beschrieben, die Namen der Regeln, die Kategorien und die einzelnen Eigenschaften, deren Datentyp, Standardwerte und Verwandtschaft angezeigt werden. Wenn Sie eine Eigenschaft in der IDE festlegen, wird der neue Wert in der Projektdatei gespeichert.

Die einzigen Szenarien, die in denen müssen Sie verstehen, dass die interne Funktionsweise dieser Dateien und der Visual Studio-IDE (a) Sie sind eine benutzerdefinierten Eigenschaftenseite erstellt werden soll, oder (b) Sie die Projekteigenschaften Weise als über die Visual Studio IDE anpassen möchten. 

Zunächst sehen wir die Eigenschaftenseiten für ein Projekt öffnen (klicken Sie mit der rechten Maustaste auf den Projektknoten in **Projektmappen-Explorer** , und wählen Sie Eigenschaften):
   
![Visual C++-Projekteigenschaften](media/cpp-property-page-2017.png)

Jeder Knoten unter **Konfigurationseigenschaften** eine Regel aufgerufen wird. Eine Regel darstellt manchmal eines einzigen Tools wie der Compiler, aber im Allgemeinen bezieht sich der Begriff, die verfügt über Eigenschaften, die ausgeführt wird, und möglicherweise einige Ausgabe erzeugt. Jede Regel wird aus einer XML-Datei im Ordner "VCTargets" aufgefüllt. Beispielsweise wird die C/C++-Regel, die oben angezeigt wird, mit "cl.xml" aufgefüllt.

Wie oben dargestellt, hat jeder Regel einen Satz von Eigenschaften, die in Kategorien organisiert sind. Jeder untergeordnete Knoten unter einer Regel stellt eine Kategorie dar. Beispielsweise enthält der Knoten "Optimierung" unter "C/C++" alle Optimierung bezogenen Eigenschaften der vom Compiler-Tool. In einem Rasterformat im rechten Bereich werden die Eigenschaften und ihre Werte selbst gerendert.

Sie können cl.xml in Editor oder einem beliebigen XML-Editor (siehe unten snapshot) öffnen. Sehen Sie einen Stammknoten namens Regel, die die gleiche Liste von Eigenschaften wird definiert, wie in der Benutzeroberfläche sowie zusätzliche Metadaten, die angezeigt wird.

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

Es ist eine XML-Datei für jeden Knoten unter Konfigurationseigenschaften auf den Eigenschaftenseiten Benutzeroberfläche entspricht. Sie können hinzufügen oder Entfernen von Regeln in der Benutzeroberfläche durch ein- oder Orte, um die entsprechenden XML-Dateien im Projekt entfernen. Dies ist z. B. wie Microsoft.CppBuild.targets (eine Ebene nach oben aus dem Ordner 1033) cl.xml enthält:

```xml  
<PropertyPageSchema Condition="'$(ConfigurationType)' != 'Utility'" Include="$(VCTargetsPath)$(LangID)\cl.xml"/>

``` 
Wenn Sie cl.xml aller Daten entfernt wird, werden Sie sich mit den folgenden Skeleton beenden:
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

Der folgende Abschnitt beschreibt jede Hauptelemente und einige der Metadaten, die an diese angefügt werden kann.

1. **Regel:** Regel ist im Allgemeinen der Stammknoten in der XML-Datei; es kann viele Attribute verfügen:

```xml    
<Rule Name="CL" PageTemplate="tool" SwitchPrefix="/" Order="10"
          xmlns="http://schemas.microsoft.com/build/2009/properties"
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
          xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <Rule.DisplayName>
    <sys:String>C/C++</sys:String>
  </Rule.DisplayName>
```  

   a. **Name:** das Name-Attribut ist eine Id für die Regel. Es muss für alle Eigenschaft Seite XML-Dateien für ein Projekt eindeutig sein.

   b. **PageTemplate:** der Wert dieses Attributs wird über die Benutzeroberfläche verwendet, aus einer Auflistung von Benutzeroberflächenautomatisierungs-Vorlagen auswählen. Die Vorlage "-Tool" rendert die Eigenschaften im standard-Tabellenformat an. Andere integrierte Werte für dieses Attribut sind "Debugger" und "generisch". Finden Sie unter den Knoten "Debuggen" und den Knoten Allgemein, sehen Sie das UI-Format aus Sie diese Werte angeben. Die Benutzeroberfläche für die Seite "Vorlage"Debugger"verwendet ein Dropdown-Feld, um zwischen den Eigenschaften der verschiedenen Debugger wechseln, während die Vorlage"generische"verschiedene Eigenschaftenkategorien alle auf einer Seite im Gegensatz zur Verwendung von mehreren Kategorie Unterknoten unter der Regel anzeigt. Knoten. Dieses Attribut ist nur einen Vorschlag für die Benutzeroberfläche. die XML-Datei dient zur Benutzeroberfläche unabhängig sein. Eine andere Benutzeroberfläche kann dieses Attribut für unterschiedliche Zwecke verwenden.

  c. **SwitchPrefix:** Dies ist das Präfix für die Schalter in der Befehlszeile verwendet. Ein Wert von "/" Switches, die/Zi, / nologo, /W3 aussehen würde.

  d. **Auftrag:** Hierbei handelt es sich um einen Vorschlag für einen potenziellen Benutzeroberflächenautomatisierungs-Client auf den relativen Speicherort der mit dieser Regel im Vergleich zu allen anderen Regeln im System.

  e. **Xmlns:** Dies ist ein standard-XAML-Element. Sie können drei aufgeführten Namespaces finden Sie unter. Diese entsprechen die Namespaces für die Verwendung von XAML-Deserialisierung-Klassen XAML Schema- und Systemdaten Namespace bzw. Server.

  f. **DisplayName:** Dies ist der Name, der auf der Eigenschaftenseite UI für den Knoten für die Regel angezeigt wird. Dieser Wert ist lokalisiert. Wir erstellt DisplayName nicht als ein Attribut (z. B. Name oder SwitchPrefix), sondern als untergeordnetes Element der Regel aufgrund interner Lokalisierung Tool Anforderungen. Aus Sicht des XAML-sind beide entspricht. Deshalb können Sie nur erleichtern ein Attribut Übersichtlichkeit, oder lassen Sie das Feld entspricht.

  g. **Datenquelle:** Dies sind sehr wichtig, die die vom Projektsystem angewiesen, den Speicherort aus dem Wert der Eigenschaft sollte gelesen und geschrieben und seine gruppieren (siehe unten). Für cl.xml sind diese Werte:

```xml  
       <DataSource Persistence="ProjectFile" ItemType="ClCompile" Label="" HasConfigurationCondition="true" />
```  
   - `Persistence="ProjectFile` Zeigt das Projektsystem, das alle Eigenschaften für die Regel auf die Projektdatei geschrieben werden sollen, oder der Eigenschaftenblattdatei (je nachdem, welche Knoten verwendet wurde beim Erzeugen der Eigenschaftenseiten). Der andere Wert ist "Benutzerlistendatei befindet sich eine" dem Wert in der User-Datei schreiben kann.

   - `ItemType="ClCompile"` besagt, dass die Eigenschaften gespeichert werden soll, als ItemDefinition oder Elementmetadaten (Bei letzterem Betriebssystem nur, wenn Sie die Eigenschaftenseiten von einem Dateiknoten im Projektmappen-Explorer erzeugt wurden) für diesen Elementtyp. Wenn dieses Feld nicht festgelegt ist, wird die Eigenschaft als eine allgemeine Eigenschaft in einer PropertyGroup geschrieben.

   - `Label=""` Gibt an, dass, wenn die Eigenschaften, als geschrieben werden `ItemDefinition` Metadaten, die Beschriftung des übergeordneten Elements ItemDefinitionGroup wird leer sein (jedes MSBuild-Element kann eine Bezeichnung haben). Visual Studio-2017 verwendet bezeichnete Gruppen die VCXPROJ-Projektdatei zu navigieren. Beachten Sie, dass die Gruppen, die meisten Eigenschaften für Abfrageregel enthalten eine leere Zeichenfolge als eine Bezeichnung verfügen.

   - `HasConfigurationCondition="true"` weist das Projektsystem, eine Konfiguration Bedingung mit dem Wert anzubringen, damit sie wirksam nur für die aktuelle Konfiguration des Projekts wird (die Bedingung konnte auf der übergeordneten Gruppe oder den Wert selbst angebracht werden.). Z. B. Öffnen Sie die Eigenschaftenseiten deaktiviert den Projektknoten, und legen Sie den Wert der Eigenschaft **Warnungen als Fehler behandeln** unter **Konfigurationseigenschaften > C/C++-Allgemein** auf "Yes". Der folgende Wert wird in der Projektdatei geschrieben. Beachten Sie, dass die Bedingung für die Konfiguration, die an das übergeordnete Element ItemDefinitionGroup angefügt werden.

```xml  
     <ItemDefinitionGroup Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">
        <ClCompile>
           <TreatWarningAsError>true</TreatWarningAsError>
        </ClCompile>
     </ItemDefinitionGroup>
 ```
   Wenn dieser Wert festgelegt wurden, auf der Eigenschaftenseite für eine bestimmte Datei, z. B. "stdafx.cpp", würde den Wert der Eigenschaft unter dem Element "stdafx.cpp" in der Projektdatei wie folgt geschrieben werden. Beachten Sie, wie die Bedingung für die Konfiguration direkt an die Metadaten selbst angefügt ist.

 ```xml  
<ItemGroup>
   <ClCompile Include="stdafx.cpp">
      <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">true</TreatWarningAsError>
   </ClCompile>
</ItemGroup>
 ```
   Ein weiteres Attribut der **DataSource** oben nicht aufgeführt ist **PersistedName**. Sie können dieses Attribut verwenden, um eine Eigenschaft in der Projektdatei, die unter einem anderen Namen darzustellen. Standardmäßig ist dieses Attribut festgelegt, für der Eigenschaft **Namen**. 

   Eine einzelne Eigenschaft kann die übergeordnete Regel DataSource überschreiben. In diesem Fall wird der Speicherort für diese Eigenschaft-Wert von anderen Eigenschaften in der Regel abweichen.

   h. Es gibt andere Attribute einer Regel z. B. Beschreibung, SupportsFileBatching usw., die hier nicht angezeigt werden. Der vollständige Satz von Attributen auf eine Regel oder ein anderes Element kann durch Durchsuchen der Dokumentation für diese Typen abgerufen werden. Alternativ können Sie überprüfen, für die Typen in öffentlichen Eigenschaften der `Microsoft.Build.Framework.XamlTypes` Namespace in der `Microsoft.Build.Framework .dll` Assembly.

   i. **DisplayName**, **PageTemplate**, und **Reihenfolge** UI-bezogene Eigenschaften, die in diesem vorhanden sind. Andernfalls werden unabhängig von UI-Datenmodell. Diese Eigenschaften sind fast sicher von Benutzeroberflächen verwendet werden, die verwendet wird, um die Eigenschaftenseiten angezeigt. **DisplayName** und **Beschreibung** sind zwei Eigenschaften, die auf fast alle Elemente in der XML-Datei vorhanden sind. Diese sind nur zwei Eigenschaften, die lokalisiert werden (der Lokalisierung von diese Zeichenfolgen werden in einer späteren Post erläutert).

2.  **Kategorie:** eine Regel kann mehrere Kategorien haben. Die Reihenfolge, in der die Kategorien, in der XML-Datei aufgeführt sind, ist einen Vorschlag für die Benutzeroberfläche zu die Kategorien in der gleichen Reihenfolge angezeigt. Z. B. die Reihenfolge der Kategorien unter dem C/C++-Knoten wie in der Benutzeroberfläche dargestellt – Allgemein "," Optimierung "," Präprozessor...  – Dieser in cl.xml identisch ist. Eine Beispielkategorie sieht wie folgt:

```xml  
 <Category Name="Optimization">
    <Category.DisplayName>
        <sys:String>Optimization</sys:String>
    </Category.DisplayName>
 </Category>
```
Im obigen Codeausschnitt dargestellt die **Namen** und **DisplayName** Attribute, die vor beschrieben wurden. Wieder andere Attribute vorhanden sind eine **Kategorie** kann verfügen, werden oben nicht verwendet. Sie können sie durch Lesen der Dokumentation oder durch Untersuchen der Assemblys, die mithilfe von ildasm.exe erfahren.

3. **Eigenschaften:** Dies ist der Hauptbestandteil der XML-Datei und enthält die Liste aller Eigenschaften in dieser Regel. Jede Eigenschaft kann einen von fünf möglichen Typen, die in das XAML-Skelett oben angezeigt werden. Natürlich könnten Sie nur einige dieser Typen in der Datei verfügen. Eine Eigenschaft verfügt über eine Reihe von Attributen, die ihm ermöglichen, Rich-Text beschrieben werden. Ich werde nur erläutern die **StringProperty** hier. Die übrigen sind sehr ähnlich.

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
Die meisten der Attribute im Ausschnitt haben vor beschrieben wurde. Neue sind Untertyp, Kategorie und Switches.

   a. **Untertyp** steht nur für ein Attribut **StringProperty** und **StringListProperty**; sie bietet Kontextinformationen. Der Wert "File" bedeutet z. B. die Eigenschaft einen Dateipfad darstellt. Solche Kontextinformationen dient zum Verbessern der Bearbeitungsoberfläche durch die Bereitstellung einer Windows-Explorer als Editor für die Eigenschaft, die dem Benutzer ermöglicht, wählen die Datei visuell.

   b. **Kategorie:** dies deklariert die Kategorie, unter denen diese Eigenschaft liegt. Versuchen Sie, diese Eigenschaft mit dem Suchen der **Ausgabedateien** Kategorie in der Benutzeroberfläche.

   c. **Switch:** Wenn eine Regel darstellt, ein Tool – z. B. vom Compiler-Tool in diesem Fall – die meisten Eigenschaften der Regel werden als übergeben Schalter für das Tool ausführbare während des Buildvorgangs. Der Wert dieses Attributs gibt an, die Switch-literal verwendet werden. Die oben genannten Eigenschaft gibt an, dass der Switch sollte **Fo**. In Kombination mit der **SwitchPrefix** Attribut für die übergeordnete Regel, die diese Eigenschaft wird an die ausführbare Datei als übergeben **/Fo "Debuggen\"**  (in der Befehlszeile für C/C++-auf der Seite der Benutzeroberfläche sichtbar).

   Andere Eigenschaftenattribute enthalten:

   d. **Visible:** Wenn aus irgendeinem Grund nicht Ihrer Eigenschaft angezeigt sollen werden, auf den Eigenschaftenseiten (aber trotzdem während des Buildvorgangs verfügbar), legen Sie dieses Attribut auf "false".

   e. **ReadOnly:** , wenn Sie eine schreibgeschützte Ansicht des Werts dieser Eigenschaft auf den Eigenschaftenseiten bereitstellen möchten, legen Sie dieses Attribut auf "true".

   f. **IncludeInCommandLine:** einige Eigenschaften können nicht während des Buildvorgangs zu einem Tool übergeben werden müssen. Wenn dieses Attribut auf "false" werden verhindern übergeben werden.


