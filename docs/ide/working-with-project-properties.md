---
title: Arbeiten mit Projekteigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- project properties [C++], modifying
- properties [C++]
- Visual C++ projects, properties
- projects [C++], properties
ms.assetid: 9b0d6f8b-7d4e-4e61-aa75-7d14944816cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3c33a18ff0d492ef3a870a342c9d8ff292007748
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339942"
---
# <a name="working-with-project-properties"></a>Arbeiten mit Projekteigenschaften
In der IDE werden alle Informationen, die für das Erstellen eines Projekts erforderlich sind, als *Eigenschaften* verfügbar gemacht. Zu diesen Informationen zählen unter anderem der Anwendungsname, die Erweiterung (z.B. DLL, LIB, EXE), Compileroptionen, Linkeroptionen, Debuggereinstellungen und benutzerdefinierte Buildschritte. Sie verwenden üblicherweise *Eigenschaftenseite* (**Projekt > Eigenschaften**), um diese Eigenschaften anzuzeigen und zu ändern. 
  
 Wenn Sie ein Projekt erstellen, weist das System verschiedenen Eigenschaften Werte zu. Die Standardwerte variieren in Abhängigkeit von der Art des Projekts und den Optionen, die Sie im App-Assistenten auswählen. Ein ATL-Projekt verfügt beispielsweise über Eigenschaften für MIDL-Dateien. Diese sind jedoch in einer Basiskonsolenanwendung nicht vorhanden. Die Standardeigenschaften werden im Bereich „Allgemein“ auf den Eigenschaftenseiten angezeigt:  
  
 ![Visual C++-Projektstandards](../ide/media/visual-c---project-defaults.png "Visual C++ Project Defaults")  
  
 Einige Eigenschaften (z.B. der Anwendungsname) gelten für alle Buildvarianten, unabhängig von der Zielplattform oder davon, ob es sich um einen Debug- oder um einen Releasebuild handelt. Die meisten Eigenschaften hängen jedoch von Konfigurationen ab. Das liegt daran, dass der Compiler wissen muss, auf welcher Plattform das Programm ausgeführt wird und welche Compileroptionen verwendet werden müssen, um den richtigen Code zu generieren. Wenn Sie eine Eigenschaft festlegen, sollten Sie deshalb darauf achten, für welche Konfiguration und welche Plattform der neue Wert gelten soll. Soll sie nur für Win32-Debugbuilds oder ebenfalls für ARM- und x64-Debugbuilds gelten? Die Eigenschaft **Optimierung** ist in einer Releasekonfiguration beispielsweise standardmäßig auf **Geschwindigkeit maximieren (/O2)** festgelegt. In einer Debugkonfiguration ist sie jedoch deaktiviert.  
  
 Die Eigenschaftenseiten wurden so entwickelt, dass Sie immer sehen und bei Bedarf ändern können, für welche Konfiguration und Plattform ein Eigenschaftswert gelten soll. Die folgende Abbildung zeigt die Eigenschaftenseiten mit Informationen zur Konfiguration und zur Plattform in den Listenfeldern im oberen Bereich. Wenn die Eigenschaft **Optimierung** hier festgelegt ist, gilt diese nur für Win32-Debugbuilds. Dies ist die aktive Konfiguration (angezeigt durch die roten Pfeile).  
  
 ![Visual C++-Eigenschaftenseite, die die aktive Konfiguration anzeigt](../ide/media/visual-c---property-pages-showing-active-configuration.png "Visual C++ Property Pages showing active configuration")  
  
 Die folgende Abbildung zeigt dieselbe Eigenschaftenseite des Projekts, allerdings wurde die Konfiguration in „Release“ geändert. Beachten Sie den geänderten Wert der Eigenschaft „Optimierung“. Beachten Sie außerdem, dass die aktive Konfiguration immer noch „Debug“ ist. Sie können hier Eigenschaften für jede Konfiguration festlegen. Diese müssen nicht der aktiven Konfiguration entsprechen.  
  
 ![Visual C++-Eigenschaftenseite, die die Konfiguration „Release“ anzeigt](../ide/media/visual-c---property-pages-showing-release-config.png "Visual C++ Property Pages showing release config")  
  
 Das Projektsystem basiert auf MSBuild. MSBuild definiert die Dateiformate und die Regeln für das Erstellen von Projekten. MSBuild verwaltet einen Großteil der Komplexität für das Erstellen für mehrere Konfigurationen und Plattformen. Sie sollten jedoch die Funktionsweise kennen. Dies ist besonders wichtig, wenn Sie benutzerdefinierte Konfigurationen definieren oder wiederverwendbare Eigenschaften erstellen möchten, die Sie für mehrere Projekte freigeben und in diese importieren können.  
  
 Projekteigenschaften werden entweder direkt in der Projektdatei (*.vcxproj) oder in anderen XML- oder PROPS-Dateien gespeichert, die Standardwerte angeben und von der Projektdatei importiert werden. Wie zuvor beschrieben kann der gleichen Eigenschaft für die gleiche Konfiguration ein anderer Wert in verschiedenen Dateien zugewiesen werden. Wenn Sie ein Projekt erstellen, wertet die MSBuild-Engine die Projektdatei und alle importierten Dateien in einer klar definierten Reihenfolge (siehe unten) aus. Während die Dateien ausgewertet werden, überschreiben alle Eigenschaftswerte, die in den Dateien definiert sind, die vorhandenen Werte. Alle nicht angegebenen Werte werden von Dateien geerbt, die zuvor ausgewertet wurden. Deshalb ist beim Festlegen einer Eigenschaft mit Eigenschaftenseiten ebenfalls wichtig, darauf zu achten, wo Sie diese festlegen. Wenn Sie eine Eigenschaft in einer PROPS-Datei auf „X“ festlegen, diese aber in der Projektdatei auf „Y“ festgelegt ist, wird das Projekt mit der auf „Y“ festgelegten Eigenschaft erstellt. Wenn die gleiche Eigenschaft in einem Projektelement (z.B. in einer CPP-Datei) auf „Z“ festgelegt ist, verwendet die MSBuild-Engine den Wert „Z“. Weitere Informationen finden Sie unter [Eigenschaftenvererbung](#bkmkPropertyInheritance) im Verlauf dieses Artikels.  
  
## <a name="build-configurations"></a>Buildkonfigurationen  
 Eine Konfiguration ist nur eine beliebige Gruppe von Eigenschaften, denen ein Name zugewiesen wird. Visual Studio stellt Debug- und Releasekonfigurationen bereit und legt jeweils verschiedene Eigenschaften fest, die einem Debugbuild oder einem Releasebuild entsprechen. Sie können den **Konfigurations-Manager** verwenden, um benutzerdefinierte Konfigurationen zu definieren und somit Eigenschaften einfach für einen bestimmten Build gruppieren. Der Eigenschaften-Manager wird für das erweiterte Arbeiten mit Eigenschaften verwendet. Er wird hier jedoch vorgestellt, da er beim Veranschaulichen der Projektkonfigurationen hilft. Sie können je nach Ihren Einstellungen über **Ansicht > Eigenschaften-Manager** oder über **Ansicht > Weitere Fenster > Eigenschaften-Manager** auf ihn zugreifen. Er enthält Knoten für jedes Konfiguration/Plattform-Paar im Projekt. Unter jedem dieser Knoten sind Knoten für Eigenschaftenblätter (PROPS-Dateien), die für diese Konfiguration spezifische Eigenschaften festlegen.  
  
 ![Eigenschaften-Manager](../ide/media/property-manager.png "Property Manager")  
  
 Wenn Sie auf den Eigenschaftenseiten zum Bereich „Allgemein“ wechseln (siehe Abbildung oben) und die Eigenschaft „Zeichensatz“ auf „Nicht festgelegt“ statt auf „Unicode-Zeichensatz verwenden“ festlegen und auf **OK** klicken, zeigt der Eigenschaften-Manager das Eigenschaftenblatt **Unicode-Unterstützung** für die aktuelle Konfiguration nicht an. Für andere Konfigurationen ist es jedoch vorhanden.  
  
 Weitere Informationen zum Eigenschaften-Manager und zu Eigenschaftenblättern finden Sie im Verlauf dieses Artikels unter [Erstellen wiederverwendbarer Eigenschaftenkonfigurationen](#bkmkPropertySheets).  
  
> [!TIP]
>  Bei der USER-Datei handelt es sich um ein veraltetes Feature. Es wird empfohlen, diese zu löschen, damit die Eigenschaften entsprechend der Konfiguration und Plattform richtig gruppiert werden.  
  
## <a name="target-platforms"></a>Zielplattformen  
 *Zielplattform* bezieht sich auf den Gerätetyp und/oder das Betriebssystem, auf dem die ausführbare Datei ausgeführt wird. Sie können ein Projekt für mehr als eine Plattform erstellen. Die verfügbaren Zielplattformen für C++-Projekte hängen von der Art des Projekts ab. Unter anderem sind Win32, x64, ARM, Android und iOS verfügbar.     Die Zielplattform **x86**, die im **Konfigurations-Manager** angezeigt wird, entspricht **Win32** in nativen C++-Projekten. Win32 bedeutet 32-Bit-Windows, und **x64** bedeutet 64-Bit-Windows. Weitere Informationen zu diesen beiden Plattformen finden Sie unter [Ausführung von 32-Bit-Anwendungen](https://msdn.microsoft.com/library/windows/desktop/aa384249\(v=vs.85\).aspx).  
  
 Der Wert **Beliebige CPU**, den Sie im **Konfigurations-Manager** für die Zielplattform sehen, hat keine Auswirkung auf native C++-Projekte. Er ist nur für C++/CLI- und andere .NET-Projekttypen relevant. Weitere Informationen finden Sie unter [/CLRIMAGETYPE (Angeben des CLR-Bildtyps)](../build/reference/clrimagetype-specify-type-of-clr-image.md).  
  
## <a name="property-pages"></a>Eigenschaftenseiten  
 Wie zuvor erwähnt basiert das Visual C++-Projektsystem auf [MSBuild](/visualstudio/msbuild/msbuild-properties), und die Werte werden in der XML-Projektdatei und in den PROPS- und TARGETS-Standarddateien gespeichert. Für Visual Studio 2015 befinden sich diese Dateien unter **\Programme (x86)\MSBuild\Microsoft.Cpp\v4.0\V140**. Für Visual Studio 2017 befinden sich diese Dateien unter **\\Programme (x86)\\Microsoft Visual Studio\\2017\\_Edition_\\Common7\\IDE\\VC\\VCTargets**. Hierbei entspricht _Edition_ der installierten Visual Studio-Edition. Eigenschaften werden ebenfalls in einer PROPS-Datei gespeichert, die Sie zu Ihrem Projekt hinzufügen können. Es wird dringend empfohlen, diese Dateien nicht manuell zu bearbeiten, sondern die Eigenschaftenseiten in der IDE dafür zu verwenden. Dies gilt insbesondere für die Dateien, die in die Vererbung mit einbezogen werden, sofern Sie nicht über gute MSBuild-Kenntnisse verfügen.  
  
 Die folgende Abbildung zeigt die Eigenschaftenseiten für ein Visual C++-Projekt. Im linken Bereich ist die Regel **VC++-Verzeichnisse**** ausgewählt, und im rechten Bereich werden die Eigenschaften aufgeführt, die dieser Regel zugeordnet sind. Die `$(...)`-Werte werden fälschlicherweise als *Makros* bezeichnet. Es handelt sich dabei jedoch *nicht* um C++-Makros, sondern nur um Kompilierzeitkonstanten. Makros werden im Verlauf dieses Artikels unter [Makros für Eigenschaftenseiten](#bkmkPropertiesVersusMacros) erläutert.  
  
 ![Projekteigenschaftenseiten](../ide/media/project_property_pages_vc.png "Project_Property_Pages_VC")  
  
> [!WARNING]
>  Die Konfiguration **Allgemeine Eigenschaften** aus älteren Versionen von Visual Studio wurde entfernt. Wenn Sie einen Verweis zu einem Projekt hinzufügen möchten, verwenden Sie nun das Dialogfeld **Verweis hinzufügen** auf die gleiche Weise wie für verwaltete Sprachen. Weitere Informationen finden Sie unter [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project).  
  
#### <a name="to-set-a-property-for-a-project"></a>So legen Sie eine Eigenschaft für ein Projekt fest  
  
1.  In den meisten Szenarios können Sie Eigenschaften auf Projektebene festlegen, ohne ein benutzerdefiniertes Eigenschaftenblatt zu erstellen. Klicken Sie im Hauptmenü auf **Projekt > Eigenschaften**, oder klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Eigenschaften** aus.  
  
2.  Verwenden Sie die Listenfelder **Konfiguration** und **Plattform** im oberen Bereich des Dialogfelds, um anzugeben, für welche Eigenschaftengruppen Ihre Änderungen gelten sollen. In vielen Fällen sind **Alle Plattformen** und **Alle Konfigurationen** die richtige Wahl. Wenn Sie Eigenschaften für mehrere, aber nicht alle Konfigurationen festlegen möchten, wählen Sie die gewünschten Konfigurationen im **Eigenschaften-Manager**aus, öffnen Sie das Kontextmenü, und klicken Sie auf **Eigenschaften**.  
  
 Im Dialogfeld **Eigenschaftenseiten** werden nur die Eigenschaftenseiten angezeigt, die für das aktuelle Projekt gelten. Wenn das Projekt beispielsweise keine IDL-Datei enthält, wird die MIDL-Eigenschaftenseite nicht angezeigt.  
  
 Wenn Sie eine Eigenschaft auf einer Eigenschaftenseite hervorheben, können Sie **F1** drücken, um zum Referenzthema zu gelangen. Dort finden Sie weitere Informationen zur entsprechenden Compiler- oder Linkeroption.  
  
 Weitere Informationen zu den einzelnen Eigenschaftenseiten finden Sie in folgenden Themen:  
  
-   [Eigenschaftenseite „Allgemein“ (Projekt)](../ide/general-property-page-project.md)  
  
-   [Eigenschaftenseite "Allgemein" (Datei)](../ide/general-property-page-file.md)  
  
-   [Eigenschaftenseiten "Befehlszeile"](../ide/command-line-property-pages.md)  
  
-   [Projekteinstellungen für eine C++-Debugkonfiguration](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration)  
  
-   [Eigenschaftenseite "NMake"](../ide/nmake-property-page.md)  
  
-   [Eigenschaftenseiten "Linker"](../ide/linker-property-pages.md)  
  
-   [Eigenschaftenseiten "Ressourcen"](../ide/resources-property-pages.md)  
  
-   [Eigenschaftenseiten "MIDL"](../ide/midl-property-pages.md)  
  
-   [Eigenschaftenseite "Webverweise"](../ide/web-references-property-page.md)  
  
-   [Eigenschaftenseite "Tool zum Generieren von XML-Daten"](../ide/xml-data-generator-tool-property-page.md)  
  
## <a name="to-quickly-browse-and-search-all-properties"></a>Suchen und Durchsuchen aller Eigenschaften  
 Die Eigenschaftenseite **Alle Optionen** (unter dem Knoten **Konfigurationseigenschaften > C/C++** im linken Bereich des Dialogfelds **Eigenschaftenseiten**) bietet eine schnelle Möglichkeit, die Eigenschaften zu durchsuchen, die im aktuellen Kontext verfügbar sind, und nach ihnen zu suchen. Über ein spezielles Suchfeld und eine einfache Syntax können Sie Ergebnisse filtern:  
  
 Kein Präfix:  
 Suche nur in den Eigenschaftennamen (untergeordnete Zeichenfolge ohne Berücksichtigung der Groß-/Kleinschreibung)  
  
 '/' oder '-' :  
 Suche nur in den Compilerschaltern (Präfix ohne Berücksichtigung der Groß-/Kleinschreibung)  
  
 v:  
 Suche nur in Werten (untergeordnete Zeichenfolge ohne Berücksichtigung der Groß-/Kleinschreibung)  
  
##  <a name="bkmkPropertiesVersusMacros"></a> Makros für Eigenschaftenseiten  
 Ein *Makro* ist eine Kompilierzeitkonstante, die auf einen benutzerdefinierten Wert oder auf einen Wert verweisen kann, der von Visual Studio oder dem MSBuild-System definiert wurde. Mit Makros anstelle von hartcodierten Werte wie Verzeichnispfaden können Eigenschafteneinstellungen zwischen Computern und verschiedenen Versionen von Visual Studio einfacher freigegeben werden. Zudem können Sie besser sicherstellen, dass die Projekteinstellungen ordnungsgemäß an der Eigenschaftenvererbung teilnehmen. Sie können den Eigenschaften-Editor verwenden, um die Werte aller verfügbaren Makros anzuzeigen.  
  
### <a name="predefined-macros"></a>Vordefinierte Makros  
 Globale Makros  
 Gilt für alle Elemente in einer Projektkonfiguration. Besitzt die Syntax `$(name)`. Ein Beispiel eines globalen Makros ist `$(VCInstallDir)`, das das Stammverzeichnis der Visual Studio-Installation speichert. Ein globales Makro entspricht einer `PropertyGroup` in MSBuild.  
  
 Elementmakros  
 Besitzt die Syntax `%(name)`. Bei einer Datei gilt ein Elementmakro nur für diese Datei – z. B. können Sie `%(AdditionalIncludeDirectories)` verwenden, um Includeverzeichnisse anzugeben, die nur für eine bestimmte Datei gelten. Diese Art des Elementmakros entspricht den `ItemGroup`-Metadaten in MSBuild. Wenn ein Elementmakro im Zusammenhang mit einer Projektkonfiguration verwendet wird, gilt es für alle Dateien eines bestimmten Typs. Beispielsweise kann die C/C++-Konfigurationseigenschaft **Präprozessordefinitionen** ein `%(PreprocessorDefinitions)`-Elementmakro verwenden, das für alle CPP-Dateien im Projekt gilt. Diese Art des Elementmakros entspricht den `ItemDefinitionGroup`-Metadaten in MSBuild. Weitere Informationen finden Sie unter [Item Definitions](/visualstudio/msbuild/item-definitions) (Elementdefinitionen).  
  
### <a name="user-defined-macros"></a>benutzerdefinierte Makros  
 Sie können *benutzerdefinierte Makros* erstellen, um sie als Variablen in Projektbuilds zu verwenden. Sie können z. B. ein benutzerdefiniertes Makro erstellen, das einen Wert für einen benutzerdefinierten Buildschritt oder ein benutzerdefiniertes Buildtool bereitstellt. Ein benutzerdefiniertes Makro ist ein Name-Wert-Paar. Verwenden Sie in einer Projektdatei die Notation **$(***name***)**, um auf den Wert zuzugreifen.  
  
 Ein benutzerdefiniertes Makro wird in einem Eigenschaftenblatt gespeichert. Wenn Ihr Projekt noch kein Eigenschaftenblatt enthält, können Sie eins erstellen, indem Sie die Schritte unter [Erstellen wiederverwendbarer Eigenschaftenkonfigurationen](#bkmkPropertySheets) befolgen.  
  
##### <a name="to-create-a-user-defined-macro"></a>So erstellen Sie ein benutzerdefiniertes Makro  
  
1.  Öffnen Sie im Fenster **Eigenschaften-Manager** (klicken Sie auf der Menüleiste auf **Ansicht** > **Eigenschaften-Manager**) das Kontextmenü für ein Eigenschaftenblatt (der Name endet auf „.user“), und wählen Sie „Eigenschaften“ aus. Das Dialogfeld **Eigenschaftenseiten** für dieses Eigenschaftenblatt wird geöffnet.  
  
2.  Klicken Sie im linken Bereich des Dialogfelds auf **Benutzermakros**. Klicken Sie im rechten Bereich auf die Schaltfläche **Makro hinzufügen**, um das Dialogfeld **Benutzermakro hinzufügen** zu öffnen.  
  
3.  Geben Sie im Dialogfeld einen Namen und einen Wert für das Makro an. Optional können Sie das Kontrollkästchen **Makro als Umgebungsvariable in Buildumgebung festlegen** aktivieren.  
  
## <a name="property-editor"></a>Eigenschaften-Editor  
 Mit dem Eigenschaften-Editor können Sie bestimmte Zeichenfolgeneigenschaften ändern und Makros als Werte auswählen. Um auf den Eigenschaften-Editor zuzugreifen, wählen Sie eine Eigenschaft auf einer Eigenschaftenseite aus, und klicken Sie rechts auf die Schaltfläche mit dem Pfeil nach unten. Wenn die Dropdownliste die Option **\<Bearbeiten>** enthält, können Sie auf diese klicken, um den Eigenschaften-Editor für diese Eigenschaft anzuzeigen.  
  
 ![Dropdownliste im Eigenschaften-Editor](../ide/media/property_editor_dropdown.png "Property_Editor_Dropdown")  
  
 Im Eigenschaften-Editor können Sie auf die Schaltfläche **Makros** klicken, um die verfügbaren Makros und deren aktuelle Werte anzuzeigen. Die folgende Abbildung zeigt den Eigenschaften-Editor für die Eigenschaft **Zusätzliche Includeverzeichnisse**, nachdem auf die Schaltfläche **Makros** geklickt wurde. Wenn das Kontrollkästchen **Vom übergeordneten Projekt erben oder Projektstandard** aktiviert ist und Sie einen neuen Wert hinzufügen, wird dieser an alle Werte angefügt, die derzeit vererbt werden. Wenn Sie das Kontrollkästchen deaktivieren, ersetzt der neue Wert die vererbten Werte. In den meisten Fällen bleibt das Kontrollkästchen aktiviert.  
  
 ![Eigenschaften-Editor, Visual C++](../ide/media/propertyeditorvc.png "PropertyEditorVC")  
  
##  <a name="bkmkPropertySheets"></a> Erstellen wiederverwendbarer Eigenschaftenkonfigurationen  
 Sie können zwar "globale" Eigenschaften für einen Benutzer und Computer festlegen, dies wird jedoch nicht mehr empfohlen. Stattdessen empfiehlt es sich, über den **Eigenschaften-Manager** ein *Eigenschaftenblatt* zu erstellen, um die Einstellungen für die Arten von Projekten zu speichern, die Sie wiederverwenden oder freigeben möchten. Über Eigenschaftenblätter verringern Sie zudem die Wahrscheinlichkeit, dass Eigenschafteneinstellungen für andere Projekttypen versehentlich geändert werden. Eigenschaftenblätter werden unter [Erstellen wiederverwendbarer Eigenschaftenkonfigurationen](#bkmkPropertySheets) ausführlicher erläutert.  
  
> [!IMPORTANT]
>  **USER-Dateien und mit ihnen verbundene Schwierigkeiten**  
>   
>  In früheren Versionen von Visual Studio wurden globale Eigenschaftenblätter mit der USER-Erweiterung verwendet. Diese befanden sich in dem Ordner \<Benutzerprofil>\AppData\Local\Microsoft\MSBuild\v4.0\. Diese Dateien werden nicht mehr empfohlen, da sie Eigenschaften für Projektkonfigurationen pro Benutzer pro Computer festlegen. Solche "globalen" Einstellungen können Builds beeinträchtigen, insbesondere wenn Sie mehr als eine Zielplattform auf dem Buildcomputer verwenden. Wenn Sie beispielsweise ein MFC-Projekt und ein Windows Phone-Projekt haben, wären die USER-Eigenschaften für eines von ihnen ungültig. Wiederverwendbare Eigenschaftenblätter sind flexibler und stabiler.  
>   
>  USER-Dateien werden noch von Visual Studio installiert und nehmen an der Eigenschaftenvererbung teil, sie sind jedoch standardmäßig leer. Die empfohlene Vorgehensweise besteht darin, den Verweis auf diese Dateien im **Eigenschaften-Manager** zu löschen, um sicherzustellen, dass die Projekte unabhängig von den benutzer- und computerbezogenen Einstellungen funktionieren. Das ist wichtig, um das richtige Verhalten in einer SCC-Umgebung (Quellcodeverwaltung) zu gewährleisten.  
  
 Wenn Sie den **Eigenschaften-Manager** anzeigen möchten, klicken Sie in der Menüleiste auf **Ansicht** > **Weitere Fenster** > **Eigenschaften-Manager**.  
  
 Wenn Sie allgemeine, häufig verwendete Eigenschaften haben, die Sie in mehreren Projekten verwenden möchten, können Sie diese über den **Eigenschaften-Manager** in einer wiederverwendbaren *Eigenschaftenblattdatei* erfassen, deren Erweiterung gemäß der Konvention „.props“ lautet. Sie können das Blatt (oder die Blätter) auf neue Projekte anwenden, sodass Sie dessen Eigenschaften nicht von Grund auf neu festlegen müssen. Sie können auf den **Eigenschaften-Manager** zugreifen, indem Sie auf der Menüleiste auf **Ansicht** > **Eigenschaften-Manager** klicken.  
  
 ![Kontextmenü des Eigenschaften-Managers](../ide/media/sharingnew.png "SharingNew")  
  
 Unter jedem Konfigurationsknoten werden Knoten für jedes Eigenschaftenblatt angezeigt, das für diese Konfiguration gilt. Das System fügt Eigenschaftenblätter, die Werte festlegen, basierend auf den Optionen fest, die Sie im App-Wizard beim Erstellen des Projekts auswählen. Klicken Sie mit der rechten Maustaste auf einen beliebigen Knoten, und wählen Sie „Eigenschaften“ aus, um anzuzeigen, welche Eigenschaften für diesen Knoten gelten. Sämtliche Eigenschaftenblätter werden automatisch in das „Haupteigenschaftenblatt“ des Projekts (ms.cpp.props) importiert und in der Reihenfolge ausgewertet, in der sie im Eigenschaften-Manager angezeigt werden. Sie können sie verschieben, um die Reihenfolge der Auswertung zu ändern. Eigenschaftenblätter, die später ausgewertet werden, überschreiben die Werte der zuvor ausgewerteten Blätter.  
  
 Wenn Sie auf **Neues Projekteigenschaftenblatt hinzufügen** klicken und dann beispielsweise das Eigenschaftenblatt „MyProps.props“ auswählen, wird das Dialogfeld „Eigenschaftenseiten“ geöffnet. Beachten Sie, dass es für das MyProps-Eigenschaftenblatt gilt. Alle Änderungen, die Sie vornehmen, werden in das Blatt und nicht in die Projektdatei (VCXPROJ) geschrieben.  
  
 Eigenschaften in einem Eigenschaftenblatt werden überschrieben, wenn die gleiche Eigenschaft direkt in der VCXPROJ-Datei festgelegt ist.  
  
 Sie können ein Eigenschaftenblatt so oft wie nötig importieren. Mehrere Projekte in einer Projektmappe können Einstellungen aus demselben Eigenschaftenblatt erben, und ein Projekt kann über mehrere Blätter verfügen. Eigenschaftenblätter selbst können Einstellungen von einem anderen Eigenschaftenblatt erben.  
  
 Sie können auch ein Eigenschaftenblatt für mehrere Konfigurationen erstellen. Erstellen Sie dazu ein Eigenschaftenblatt für jede Konfiguration, öffnen Sie das Kontextmenü einer Konfiguration, wählen Sie **Vorhandenes Eigenschaftenblatt hinzufügen** aus, und fügen Sie die anderen Blätter hinzu. Wenn Sie ein gemeinsames Eigenschaftenblatt verwenden, beachten Sie jedoch, dass eine Eigenschaft für alle Konfigurationen festgelegt wird, für die das Blatt gilt. Dabei wird in der IDE nicht angezeigt, welche Projekte oder anderen Eigenschaftenblätter von einem bestimmten Eigenschaftenblatt erben.  
  
 In großen Projektmappen mit zahlreichen Projekten kann es hilfreich sein, ein Eigenschaftenblatt auf Projektmappenebene zu erstellen. Wenn Sie der Projektmappe ein Projekt hinzufügen, fügen Sie über den **Eigenschaften-Manager** das Eigenschaftenblatt dem Projekt hinzu. Bei Bedarf können Sie auf Projektebene ein neues Eigenschaftenblatt hinzufügen, über das projektspezifische Werte festgelegt werden.  
  
> [!IMPORTANT]
>  Eine PROPS-Datei wird standardmäßig nicht in der Quellcodeverwaltung verwendet, da sie nicht als Projektelement erstellt wird. Wenn Sie die Datei in die Quellcodeverwaltung aufnehmen möchten, können Sie sie manuell als Projektmappenelement hinzufügen.  
  
#### <a name="to-create-a-property-sheet"></a>So erstellen Sie ein Eigenschaftenblatt  
  
1.  Klicken Sie in der Menüleiste auf **Ansicht** > **Eigenschaften-Manager**. Der **Eigenschaften-Manager** wird geöffnet.  
  
2.  Um den Umfang des Eigenschaftenblatts zu definieren, wählen Sie das Element aus, auf das es angewendet wird. Dies kann eine bestimmte Konfiguration oder ein anderes Eigenschaftenblatt sein. Öffnen Sie das Kontextmenü für dieses Element, und wählen Sie **Neues Projekteigenschaftenblatt hinzufügen** aus. Geben Sie einen Namen und den Speicherort an.  
  
3.  Öffnen Sie im **Eigenschaften-Manager**das neue Eigenschaftenblatt, und legen Sie dann die Eigenschaften fest, die Sie einschließen möchten.  
  
##  <a name="bkmkPropertyInheritance"></a> Eigenschaftenvererbung  
 Projekteigenschaften sind in Ebenen angelegt. Jede Ebene erbt die Werte der vorherigen Ebene. Ein geerbter Wert kann jedoch überschrieben werden, indem Sie explizit die Eigenschaft festlegen. So sieht die grundlegende Vererbungsstruktur aus:  
  
1.  Standardeinstellungen von MSBuild CPP Toolset („..\Programme\MSBuild\Microsoft.Cpp\v4.0\Microsoft.Cpp.Default.props“, die durch die VCXPROJ-Datei importiert wird)  
  
2.  Eigenschaftenblätter  
  
3.  VCXPROJ-Datei (Kann Standard- und die Eigenschaftenblatteinstellungen überschreiben.)  
  
4.  Elementmetadaten  
  
> [!TIP]
>  Auf einer Eigenschaftenseite wird eine Eigenschaft in `bold` im aktuellen Kontext definiert. Eine Eigenschaft in normaler Schriftart ist geerbt.  
  
 Eine Projektdatei (VCXPROJ) importiert zur Buildzeit andere Eigenschaftenblätter. Nachdem alle Eigenschaftenblätter importiert sind, wird die Projektdatei ausgewertet, und es wird die jeweils letzte Definition der Eigenschaftswerte verwendet. Manchmal ist es hilfreich, die erweiterte Datei anzuzeigen, um zu bestimmen, wie ein bestimmter Eigenschaftswert vererbt wird. Um die erweiterte Version anzuzeigen, geben Sie folgenden Befehl an einer Visual Studio-Eingabeaufforderung ein. (Ändern Sie die Platzhalterdateinamen in die Namen der Dateien, die Sie verwenden möchten.)  
  
 **msbuild /pp:** *temp* **.txt** *myapp* **.vcxproj**  
  
 Erweiterte Projektdateien können sehr groß und schwierig zu verstehen sein, wenn Sie nicht mit MSBuild vertraut sind. So sieht die grundlegende Struktur einer Projektdatei aus:  
  
1.  Grundlegende Projekteigenschaften, die in der IDE nicht verfügbar gemacht werden.  
  
2.  Import von Microsoft.cpp.default.props, die einige einfache, Toolset-unabhängige Eigenschaften definiert.  
  
3.  Globale Konfigurationseigenschaften (verfügbar als Standardeigenschaften **PlatformToolset** und **Project** auf der Seite **Konfiguration > Allgemein**). Diese Eigenschaften bestimmen, welche Toolset- und systeminternen Eigenschaftenblätter im nächsten Schritt in Microsoft.cpp.props importiert werden.  
  
4.  Import von Microsoft.cpp.props, die die meisten Projektstandardwerte festlegt.  
  
5.  Import aller Eigenschaftenblätter, einschließlich USER-Dateien. Diese Eigenschaftenblätter können alle Eigenschaften außer die Standardeigenschaften **PlatformToolset** und **Project** überschreiben.  
  
6.  Die restlichen Eigenschaften der Projektkonfiguration. Diese Werte können das überschreiben, was in den Eigenschaftenblättern festgelegt wurde.  
  
7.  Elemente (Dateien) zusammen mit ihren Metadaten. Diese stellen immer das letzte Wort in den MSBuild-Auswertungsregeln dar, selbst wenn sie vor anderen Eigenschaften und Importen auftreten.  
  
 Weitere Informationen finden Sie unter [MSBuild Properties](/visualstudio/msbuild/msbuild-properties) (MSBuild-Eigenschaften).  
  
## <a name="adding-an-include-directory-to-the-set-of-default-directories"></a>Hinzufügen eines Includeverzeichnisses zu den Standardverzeichnissen  
 Wenn Sie einem Projekt ein Includeverzeichnis hinzufügen, ist es wichtig darauf zu achten, die Standardverzeichnisse nicht zu überschreiben. Die richtige Methode, ein Verzeichnis hinzuzufügen, besteht darin, den neuen Pfad anzufügen (z.B. C:\MeinNeuesIncludeVerz\"), und dann das Makro **$(IncludePath)** an den Eigenschaftswert anzufügen.  
  
## <a name="setting-environment-variables-for-a-build"></a>Einstellungsumgebungsvariablen für einen Build  
 Der Visual C++-Compiler (cl.exe) erkennt bestimmte Umgebungsvariablen, insbesondere LIB, LIBPATH, PATH und INCLUDE. Wenn Sie die Erstellung mit der IDE vornehmen, werden die Eigenschaften, die auf der Eigenschaftenseite [VC++-Verzeichnisse](../ide/vcpp-directories-property-page.md) festgelegt sind, zum Festlegen der Umgebungsvariablen verwendet. Wenn LIB-, LIBPATH- und INCLUDE-Werte bereits festgelegt wurden, beispielsweise durch eine Developer-Eingabeaufforderung, werden diese durch die Werte der entsprechenden MSBuild-Eigenschaften ersetzt. Der Build stellt dann PATH den Wert der ausführbaren Verzeichniseigenschaft VC++-Verzeichnisse voran. Sie können eine benutzerdefinierte Umgebungsvariable festlegen, indem Sie ein benutzerdefiniertes Makro erstellen und dann das Kontrollkästchen **Makro als Umgebungsvariable in Buildumgebung festlegen** aktivieren.  
  
## <a name="setting-environment-variables-for-a-debugging-session"></a>Einstellen von Umgebungsvariablen für eine Debugsitzung  
 Erweitern Sie im linken Bereich des Dialogfelds **Eigenschaftenseiten** die **Konfigurationseigenschaften** des Projekts, und klicken Sie auf **Debugging**. 
  
 Ändern Sie im rechten Bereich die Projekteinstellungen **Umgebung** oder **Mergeumgebung**, und klicken Sie dann auf die Schaltfläche **OK**.  

## <a name="modifying-properties-and-targets-without-changing-the-project-file"></a>Ändern von Eigenschaften und Zielen ohne Änderungen an der Projektdatei
Sie können Projekteigenschaften und -ziele über die MSBuild-Eingabeaufforderung überschreiben, ohne die Projektdatei zu ändern. Dies ist nützlich, wenn Sie einige Eigenschaften vorübergehend oder gelegentlich anwenden möchten. MSBuild-Kenntnisse sind hierbei von Vorteil. Weitere Informationen finden Sie unter [MSBuild](https://docs.microsoft.com/en-us/visualstudio/msbuild/msbuild).

> [!IMPORTANT]
> Sie können den XML-Editor in Visual Studio oder einen beliebigen Text-Editor verwenden, um die PROPS- oder TARGETS-Datei zu erstellen. Verwenden Sie in diesem Szenario nicht den **Eigenschaften-Manager**, da dieser die Eigenschaften zur Projektdatei hinzufügt.

*So überschreiben Sie Projekteigenschaften:*
- Erstellen Sie eine PROPS-Datei, die die Eigenschaften angibt, die Sie überschreiben möchten. 
- Geben Sie über die Eingabeaufforderung Folgendes ein: set ForceImportBeforeCppTargets="C:\sources\my_props.props"
 
*So überschreiben Sie Projektziele:*
1) Erstellen Sie eine TARGETS-Datei mit ihrer Implementierung oder einem bestimmten Ziel.
2) Geben Sie über die Eingabeaufforderung Folgendes ein: set ForceImportAfterCppTargets ="C:\sources\my_target.targets"
 
Sie können diese Optionen auch über die MSBuild-Befehlszeile festlegen, indem Sie die Option „/p:“ verwenden:

```cmd
> msbuild myproject.sln /p:ForceImportBeforeCppTargets="C:\sources\my_props.props" 
> msbuild myproject.sln /p:ForceImportAfterCppTargets="C:\sources\my_target.targets" 
```  

Das Überschreiben von Eigenschaften und Zielen auf diese Weise entspricht dem Hinzufügen folgender Importe zu allen VCXPROJ-Dateien in der Projektmappe:

```cmd 
<Import Project=="C:\sources\my_props.props" />
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
<Import Project==" C:\sources\my_target.targets"" />
```  

## <a name="see-also"></a>Siehe auch  
 [Creating and Managing Visual C++ Projects (Erstellen und Verwalten von Visual C++-Projekten)](../ide/creating-and-managing-visual-cpp-projects.md) [VCXPROJ- und PROPS-Dateistruktur](vcxproj-file-structure.md) [Property page XML files (XML-Dateien für Eigenschaftenseiten)](property-page-xml-files.md)