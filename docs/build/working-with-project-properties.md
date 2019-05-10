---
title: Festlegen von C++-Compiler und erstellen Sie die Eigenschaften in Visual Studio
description: Verwenden Sie Visual Studio-IDE, um Optionen von C++-Compiler und Linker und andere Buildeinstellungen zu ändern.
ms.date: 03/27/2019
helpviewer_keywords:
- project properties [C++], modifying
- properties [C++]
- Visual C++ projects, properties
- projects [C++], properties
ms.assetid: 9b0d6f8b-7d4e-4e61-aa75-7d14944816cd
ms.openlocfilehash: a8c15de43a3843b8ff12cb4ad3d951d76b90c039
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446184"
---
# <a name="set-compiler-and-build-properties"></a>Festlegen des Compilers und der Buildeigenschaften

In der IDE werden alle Informationen, die für das Erstellen eines Projekts erforderlich sind, als *Eigenschaften* verfügbar gemacht. Zu diesen Informationen zählen unter anderem der Anwendungsname, die Erweiterung (z.B. DLL, LIB, EXE), Compileroptionen, Linkeroptionen, Debuggereinstellungen und benutzerdefinierte Buildschritte. Sie verwenden üblicherweise *Eigenschaftenseite* (**Projekt > Eigenschaften**), um diese Eigenschaften anzuzeigen und zu ändern. Wählen Sie den Zugriff auf den Eigenschaftenseiten **Projekt > \<Projektname > Eigenschaften** das Hauptmenü oder mit der rechten Maustaste auf den Projektknoten im **Projektmappen-Explorer** , und wählen Sie **Eigenschaften**.

## <a name="default-properties"></a>Standardeigenschaften

Wenn Sie ein Projekt erstellen, weist das System verschiedenen Eigenschaften Werte zu. Die Standardwerte variieren in Abhängigkeit von der Art des Projekts und den Optionen, die Sie im App-Assistenten auswählen. Ein ATL-Projekt verfügt beispielsweise über Eigenschaften für MIDL-Dateien. Diese sind jedoch in einer Basiskonsolenanwendung nicht vorhanden. Die Standardeigenschaften werden im Bereich „Allgemein“ auf den Eigenschaftenseiten angezeigt:

![Visual C#&#43; &#43; Projektstandards](media/visual-c---project-defaults.png "Visual C++ Projektstandards")

## <a name="applying-properties-to-build-configurations-and-target-platforms"></a>Anwenden von Eigenschaften zum Erstellen von Konfigurationen und Plattformen

Einige Eigenschaften (z.B. der Anwendungsname) gelten für alle Buildvarianten, unabhängig von der Zielplattform oder davon, ob es sich um einen Debug- oder um einen Releasebuild handelt. Die meisten Eigenschaften hängen jedoch von Konfigurationen ab. Das liegt daran, dass der Compiler wissen muss, auf welcher Plattform das Programm ausgeführt wird und welche Compileroptionen verwendet werden müssen, um den richtigen Code zu generieren. Wenn Sie eine Eigenschaft festlegen, sollten Sie deshalb darauf achten, für welche Konfiguration und welche Plattform der neue Wert gelten soll. Soll sie nur für Win32-Debugbuilds oder ebenfalls für ARM- und x64-Debugbuilds gelten? Die Eigenschaft **Optimierung** ist in einer Releasekonfiguration beispielsweise standardmäßig auf **Geschwindigkeit maximieren (/O2)** festgelegt. In einer Debugkonfiguration ist sie jedoch deaktiviert.

Die Eigenschaftenseiten wurden so entwickelt, dass Sie immer sehen und bei Bedarf ändern können, für welche Konfiguration und Plattform ein Eigenschaftswert gelten soll. Die folgende Abbildung zeigt die Eigenschaftenseiten mit Informationen zur Konfiguration und zur Plattform in den Listenfeldern im oberen Bereich. Wenn die Eigenschaft **Optimierung** hier festgelegt ist, gilt diese nur für Win32-Debugbuilds. Dies ist die aktive Konfiguration (angezeigt durch die roten Pfeile).

![Visual C++-Eigenschaftenseite, die die aktive Konfiguration anzeigt](media/visual-c---property-pages-showing-active-configuration.png "Visual C++ Property Pages showing active configuration")

Die folgende Abbildung zeigt dieselbe Eigenschaftenseite des Projekts, allerdings wurde die Konfiguration in „Release“ geändert. Beachten Sie den geänderten Wert der Eigenschaft „Optimierung“. Beachten Sie außerdem, dass die aktive Konfiguration immer noch „Debug“ ist. Sie können hier Eigenschaften für jede Konfiguration festlegen. Diese müssen nicht der aktiven Konfiguration entsprechen.

![Visual C++-Eigenschaftenseite, die die Konfiguration „Release“ anzeigt](media/visual-c---property-pages-showing-release-config.png "Visual C++ Property Pages showing release config")

## <a name="target-platforms"></a>Zielplattformen

*Zielplattform* bezieht sich auf den Gerätetyp und/oder das Betriebssystem, auf dem die ausführbare Datei ausgeführt wird. Sie können ein Projekt für mehr als eine Plattform erstellen. Die verfügbaren Zielplattformen für C++-Projekte hängen von der Art des Projekts ab. Unter anderem sind Win32, x64, ARM, Android und iOS verfügbar.     Die Zielplattform **x86**, die im **Konfigurations-Manager** angezeigt wird, entspricht **Win32** in nativen C++-Projekten. Win32 bedeutet 32-Bit-Windows, und **x64** bedeutet 64-Bit-Windows. Weitere Informationen zu diesen beiden Plattformen finden Sie unter [Ausführung von 32-Bit-Anwendungen](/windows/desktop/WinProg64/running-32-bit-applications).

Der Wert **Beliebige CPU**, den Sie im **Konfigurations-Manager** für die Zielplattform sehen, hat keine Auswirkung auf native C++-Projekte. Er ist nur für C++/CLI- und andere .NET-Projekttypen relevant. Weitere Informationen finden Sie unter [/CLRIMAGETYPE (Angeben des CLR-Bildtyps)](reference/clrimagetype-specify-type-of-clr-image.md).


Weitere Informationen zum Festlegen von Eigenschaften für einen Debugbuild finden Sie unter:

- [Projekteinstellungen für eine C++-Debugkonfiguration](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration)
- [Debuggereinstellungen und -vorbereitung](/visualstudio/debugger/debugger-settings-and-preparation)
- [Vorbereitung zum Debuggen: Visual C++-Projekttypen](/visualstudio/debugger/debugging-preparation-visual-cpp-project-types)
- [Angeben von Symbol- (PDB-) und Quelldateien im Visual Studio Debugger](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger)

## <a name="c-compiler-and-linker-options"></a>Optionen von C++-Compiler und linker

C++-Compiler und Linker Optionen befinden sich unter dem **C/C++-** und **Linker** Knoten im linken Bereich unter **Konfigurationseigenschaften**. Diese übersetzt sich direkt den Befehlszeilenoptionen, die an den Compiler übergeben werden. Wählen Sie die Option zum Lesen der Dokumentation zu einer bestimmten Option in den mittleren Bereich, und drücken Sie **F1**. Oder Sie können die Dokumentation für alle Optionen unter Durchsuchen [MSVC-Compiler-Optionen](reference/compiler-options.md) und [MSVC-Linkeroptionen](reference/linker-options.md). 

Die **Eigenschaftenseiten** Dialogfeld zeigt nur die Eigenschaftenseiten, die für das aktuelle Projekt relevant sind. Wenn das Projekt beispielsweise keine IDL-Datei enthält, wird die MIDL-Eigenschaftenseite nicht angezeigt. Weitere Informationen zu den Einstellungen auf den einzelnen Eigenschaftenseiten finden Sie unter [Property Pages (C++)](reference/property-pages-visual-cpp.md). 

## <a name="directory-and-path-values"></a>Anwendungsverzeichnis oder-Pfad Werte

MSBuild unterstützt die Verwendung von Kompilierzeitkonstanten "Makros" bezeichnet, für bestimmte Zeichenfolgenwerte Verzeichnisse und Pfade enthalten. Diese werden verfügbar gemacht, in den Eigenschaftenseiten können Sie verweisen und ändern sie mithilfe der [Eigenschaften-Editor](#property_editor). 

Die folgende Abbildung zeigt die Eigenschaftenseiten für ein Visual Studio C++ Projekt. Im linken Bereich ist die *Regel* **VC++-Verzeichnisse** ausgewählt, und im rechten Bereich werden die Eigenschaften aufgeführt, die dieser Regel zugeordnet sind. Die `$(...)` Werte heißen *Makros*. Ein *Makro* ist eine Kompilierzeitkonstante, die auf einen benutzerdefinierten Wert oder auf einen Wert verweisen kann, der von Visual Studio oder dem MSBuild-System definiert wurde. Mit Makros anstelle von hartcodierten Werte wie Verzeichnispfaden können Sie leichter eigenschafteneinstellungen zwischen Computern und zwischen Versionen von Visual Studio, und können Sie besser sicherstellen, dass die projekteinstellungen ordnungsgemäß in teilnehmen [ eigenschaftenvererbung](project-property-inheritance.md). 

![Projekteigenschaftenseiten](media/project_property_pages_vc.png "Project_Property_Pages_VC")

Sie können den Eigenschaften-Editor verwenden, um die Werte aller verfügbaren Makros anzuzeigen.

### <a name="predefined-macros"></a>Vordefinierte Makros

*Globale Makros*<br/>
Gilt für alle Elemente in einer Projektkonfiguration. Besitzt die Syntax `$(name)`. Ein Beispiel eines globalen Makros ist `$(VCInstallDir)`, das das Stammverzeichnis der Visual Studio-Installation speichert. Ein globales Makro entspricht einer `PropertyGroup` in MSBuild.

*Elementmakros*<br/>
Besitzt die Syntax `%(name)`. Bei einer Datei gilt ein Elementmakro nur für diese Datei – z. B. können Sie `%(AdditionalIncludeDirectories)` verwenden, um Includeverzeichnisse anzugeben, die nur für eine bestimmte Datei gelten. Diese Art des Elementmakros entspricht den `ItemGroup`-Metadaten in MSBuild. Wenn ein Elementmakro im Zusammenhang mit einer Projektkonfiguration verwendet wird, gilt es für alle Dateien eines bestimmten Typs. Beispielsweise kann die C/C++-Konfigurationseigenschaft **Präprozessordefinitionen** ein `%(PreprocessorDefinitions)`-Elementmakro verwenden, das für alle CPP-Dateien im Projekt gilt. Diese Art des Elementmakros entspricht den `ItemDefinitionGroup`-Metadaten in MSBuild. Weitere Informationen finden Sie unter [Item Definitions](/visualstudio/msbuild/item-definitions) (Elementdefinitionen).

### <a name="user-defined-macros"></a>benutzerdefinierte Makros

Sie können *benutzerdefinierte Makros* erstellen, um sie als Variablen in Projektbuilds zu verwenden. Sie können z. B. ein benutzerdefiniertes Makro erstellen, das einen Wert für einen benutzerdefinierten Buildschritt oder ein benutzerdefiniertes Buildtool bereitstellt. Ein benutzerdefiniertes Makro ist ein Name-Wert-Paar. Verwenden Sie in einer Projektdatei die Notation **$(**<em>name</em>**)**, um auf den Wert zuzugreifen.

Ein benutzerdefiniertes Makro wird in einem Eigenschaftenblatt gespeichert. Wenn Ihr Projekt nicht bereits ein Eigenschaftenblatt enthält, können Sie erstellen, indem Sie die Schritte unter [Freigabe oder zur Wiederverwendung von Visual Studio-projekteinstellungen](create-reusable-property-configurations.md).

#### <a name="to-create-a-user-defined-macro"></a>So erstellen Sie ein benutzerdefiniertes Makro

1. Öffnen Sie im Fenster **Eigenschaften-Manager** (klicken Sie auf der Menüleiste auf **Ansicht** > **Eigenschaften-Manager**) das Kontextmenü für ein Eigenschaftenblatt (der Name endet auf „.user“), und wählen Sie „Eigenschaften“ aus. Das Dialogfeld **Eigenschaftenseiten** für dieses Eigenschaftenblatt wird geöffnet.

1. Klicken Sie im linken Bereich des Dialogfelds auf **Benutzermakros**. Klicken Sie im rechten Bereich auf die Schaltfläche **Makro hinzufügen**, um das Dialogfeld **Benutzermakro hinzufügen** zu öffnen.

1. Geben Sie im Dialogfeld einen Namen und einen Wert für das Makro an. Optional können Sie das Kontrollkästchen **Makro als Umgebungsvariable in Buildumgebung festlegen** aktivieren.

## <a name="property_editor">Eigenschaften-Editor</a>

Mit dem Eigenschaften-Editor können Sie bestimmte Zeichenfolgeneigenschaften ändern und Makros als Werte auswählen. Um auf den Eigenschaften-Editor zuzugreifen, wählen Sie eine Eigenschaft auf einer Eigenschaftenseite aus, und klicken Sie rechts auf die Schaltfläche mit dem Pfeil nach unten. Wenn die Dropdownliste die Option **\<Bearbeiten>** enthält, können Sie auf diese klicken, um den Eigenschaften-Editor für diese Eigenschaft anzuzeigen.

![Dropdownliste im Eigenschaften-Editor](media/property_editor_dropdown.png "Property_Editor_Dropdown")

Im Eigenschaften-Editor können Sie auf die Schaltfläche **Makros** klicken, um die verfügbaren Makros und deren aktuelle Werte anzuzeigen. Die folgende Abbildung zeigt den Eigenschaften-Editor für die Eigenschaft **Zusätzliche Includeverzeichnisse**, nachdem auf die Schaltfläche **Makros** geklickt wurde. Wenn das Kontrollkästchen **Vom übergeordneten Projekt erben oder Projektstandard** aktiviert ist und Sie einen neuen Wert hinzufügen, wird dieser an alle Werte angefügt, die derzeit vererbt werden. Wenn Sie das Kontrollkästchen deaktivieren, ersetzt der neue Wert die vererbten Werte. In den meisten Fällen bleibt das Kontrollkästchen aktiviert.

![Eigenschaften-Editor, Visual C++](media/propertyeditorvc.png "PropertyEditorVC")

## <a name="add-an-include-directory-to-the-set-of-default-directories"></a>Ein Includeverzeichnis auf den Satz von dem Standard entsprechenden Verzeichnissen hinzufügen

Wenn Sie einem Projekt ein Includeverzeichnis hinzufügen, ist es wichtig darauf zu achten, die Standardverzeichnisse nicht zu überschreiben. Die richtige Methode, ein Verzeichnis hinzuzufügen, besteht darin, den neuen Pfad anzufügen (z.B. C:\MeinNeuesIncludeVerz\"), und dann das Makro **$(IncludePath)** an den Eigenschaftswert anzufügen.

## <a name="quickly-browse-and-search-all-properties"></a>Durchsuchen Sie einfach alle Eigenschaften

Die Eigenschaftenseite **Alle Optionen** (unter dem Knoten **Konfigurationseigenschaften > C/C++** im linken Bereich des Dialogfelds **Eigenschaftenseiten**) bietet eine schnelle Möglichkeit, die Eigenschaften zu durchsuchen, die im aktuellen Kontext verfügbar sind, und nach ihnen zu suchen. Über ein spezielles Suchfeld und eine einfache Syntax können Sie Ergebnisse filtern:

Kein Präfix:<br/>
Suche nur in den Eigenschaftennamen (untergeordnete Zeichenfolge ohne Berücksichtigung der Groß-/Kleinschreibung)

'/' oder '-' :<br/>
Suche nur in den Compilerschaltern (Präfix ohne Berücksichtigung der Groß-/Kleinschreibung)

v:<br/>
Suche nur in Werten (untergeordnete Zeichenfolge ohne Berücksichtigung der Groß-/Kleinschreibung)

## <a name="set-environment-variables-for-a-build"></a>Festlegen von Umgebungsvariablen für einen build

Der MSVC-Compiler (cl.exe) erkennt bestimmte Umgebungsvariablen, insbesondere LIB, LIBPATH, PATH und INCLUDE. Wenn Sie die Erstellung mit der IDE vornehmen, werden die Eigenschaften, die auf der Eigenschaftenseite [VC++-Verzeichnisse](reference/vcpp-directories-property-page.md) festgelegt sind, zum Festlegen der Umgebungsvariablen verwendet. Wenn LIB-, LIBPATH- und INCLUDE-Werte bereits festgelegt wurden, beispielsweise durch eine Developer-Eingabeaufforderung, werden diese durch die Werte der entsprechenden MSBuild-Eigenschaften ersetzt. Der Build stellt dann PATH den Wert der ausführbaren Verzeichniseigenschaft VC++-Verzeichnisse voran. Sie können eine benutzerdefinierte Umgebungsvariable festlegen, indem Sie ein benutzerdefiniertes Makro erstellen und dann das Kontrollkästchen **Makro als Umgebungsvariable in Buildumgebung festlegen** aktivieren.

## <a name="set-environment-variables-for-a-debugging-session"></a>Festlegen von Umgebungsvariablen für eine Debugsitzung

Erweitern Sie im linken Bereich des Dialogfelds **Eigenschaftenseiten** die **Konfigurationseigenschaften** des Projekts, und klicken Sie auf **Debugging**.

Ändern Sie im rechten Bereich die Projekteinstellungen **Umgebung** oder **Mergeumgebung**, und klicken Sie dann auf die Schaltfläche **OK**.

## <a name="in-this-section"></a>In diesem Abschnitt

[Freigeben oder Wiederverwenden von Visual Studio-Projekteinstellungen](create-reusable-property-configurations.md)<br/>
So erstellen Sie eine PROPS-Datei mit benutzerdefinierten Einstellungen, die freigegeben werden können oder Resused.

[Vererbung von Projekteigenschaften](project-property-inheritance.md)<br/>
Beschreibt die Reihenfolge der Auswertung für props, targets, vcxproj-Dateien und Umgebungsvariablen im Buildprozess.

[Ändern von Eigenschaften und Zielen ohne Änderungen an der Projektdatei](modify-project-properties-without-changing-project-file.md)<br/>
Vorgehensweise: temporäre Buildeinstellungen zu erstellen, ohne eine Projektdatei zu ändern. 

## <a name="see-also"></a>Siehe auch

[Visual Studio-Projekte: C++](creating-and-managing-visual-cpp-projects.md)<br/>
[VCXPROJ- und PROPS-Dateistruktur](reference/vcxproj-file-structure.md)<br/>
[Eigenschaftenseite: XML-Dateien](reference/property-page-xml-files.md)<br/>
