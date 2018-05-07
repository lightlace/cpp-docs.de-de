---
title: Arbeiten mit Projekteigenschaften | Microsoft Docs
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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="working-with-project-properties"></a>Arbeiten mit Projekteigenschaften
In der IDE werden alle Informationen, die zum Erstellen eines Projekts erforderlich ist als verfügbar gemacht *Eigenschaften*. Diese Informationen umfassen den Namen der Anwendung, Erweiterung (z. B. DLL "," LIB "," EXE "), Compileroptionen, Linkeroptionen, Debuggereinstellungen, benutzerdefinierte Buildschritte und viele andere Dinge. Verwenden Sie in der Regel *Eigenschaftenseiten* ( **Projekt &#124; Eigenschaften**) anzeigen und ändern diese Eigenschaften. 
  
 Wenn Sie ein Projekt erstellen, weist das System Werte für verschiedene Eigenschaften aus. Die Standardwerte, unterscheiden sich geringfügig, je nach Art des Projekts und welche Optionen wählen Sie im Anwendungs-Assistenten. Z. B. eine ATL-Projekt verfügt über Eigenschaften, die im Zusammenhang mit der Dateien "MIDL", aber diese relevant sind in eine basiskonsolenanwendung. Die Standardeigenschaften werden im Bereich Allgemein auf den Eigenschaftenseiten angezeigt:  
  
 ![Visual C#&#43; &#43; Projekt Standardwerte](../ide/media/visual-c---project-defaults.png "standardmäßig von Visual C++-Projekt")  
  
 Einige Eigenschaften, z. B. den Anwendungsnamen, gelten für alle Varianten für den Build, unabhängig von der Zielplattform oder gibt an, ob es sich um eine Debug- oder Releasekonfiguration Build handelt. Aber die meisten Eigenschaften hängen von der Konfiguration ab. Dies ist, da der Compiler muss wissen, welche spezifische Plattform, auf den das Programm ausgeführt wird, und welche bestimmten Compileroptionen verwenden, um den richtigen Code zu generieren. Wenn Sie eine Eigenschaft festlegen, ist es daher wichtig, achten Sie darauf, welche Konfiguration und Plattform, die der neue Wert angewendet werden sollen. Sollten sie gelten nur für Debug Win32-Builds oder sollte er gelten auch für ARM Debuggen und Debug X64? Z. B. die **Optimierung** -Eigenschaft, wird standardmäßig festgelegt ist **Geschwindigkeit maximieren (/ O2)** in einer Release-Konfiguration, aber in der Debugkonfiguration automatisch deaktiviert.  
  
 Die Eigenschaftenseiten werden entwickelt, sodass Sie immer sehen, und wenn nötig ändern, welche Konfiguration und Plattform ein Eigenschaftswert für gelten sollte. Die folgende Abbildung zeigt die Eigenschaftenseiten, mit der Konfiguration und Plattforminformationen in den Listenfeldern oben. Wenn die **Optimierung** Eigenschaft hier festgelegt ist, es gelten nur für Win32 Debug-Builds, das sich in diesem Fall werden die aktive Konfiguration, wie durch rote Pfeile angezeigt.  
  
 ![Visual C#&#43; &#43; Eigenschaftenseiten zeigt aktive Konfiguration](../ide/media/visual-c---property-pages-showing-active-configuration.png "Visual C++-Eigenschaftenseiten zeigt aktive Konfiguration")  
  
 Die folgende Abbildung zeigt die Eigenschaftenseite des gleichen Projekts, aber die Konfiguration wurde in Version geändert. Beachten Sie die anderen Wert für die Eigenschaft für die Optimierung aus. Beachten Sie außerdem, dass die aktive Konfiguration noch Debuggen. Sie können die Eigenschaften für jede Konfiguration hier festlegen. Er hat keine aktiv sein.  
  
 ![Visual C#&#43; &#43; Eigenschaftenseiten mit Version Config](../ide/media/visual-c---property-pages-showing-release-config.png "Visual C++-Eigenschaftenseiten mit Release-Konfiguration")  
  
 Das Projektsystem selbst beruht auf MSBuild, die Dateiformate und die Regeln zum Erstellen von Projekten beliebiger Art definiert. MSBuild verwaltet ein Großteil der Komplexität der Erstellung für mehrere Konfigurationen und Plattformen, aber Sie etwas über die Funktionsweise kennen müssen. Dies ist besonders wichtig, wenn Sie benutzerdefinierte Konfigurationen zu definieren, oder erstellen Sie wiederverwendbare Sätze von Eigenschaften, die Freigabe und in mehrere Projekte importieren möchten.  
  
 Projekteigenschaften werden gespeichert, entweder direkt in der Projektdatei (*.vcxproj) oder in andere XML- oder PROPS-Dateien, die den Project-Datei importiert und die Standardwerte angeben. Wie oben beschrieben, kann die gleiche Eigenschaft für die gleiche Konfiguration einen anderen Wert in verschiedenen Dateien zugewiesen werden. Wenn Sie ein Projekt erstellen, wertet das MSBuild-Modul die Projektdatei und die importierten Dateien in einer klar definierten Reihenfolge (siehe unten). Da jede Datei ausgewertet wird, werden alle Eigenschaftswerte, die in dieser Datei definiert die vorhandenen Werte überschrieben. Alle Werte, die nicht angegeben werden, werden von Dateien geerbt, die zuvor ausgewertet wurden. Wenn Sie eine Eigenschaft mit Eigenschaftenseiten festlegen, ist es daher auch wichtig, achten Sie darauf, in dem Sie festlegen. Wenn Sie eine Eigenschaft auf "X" in eine PROPS-Datei festlegen, aber die Eigenschaft "Y" in der Projektdatei festgelegt ist, wird das Projekt mit der Eigenschaft, legen Sie auf "Y" erstellt. Wenn die gleiche Eigenschaft auf "Z", auf ein Projektelement, z. B. eine CPP-Datei festgelegt ist, verwendet das MSBuild-Modul den Wert "Z". Weitere Informationen finden Sie unter [eigenschaftenvererbung](#bkmkPropertyInheritance) weiter unten in diesem Artikel.  
  
## <a name="build-configurations"></a>Buildkonfigurationen  
 Eine Konfiguration ist nur eine beliebige Gruppe von Eigenschaften, die ein Name zugewiesen werden. Visual Studio bietet Debug- und Releasekonfigurationen und jede werden verschiedene Eigenschaften für einen Debugbuild oder Releasebuild entsprechend festgelegt. Sie können der **Configuration Manager** , benutzerdefinierte Konfigurationen als eine einfache Möglichkeit, Gruppeneigenschaften für eine bestimmte Art von Build zu definieren. Eigenschaften-Manager für erweiterte arbeiten mit Eigenschaften verwendet, aber wir stellen da mit ihrer Hilfe Eigenschaftenkonfigurationen visualisieren hier vor. Sie greifen über **Ansicht &#124; Eigenschaften-Manager** oder **Ansicht &#124; Weitere Fenster &#124; Eigenschaften-Manager** je nach Ihren Einstellungen. Es hat die Knoten für jedes Paar Configuration/Plattform im Projekt. Unter jedem dieser Knoten können Sie Knoten für Eigenschaftenblätter (PROPS-Dateien), die einige spezifischen Eigenschaften für diese Konfiguration festgelegt sind.  
  
 ![Eigenschaften-Manager](../ide/media/property-manager.png "Eigenschaften-Manager")  
  
 Wenn Sie wechseln Sie zum Bereich "Allgemein" auf den Eigenschaftenseiten (finden Sie unter der Abbildung oben), und die Zeichensatz-Eigenschaft auf "Nicht konfiguriert" anstelle von "Verwenden von Unicode" festgelegt, und klicken Sie auf **OK**, Eigenschaften-Manager zeigt keine **Unicode-Unterstützung** Eigenschaftenblatt für die aktuelle Konfiguration, sondern werden trotzdem gibt es für andere Konfigurationen.  
  
 Weitere Informationen zu Eigenschaften-Manager und Eigenschaftenblätter, finden Sie unter [Erstellen von wiederverwendbaren Eigenschaftenkonfigurationen](#bkmkPropertySheets) weiter unten in diesem Artikel.  
  
> [!TIP]
>  Die User-Datei ist eine ältere Funktion und es wird empfohlen, dass Sie es löschen, um die Eigenschaften ordnungsgemäß gruppiert nach Konfiguration-Plattform zu halten.  
  
## <a name="target-platforms"></a>Zielplattformen  
 *Zielplattform* bezieht sich auf die Art des Gerätetyps und/oder Betriebssystem, unter dem die ausführbare Datei ausgeführt wird. Sie können ein Projekt für mehrere Plattformen erstellen. Zielplattformen für C++-Projekte verfügbar hängen von der Art des Projekts ab. Sie enthalten sind jedoch nicht beschränkt auf Win32 X64, ARM, Android und iOS.     Die **X86** Zielplattform, die eventuell in Communityinhalten **Configuration Manager** ist identisch mit **Win32** in systemeigenen C++-Projekten. Win32 bedeutet, dass Windows 32-Bit- und **X64** bedeutet, dass 64-Bit-Windows. Weitere Informationen zu dieser beiden Plattformen finden Sie unter [Ausführen von 32-Bit-Anwendungen](https://msdn.microsoft.com/library/windows/desktop/aa384249\(v=vs.85\).aspx).  
  
 Die **Any CPU** Plattform Zielwert, die eventuell in Communityinhalten **Configuration Manager** hat keine Auswirkung auf systemeigene C++-Projekten; sie ist relevant für die C + c++ / CLI und anderen Projekttypen. Weitere Informationen finden Sie unter [/CLRIMAGETYPE (Angeben des CLR-Bildtyps)](../build/reference/clrimagetype-specify-type-of-clr-image.md).  
  
## <a name="property-pages"></a>Eigenschaftenseiten  
 Wie bereits erwähnt, basiert auf der Visual C++-Projektsystem [MSBuild](/visualstudio/msbuild/msbuild-properties) und die Werte sind gespeichert in der XML-Projektdatei an Standardeinstellung props und TARGETS-Dateien. Für Visual Studio 2015, befinden sich diese Dateien im **\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\V140**. Für Visual Studio 2017 befinden sich diese Dateien im  **\\Programmdateien (x86)\\Microsoft Visual Studio\\2017\\_Edition_\\Common7\\ IDE\\VC\\VCTargets**, wobei _Edition_ der Visual Studio-Edition installiert ist. Eigenschaften werden auch in eine beliebige benutzerdefinierte PROPS-Dateien gespeichert, die Sie Ihrem Projekt hinzufügen können. Es wird dringend empfohlen, dass Sie nicht die Dateien manuell bearbeiten, und stattdessen die Eigenschaftenseiten in der IDE alle Eigenschaften, insbesondere solche, die ändern, die bei der Vererbung, einbezogen werden, es sei denn, Sie eine sehr gute Kenntnisse von MSBuild haben verwenden.  
  
 Die folgende Abbildung zeigt die Eigenschaftenseiten für ein Visual C++-Projekt. Im linken Bereich die **VC++-Verzeichnisse *** Regel* ausgewählt ist, und im rechten Bereich listet die Eigenschaften, die dieser Regel zugeordnet sind. Die `$(...)` Werte heißen leider *Makros*. Hierbei handelt es sich *nicht* C/C++-Makros, aber einfach kompilierungszeitskonstanten. Makros werden in erläutert die [Eigenschaft Seite Makros](#bkmkPropertiesVersusMacros) Abschnitt weiter unten in diesem Artikel.)  
  
 ![Projekt-Eigenschaftenseiten](../ide/media/project_property_pages_vc.png "Project_Property_Pages_VC")  
  
> [!WARNING]
>  Die **allgemeine Eigenschaften** -Konfigurationen in älteren Versionen von Visual Studio wurden entfernt. Um einen Verweis auf ein Projekt hinzufügen möchten, verwenden Sie jetzt die **Verweis hinzufügen** Dialogfeld auf die gleiche Weise wie für verwaltete Sprachen. Finden Sie unter [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project).  
  
#### <a name="to-set-a-property-for-a-project"></a>So legen Sie eine Eigenschaft für ein Projekt fest  
  
1.  In den meisten Szenarien können Sie Eigenschaften auf Projektebene festlegen, ohne ein benutzerdefiniertes Eigenschaftenblatt erstellen. Wählen Sie im Hauptmenü **Projekt &#124; Eigenschaften**, oder mit der rechten Maustaste auf den Projektknoten in **Projektmappen-Explorer** , und wählen Sie **Eigenschaften**.  
  
2.  Verwenden der **Konfiguration** und **Plattform** Listenfeldern oben im Dialogfeld, um anzugeben, welche Eigenschaftengruppen Ihre Änderungen angewendet werden sollen. In vielen Fällen **alle Plattformen** und **alle Konfigurationen** die richtige Wahl. Zum Festlegen von Eigenschaften für einige Konfigurationen mit mehrfacher Auswahl bei **Eigenschaften-Manager**, und öffnen Sie das Kontextmenü, und wählen Sie **Eigenschaften**.  
  
 Die **Eigenschaftenseiten** Dialogfeld zeigt nur die Eigenschaftenseiten, die für das aktuelle Projekt gelten. Wenn das Projekt beispielsweise keine IDL-Datei enthält, wird die MIDL-Eigenschaftenseite nicht angezeigt.  
  
 Wenn Sie eine Eigenschaft auf einer Eigenschaftenseite hervorheben, drücken Sie **F1** zu einem Referenzthema für Weitere Informationen zu den entsprechenden Compiler oder Linker Switch wechseln.  
  
 Weitere Informationen zu den einzelnen Eigenschaftenseiten finden Sie in den folgenden Themen:  
  
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
  
## <a name="to-quickly-browse-and-search-all-properties"></a>So durchsuchen Sie einfach alle Sucheigenschaften  
 Die **alle Optionen** Eigenschaftenseite (unter der **Konfigurationseigenschaften &#124; C/C++-** Knoten in der **Eigenschaftenseiten** Dialogfeld) bietet eine schnelle Möglichkeit zum Suchen und Durchsuchen die Eigenschaften, die im aktuellen Kontext verfügbar sind. Über ein spezielles Suchfeld und eine einfache Syntax können Sie Ergebnisse filtern:  
  
 Kein Präfix:  
 Suche nur in den Eigenschaftennamen (untergeordnete Zeichenfolge ohne Berücksichtigung der Groß-/Kleinschreibung)  
  
 '/' oder '-' :  
 Suche nur in den Compilerschaltern (Präfix ohne Berücksichtigung der Groß-/Kleinschreibung)  
  
 v:  
 Suche nur in Werten (untergeordnete Zeichenfolge ohne Berücksichtigung der Groß-/Kleinschreibung)  
  
##  <a name="bkmkPropertiesVersusMacros"></a> Eigenschaft-Seite-Makros  
 Ein *Makro* wird eine Kompilierzeitkonstante, die auf einen Wert, der von Visual Studio oder das MSBuild-System definiert ist, oder klicken Sie auf einen benutzerdefinierten Wert verweisen kann. Mit Makros anstelle von hartcodierten Werte wie Verzeichnispfaden können Eigenschafteneinstellungen zwischen Computern und verschiedenen Versionen von Visual Studio einfacher freigegeben werden. Zudem können Sie besser sicherstellen, dass die Projekteinstellungen ordnungsgemäß an der Eigenschaftenvererbung teilnehmen. Sie können den Eigenschaften-Editor verwenden, um die Werte aller verfügbarer Makros anzuzeigen.  
  
### <a name="predefined-macros"></a>Vordefinierte Makros  
 Globale Makros  
 Gilt für alle Elemente in einer Projektkonfiguration. Besitzt die Syntax `$(name)`. Ein Beispiel eines globalen Makros ist `$(VCInstallDir)`, das das Stammverzeichnis der Visual Studio-Installation speichert. Ein globales Makro entspricht einer `PropertyGroup` in MSBuild.  
  
 Elementmakros  
 Besitzt die Syntax `%(name)`. Bei einer Datei gilt ein Elementmakro nur für diese Datei – z. B. können Sie `%(AdditionalIncludeDirectories)` verwenden, um Includeverzeichnisse anzugeben, die nur für eine bestimmte Datei gelten. Diese Art des Elementmakros entspricht den `ItemGroup`-Metadaten in MSBuild. Wenn ein Elementmakro im Zusammenhang mit einer Projektkonfiguration verwendet wird, gilt es für alle Dateien eines bestimmten Typs. Z. B. die C/C++ **Präprozessordefinitionen** Konfigurationseigenschaft dauert eine `%(PreprocessorDefinitions)` -Elementmakro verwenden, die für alle cpp-Dateien im Projekt gilt. Diese Art des Elementmakros entspricht den `ItemDefinitionGroup`-Metadaten in MSBuild. Weitere Informationen finden Sie unter [Item Definitions](/visualstudio/msbuild/item-definitions) (Elementdefinitionen).  
  
### <a name="user-defined-macros"></a>benutzerdefinierte Makros  
 Sie können erstellen *benutzerdefinierte Makros* als Variablen in Projektbuilds zu verwenden. Sie können z. B. ein benutzerdefiniertes Makro erstellen, das einen Wert für einen benutzerdefinierten Buildschritt oder ein benutzerdefiniertes Buildtool bereitstellt. Ein benutzerdefiniertes Makro ist ein Name-Wert-Paar. Verwenden Sie in einer Projektdatei die **$(***Namen***)** Notation, um auf den Wert zuzugreifen.  
  
 Ein benutzerdefiniertes Makro wird in einem Eigenschaftenblatt gespeichert. Wenn das Projekt nicht bereits ein Eigenschaftenblatt enthält, können Sie einen, indem Sie die Schritte unter Erstellen [Erstellen von wiederverwendbaren Eigenschaftenkonfigurationen](#bkmkPropertySheets).  
  
##### <a name="to-create-a-user-defined-macro"></a>So erstellen Sie ein benutzerdefiniertes Makro  
  
1.  In der **Eigenschaften-Manager** Fenster (Wählen Sie in der Menüleiste **Ansicht**, **Eigenschaften-Manager**), öffnen Sie das Kontextmenü für ein Eigenschaftenblatt (der Name endet auf. User), und wählen Sie dann Eigenschaften. Die **Eigenschaftenseiten** für dieses Eigenschaftenblatt wird geöffnet.  
  
2.  Wählen Sie im linken Bereich des Dialogfelds **Benutzermakros**. Wählen Sie im rechten Bereich die **Makro hinzufügen** die Schaltfläche, um die **Benutzermakro hinzufügen** (Dialogfeld).  
  
3.  Geben Sie im Dialogfeld einen Namen und einen Wert für das Makro an. Wählen Sie optional die **Makro als Umgebungsvariable in Buildumgebung festlegen** Kontrollkästchen.  
  
## <a name="property-editor"></a>Eigenschaften-Editor  
 Mit dem Eigenschaften-Editor können Sie bestimmte Zeichenfolgeneigenschaften ändern und Makros als Werte auswählen. Um auf den Eigenschaften-Editor zuzugreifen, wählen Sie eine Eigenschaft auf einer Eigenschaftenseite aus, und klicken Sie rechts auf die Schaltfläche mit dem Pfeil nach unten. Wenn die Dropdown Liste enthält  **\<Bearbeiten >**, können Sie sie zum Anzeigen der Eigenschaften-Editor für diese Eigenschaft auswählen.  
  
 ![Eigenschaft&#95;Editor&#95;Dropdownliste](../ide/media/property_editor_dropdown.png "Property_Editor_Dropdown")  
  
 In den Eigenschaften-Editor können Sie wählen die **Makros** Schaltfläche, um die verfügbaren Makros und deren aktuelle Werte anzuzeigen. Die folgende Abbildung zeigt die Eigenschaften-Editor für den **Zusätzliche Includeverzeichnisse** Eigenschaft nach der **Makros** Schaltfläche ausgewählt wurde. Wenn die **vom übergeordneten oder ein Projekt standardmäßig erben** Kontrollkästchen aktiviert ist und Sie einen neuen Wert hinzufügen, wird dieser angefügt, um alle Werte, die derzeit vererbt werden. Wenn Sie das Kontrollkästchen deaktivieren, ersetzt der neue Wert die vererbten Werte. In den meisten Fällen bleibt das Kontrollkästchen aktiviert.  
  
 ![Eigenschaften-Editor, Visual C#&#43;&#43;](../ide/media/propertyeditorvc.png "PropertyEditorVC")  
  
##  <a name="bkmkPropertySheets"></a> Erstellen von wiederverwendbaren Eigenschaftenkonfigurationen  
 Sie können zwar "globale" Eigenschaften für einen Benutzer und Computer festlegen, dies wird jedoch nicht mehr empfohlen. Stattdessen empfehlen wir die Verwendung von **Eigenschaften-Manager** zum Erstellen einer *Eigenschaftenblatt* um die Einstellungen für jede Art von Projekt zu speichern, die Sie möglicherweise wiederverwenden oder freigeben möchten. Über Eigenschaftenblätter verringern Sie zudem die Wahrscheinlichkeit, dass Eigenschafteneinstellungen für andere Projekttypen versehentlich geändert werden. Eigenschaftenblätter werden ausführlicher [Erstellen von wiederverwendbaren Eigenschaftenkonfigurationen](#bkmkPropertySheets).  
  
> [!IMPORTANT]
>  **User-Dateien und schwierigkeiten**  
>   
>  In früheren Versionen von Visual Studio kamen globale Eigenschaftenblätter mit der .user-Dateinamenerweiterung diese befanden sich in der \<Userprofile > Ordner \AppData\Local\Microsoft\MSBuild\v4.0\. Diese Dateien werden nicht mehr empfohlen, da sie Eigenschaften für Projektkonfigurationen pro Benutzer pro Computer festlegen. Solche "globalen" Einstellungen können Builds beeinträchtigen, insbesondere wenn Sie mehr als eine Zielplattform auf dem Buildcomputer verwenden. Wenn Sie beispielsweise ein MFC-Projekt und ein Windows Phone-Projekt haben, wären die USER-Eigenschaften für eines von ihnen ungültig. Wiederverwendbare Eigenschaftenblätter sind flexibler und stabiler.  
>   
>  USER-Dateien werden noch von Visual Studio installiert und nehmen an der Eigenschaftenvererbung teil, sie sind jedoch standardmäßig leer. Die bewährte Methode ist, löschen Sie den Verweis auf diese Dateien im **Eigenschaften-Manager** um sicherzustellen, dass Ihre Projekte unabhängig von alle pro-Benutzer ausgeführt werden, computerspezifische Einstellungen Dies ist wichtig, um sicherzustellen, dass richtige Verhalten in einer SCC (Quellcode -Steuerelement)-Umgebung.  
  
 Anzuzeigende **Eigenschaften-Manager**, wählen Sie in der Menüleiste **Ansicht**, **Weitere Fenster**, **Eigenschaften-Manager**.  
  
 Wenn Sie einen allgemeinen, häufig verwendeten Satz von Eigenschaften, die Sie für mehrere Projekte anwenden möchten verfügen, können Sie **Eigenschaften-Manager** werden in einer wiederverwendbaren erfassen *Eigenschaftenblatt* -Datei, die gemäß der Konvention ist eine props-Dateinamenerweiterung. Sie können das Blatt (oder die Blätter) auf neue Projekte anwenden, sodass Sie dessen Eigenschaften nicht von Grund auf neu festlegen müssen. Für den Zugriff auf **Eigenschaften-Manager**, wählen Sie in der Menüleiste **Ansicht**, **Eigenschaften-Manager**.  
  
 ![Kontextmenü des Eigenschaften-Manager](../ide/media/sharingnew.png "gemeinsame Nutzung von Indizesneue")  
  
 Unter den einzelnen Konfigurationsknoten finden Sie unter Knoten für jede Eigenschaftenblatt, die für diese Konfiguration gilt. Das System fügt Eigenschaftenblätter, die Werte auf Grundlage der gewählten Optionen im Anwendungs-Assistenten beim Erstellen des Projekts festgelegt. Mit der rechten Maustaste in einen beliebigen Knoten, und wählen Sie Eigenschaften um die Eigenschaften anzuzeigen, die für diesen Knoten gelten. Alle Eigenschaftenblätter werden automatisch in das Projekt "master" Eigenschaftenblatt (ms.cpp.props) importiert und werden ausgewertet, in der Reihenfolge, die sie im Eigenschaften-Manager angezeigt werden. Sie können diese zu ändern, die Reihenfolge der Auswertung von verschieben. Eigenschaftenblätter, die später ausgewertet werden, werden die Werte in Blättern zuvor ausgewertet überschrieben.  
  
 Falls gewünscht **Neues Projekteigenschaftenblatt hinzufügen** auswählen, und dann beispielsweise das MyProps.props-Eigenschaftenblatt eine Eigenschaftenseiten-Dialogfeld geöffnet. Beachten Sie, dass es für das MyProps-Eigenschaftenblatt gilt. Alle Änderungen, die Sie vornehmen, werden in das Blatt und nicht in die Projektdatei (VCXPROJ) geschrieben.  
  
 Eigenschaften in einem Eigenschaftenblatt werden überschrieben, wenn die gleiche Eigenschaft direkt in der VCXPROJ-Datei festgelegt ist.  
  
 Sie können ein Eigenschaftenblatt so oft wie nötig importieren. Mehrere Projekte in einer Projektmappe können Einstellungen aus demselben Eigenschaftenblatt erben, und ein Projekt kann über mehrere Blätter verfügen. Eigenschaftenblätter selbst können Einstellungen von einem anderen Eigenschaftenblatt erben.  
  
 Sie können auch ein Eigenschaftenblatt für mehrere Konfigurationen erstellen. Zu diesem Zweck erstellen Sie ein Eigenschaftenblatt für jede Konfiguration, öffnen Sie das Kontextmenü für eine der Datenbanken, wählen Sie **Vorhandenes Eigenschaftenblatt hinzufügen**, und fügen Sie dann die anderen Blätter hinzu. Wenn Sie ein gemeinsames Eigenschaftenblatt verwenden, beachten Sie jedoch, dass eine Eigenschaft für alle Konfigurationen festgelegt wird, für die das Blatt gilt. Dabei wird in der IDE nicht angezeigt, welche Projekte oder anderen Eigenschaftenblätter von einem bestimmten Eigenschaftenblatt erben.  
  
 In großen Projektmappen mit zahlreichen Projekten kann es hilfreich sein, ein Eigenschaftenblatt auf Projektmappenebene zu erstellen. Wenn Sie ein Projekt zur Projektmappe hinzufügen, verwenden Sie **Eigenschaften-Manager** das Eigenschaftenblatt dem Projekt hinzufügen. Bei Bedarf können Sie auf Projektebene ein neues Eigenschaftenblatt hinzufügen, über das projektspezifische Werte festgelegt werden.  
  
> [!IMPORTANT]
>  Eine PROPS-Datei wird standardmäßig nicht in der Quellcodeverwaltung verwendet, da sie nicht als Projektelement erstellt wird. Wenn Sie die Datei in die Quellcodeverwaltung aufnehmen möchten, können Sie sie manuell als Projektmappenelement hinzufügen.  
  
#### <a name="to-create-a-property-sheet"></a>So erstellen Sie ein Eigenschaftenblatt  
  
1.  Wählen Sie in der Menüleiste **Ansicht**, **Eigenschaften-Manager**. Die **Eigenschaften-Manager** wird geöffnet.  
  
2.  Um den Umfang des Eigenschaftenblatts zu definieren, wählen Sie das Element aus, auf das es angewendet wird. Dies kann eine bestimmte Konfiguration oder ein anderes Eigenschaftenblatt sein. Öffnen Sie das Kontextmenü für dieses Element aus, und wählen Sie dann **Neues Projekteigenschaftenblatt hinzufügen**. Geben Sie einen Namen und den Speicherort an.  
  
3.  In **Eigenschaften-Manager**, öffnen Sie das neue Eigenschaftenblatt, und legen Sie dann die Eigenschaften, die Sie einschließen möchten.  
  
##  <a name="bkmkPropertyInheritance"></a> Eigenschaftenvererbung  
 Projekteigenschaften sind in Ebenen angelegt. Jede Ebene erbt die Werte der vorherigen Ebene. Ein geerbter Wert kann jedoch überschrieben werden, indem Sie explizit die Eigenschaft festlegen. So sieht die grundlegende Vererbungsstruktur aus:  
  
1.  Standardeinstellungen von MSBuild CPP Toolset („..\Programme\MSBuild\Microsoft.Cpp\v4.0\Microsoft.Cpp.Default.props“, die durch die VCXPROJ-Datei importiert wird)  
  
2.  Eigenschaftenblätter  
  
3.  VCXPROJ-Datei (Kann Standard- und die Eigenschaftenblatteinstellungen überschreiben.)  
  
4.  Elementmetadaten  
  
> [!TIP]
>  Auf einer Eigenschaftenseite wird eine Eigenschaft in `bold` ist im aktuellen Kontext definiert. Eine Eigenschaft in normaler Schriftart ist geerbt.  
  
 Eine Projektdatei (VCXPROJ) importiert zur Buildzeit andere Eigenschaftenblätter. Nachdem alle Eigenschaftenblätter importiert sind, wird die Projektdatei ausgewertet, und es wird die jeweils letzte Definition der Eigenschaftswerte verwendet. Manchmal ist es hilfreich, die erweiterte Datei anzuzeigen, um zu bestimmen, wie ein bestimmter Eigenschaftswert vererbt wird. Um die erweiterte Version anzuzeigen, geben Sie folgenden Befehl an einer Visual Studio-Eingabeaufforderung ein. (Ändern Sie die Platzhalterdateinamen in die Namen der Dateien, die Sie verwenden möchten.)  
  
 **msbuild /pp:** *temp* **.txt** *myapp* **.vcxproj**  
  
 Erweiterte Projektdateien können sehr groß und schwierig zu verstehen sein, wenn Sie nicht mit MSBuild vertraut sind. So sieht die grundlegende Struktur einer Projektdatei aus:  
  
1.  Grundlegende Projekteigenschaften, die in der IDE nicht verfügbar gemacht werden.  
  
2.  Import von Microsoft.cpp.default.props, die einige einfache, Toolset-unabhängige Eigenschaften definiert.  
  
3.  Globale Konfigurationseigenschaften (verfügbar gemacht werden, als **PlatformToolset** und **Projekt** Standardeigenschaften für die **Konfiguration – Allgemein** Seite. Diese Eigenschaften bestimmen, welche Toolset- und systeminternen Eigenschaftenblätter im nächsten Schritt in Microsoft.cpp.props importiert werden.  
  
4.  Import von Microsoft.cpp.props, die die meisten Projektstandardwerte festlegt.  
  
5.  Import aller Eigenschaftenblätter, einschließlich USER-Dateien. Diese Eigenschaftenblätter können überschreiben, alles mit Ausnahme der **PlatformToolset** und **Projekt** Standardeigenschaften.  
  
6.  Die restlichen Eigenschaften der Projektkonfiguration. Diese Werte können das überschreiben, was in den Eigenschaftenblättern festgelegt wurde.  
  
7.  Elemente (Dateien) zusammen mit ihren Metadaten. Diese stellen immer das letzte Wort in den MSBuild-Auswertungsregeln dar, selbst wenn sie vor anderen Eigenschaften und Importen auftreten.  
  
 Weitere Informationen finden Sie unter [MSBuild Properties](/visualstudio/msbuild/msbuild-properties) (MSBuild-Eigenschaften).  
  
## <a name="adding-an-include-directory-to-the-set-of-default-directories"></a>Hinzufügen eines Includeverzeichnisses zu den Standardverzeichnissen  
 Wenn Sie einem Projekt ein Includeverzeichnis hinzufügen, ist es wichtig darauf zu achten, die Standardverzeichnisse nicht zu überschreiben. Die richtige Methode, ein Verzeichnis hinzuzufügen, fügen den neuen Pfad anzufügen, z. B. ist "C:\MyNewIncludeDir\", und dann die **$(IncludePath)** Makro, das den Wert der Eigenschaft.  
  
## <a name="setting-environment-variables-for-a-build"></a>Einstellungsumgebungsvariablen für einen Build  
 Der Visual C++-Compiler (cl.exe) erkennt bestimmte Umgebungsvariablen, insbesondere LIB, LIBPATH, PATH und INCLUDE. Wenn Sie die Erstellung mit der IDE, die Eigenschaften, die festgelegt werden, in der [VC++-Verzeichnisse Eigenschaftenseite](../ide/vcpp-directories-property-page.md) Eigenschaftenseite dienen zum Festlegen der Umgebungsvariablen. Wenn LIB-, LIBPATH- und INCLUDE-Werte bereits festgelegt wurden, beispielsweise durch eine Developer-Eingabeaufforderung, werden diese durch die Werte der entsprechenden MSBuild-Eigenschaften ersetzt. Der Build stellt dann PATH den Wert der ausführbaren Verzeichniseigenschaft VC++-Verzeichnisse voran. Sie können eine benutzerdefinierte Umgebungsvariable festlegen, durch Erstellen eines benutzerdefinierten Makros und dann das Kontrollkästchen **Makro als Umgebungsvariable in Buildumgebung festlegen**.  
  
## <a name="setting-environment-variables-for-a-debugging-session"></a>Einstellen von Umgebungsvariablen für eine Debugsitzung  
 Im linken Bereich des Projekts auf der **Eigenschaftenseiten** Dialogfeld erweitern Sie **Konfigurationseigenschaften** und wählen Sie dann **Debuggen**. 
  
 Ändern Sie im rechten Bereich die **Umgebung** oder **Mergeumgebung** projekteinstellungen, und wählen Sie dann die **OK** Schaltfläche.  

## <a name="modifying-properties-and-targets-without-changing-the-project-file"></a>Ändern von Eigenschaften und Ziele ohne Ändern der Projektdatei
Sie können Projekteigenschaften und Ziele über die Eingabeaufforderung MSBuild ohne Ändern der Projektdatei überschreiben. Dies ist hilfreich, wenn Sie einige Eigenschaften vorübergehend oder gelegentlich anwenden möchten. Es wird davon ausgegangen, einige Kenntnisse von MSBuild. Weitere Informationen finden Sie unter [MSBUild](https://docs.microsoft.com/en-us/visualstudio/msbuild/msbuild).

> [!IMPORTANT]
> Der XML-Editor in Visual Studio oder einem beliebigen Texteditor können Sie um die props oder TARGETS-Datei zu erstellen. Verwenden Sie nicht die **Eigenschaften-Manager** in diesem Szenario, da sie die Eigenschaften der Projektdatei hinzufügt.

*So überschreiben Sie die Projekteigenschaften:*
- Erstellen Sie eine PROPS-Datei, die angibt, die Eigenschaften, die Sie überschreiben möchten. 
- Von der Befehlszeile aus: ForceImportBeforeCppTargets="C:\sources\my_props.props festlegen"
 
*Projektziele überschreiben:*
1) Erstellen Sie eine TARGETS-Datei mit ihrer Implementierung oder ein bestimmtes Ziel
2) Von der Befehlszeile aus: Legen Sie ForceImportAfterCppTargets = "C:\sources\my_target.targets"
 
Sie können auch die beiden Optionen in der Msbuild-Befehlszeile festlegen, mithilfe der Option/p::

```cmd
> msbuild myproject.sln /p:ForceImportBeforeCppTargets="C:\sources\my_props.props" 
> msbuild myproject.sln /p:ForceImportAfterCppTargets="C:\sources\my_target.targets" 
```  

Überschreiben von Eigenschaften und Ziele auf diese Weise ist gleichbedeutend mit dem folgenden Importe für alle vcxproj-Dateien in der Projektmappe hinzufügen:

```cmd 
<Import Project=="C:\sources\my_props.props" />
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
<Import Project==" C:\sources\my_target.targets"" />
```  

## <a name="see-also"></a>Siehe auch  
 [Erstellen und Verwalten von Visual C++-Projekten](../ide/creating-and-managing-visual-cpp-projects.md) [VCXPROJ und props-Dateistruktur](vcxproj-file-structure.md) [Eigenschaft Seite XML-Dateien](property-page-xml-files.md)