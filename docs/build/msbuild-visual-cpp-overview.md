---
title: "&#220;bersicht &#252;ber MSBuild (Visual C++)"
ms.custom: na
ms.date: "12/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Übersicht über MSBuild"
ms.assetid: dd258f6f-ab51-48d9-b274-f7ba911d05ca
caps.latest.revision: 17
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# &#220;bersicht &#252;ber MSBuild (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MSBuild ist das Standardbuildsystem für Visual C++-Projekte. Wenn Sie ein Projekt in der integrierten Entwicklungsumgebung von Visual Studio (IDE) erstellen, werden das Tool "msbuild.exe", eine XML-basierte Projektdatei und optionale Einstellungsdateien verwendet. Obwohl Sie "msbuild.exe" und eine Projektdatei in der Befehlszeile verwenden können, stellt die IDE eine Benutzeroberfläche zur leichteren Konfiguration von Einstellungen und Erstellung von Projekten bereit. In dieser Übersicht wird beschrieben, wie Visual C++ das MSBuild-System verwendet.  
  
## <a name="prerequisites"></a>Voraussetzungen  
 Lesen Sie die folgenden Dokumente zu MSBuild.  
  
 [MSBuild](MSBuild1.md)  
 Übersicht über MSBuild-Konzepte.  
  
 [MSBuild-Referenz](../Topic/MSBuild%20Reference.md)  
 Referenzinformationen zum MSBuild-System.  
  
 [Referenz zum Projektdateischema](../Topic/MSBuild%20Project%20File%20Schema%20Reference.md)  
 Führt die MSBuild-XML-Schemaelemente, ihre Attribute sowie die übergeordneten und untergeordneten Elemente auf. Beachten Sie insbesondere die [ItemGroup](../Topic/ItemGroup%20Element%20\(MSBuild\).md), [PropertyGroup](../Topic/PropertyGroup%20Element%20\(MSBuild\).md), [Ziel](../Topic/Target%20Element%20\(MSBuild\).md), und [Aufgabe](../Topic/Task%20Element%20\(MSBuild\).md) Elemente.  
  
 [Befehlszeilenreferenz](../Topic/MSBuild%20Command-Line%20Reference.md)  
 Beschreibt die Befehlszeilenargumente und die Optionen, die Sie mit „msbuild.exe“ verwenden können.  
  
 [Referenz zu Aufgaben](../Topic/MSBuild%20Task%20Reference.md)  
 Beschreibt MSBuild-Aufgaben. Achten Sie gesondert auf diese Aufgaben, die für Visual C++ spezifisch sind: [BscMake-Aufgabe](../Topic/BscMake%20Task.md), [CL-Aufgabe](../Topic/CL%20Task.md), [CPPClean-Aufgabe](../Topic/CPPClean%20Task.md), [LIB-Aufgabe](../Topic/LIB%20Task.md), [Link-Aufgabe](../Topic/Link%20Task.md), [MIDL-Aufgabe](../Topic/MIDL%20Task.md), [MT-Aufgabe](../Topic/MT%20Task.md), [RC-Aufgabe](../Topic/RC%20Task.md), [SetEnv-Aufgabe](../Topic/SetEnv%20Task.md), [VCMessage-Aufgabe](../Topic/VCMessage%20Task.md), [XDCMake-Aufgabe](../Topic/XDCMake%20Task.md), [XSD-Aufgabe](../Topic/XSD%20Task.md).  
  
## <a name="msbuild-on-the-command-line"></a>MSBuild in der Befehlszeile  
 Die folgende Anweisung aus der [-Befehlszeilenreferenz](../Topic/MSBuild%20Command-Line%20Reference.md) Dokument veranschaulicht, dass das Tool "msbuild.exe" ein implizites oder explizites dauert `project file` -Argument (eine VCXPROJ-Datei für Visual C++-Projekte) und 0 (null) oder mehr Befehlszeile `options`.  
  
 **msbuild.exe [** `project file` **] [** `options` **]**  
  
 Verwenden der **/target** (oder **/t**) und **Befehlszeilenschalter/Property** (oder **/p**) Befehlszeilenoptionen zum Überschreiben von Eigenschaften und Ziele, die in der Projektdatei angegeben werden.  
  
 Eine wesentliche Funktion der Projektdatei ist an ein *Ziel*, also auf eine bestimmte Operation auf das Projekt und die Eingaben und Ausgaben, die zum Ausführen der Operation erforderlich sind. Eine Projektdatei kann ein oder mehrere Ziele angeben, zu denen auch ein Standardziel gehören kann.  
  
 Jedes Ziel besteht aus einer Folge von einem oder mehreren *Aufgaben*. Jede Aufgabe wird durch eine .NET Framework-Klasse dargestellt, die einen ausführbaren Befehl enthält. Zum Beispiel die [CL-Aufgabe](../Topic/CL%20Task.md) enthält die [cl.exe](../build/reference/compiling-a-c-cpp-program.md) Befehl.  
  
 Ein *Aufgabenparameter* ist eine Eigenschaft der Klassenaufgabe und stellt in der Regel eine Befehlszeilenoption des ausführbaren Befehls dar. Z. B. der `FavorSizeOrSpeed` Parameter von der `CL` Aufgabe entspricht der **/OS** und **/Ot** Compileroptionen.  
  
 Zusätzliche Aufgabenparameter unterstützen die MSBuild-Infrastruktur. Der `Sources`-Aufgabenparameter gibt z. B. einen Satz von Aufgaben an, die von anderen Aufgaben genutzt werden können. Weitere Informationen zu MSBuild-Aufgaben, finden Sie unter [Aufgabenreferenz](../Topic/MSBuild%20Task%20Reference.md).  
  
 Die meisten Aufgaben erfordern Eingaben und Ausgaben, z. B. Dateinamen, Pfade und Zeichenfolgenparameter bzw. numerische oder boolesche Parameter. Eine allgemeine Eingabe ist z. B. der Name einer zu kompilierenden CPP-Quelldatei. Ein wichtiger Eingabeparameter ist eine Zeichenfolge, die die Buildkonfiguration Plattform, z. B. "Debug & #124 und; Win32 ". Eingaben und Ausgaben werden von einem oder mehreren benutzerdefinierten XML-`Item`-Elementen angegeben, die in einem `ItemGroup`-Element enthalten sind.  
  
 Eine Projektdatei kann auch angeben benutzerdefinierte *Eigenschaften* und *Elementdefinitionsgruppe**Elemente*. Eigenschaften und Elemente bilden Name-Wert-Paare, die als Variablen im Build verwendet werden können. Die Namenskomponente eines Paars definiert ein *Makro*, und die Wertkomponente deklariert den *Makrowert*. Ein Eigenschaftenmakro wird mit $ zugegriffen (*Namen*) Notation und ein Elementmakro erfolgt über %(*Namen*) Notation.  
  
 Andere XML-Elemente in einer Projektdatei können Makros testen und anschließend den Wert eines Makros bedingt festlegen oder die Ausführung des Builds steuern. Makronamen und Literalzeichenfolgen können verkettet werden, um Konstrukte, wie z. B. einen Pfad oder einen Dateinamen, zu generieren. In der Befehlszeile die **Befehlszeilenschalter/Property** -Option fest oder überschreibt eine Projekteigenschaft. Auf Elemente kann in der Befehlszeile nicht verwiesen werden.  
  
 Das MSBuild-System kann vor bzw. nach einem anderen Ziel ein Ziel bedingt ausführen. Das System kann außerdem ein Ziel aufgrund dessen erstellen, ob die Dateien, die das Ziel nutzt, neuer als die vom Ziel ausgegebenen Dateien sind.  
  
## <a name="msbuild-in-the-ide"></a>MSBuild in der IDE  
 Wenn Sie Projekteigenschaften in der IDE festlegen und dann das Projekt speichern, schreibt Visual C++ die Projekteinstellungen in die Projektdatei. Die Projektdatei enthält Einstellungen, die sich eindeutig auf das Projekt beziehen. Sie enthält aber nicht alle Einstellungen, die zur Erstellung des Projekts erforderlich sind. Die Projektdatei enthält `Import` Elemente, die einen Netzwerk zusätzlicher enthalten *Dateien unterstützen.* Die Supportdateien enthalten die übrigen Eigenschaften, Ziele und Einstellungen, die erforderlich sind, um das Projekt zu erstellen.  
  
 Die meisten Ziele und Eigenschaften in den Unterstützungsdateien dienen ausschließlich der Implementierung des Buildsystems. Im folgenden Abschnitt werden einige nützliche Ziele und Eigenschaften erläutert, die Sie in der MSBuild-Befehlszeile angeben können. Durchsuchen Sie die Dateien in den Unterstützungsdateiverzeichnissen, um mehr Ziele und Eigenschaften zu ermitteln.  
  
### <a name="support-file-directories"></a>Supportdateiverzeichnisse  
 Standardmäßig befinden sich die primären Visual C++-Supportdateien in den folgenden Verzeichnissen.  
  
|Verzeichnis|Beschreibung|  
|---------------|-----------------|  
|*Laufwerk*: \Program Files\MSBuild\Microsoft.Cpp\v4.0\\*Version*\|Enthält die primären Zieldateien (TARGETS-Format) und Eigenschaftendateien (PROPS-Format), die von den Zielen verwendet werden. Standardmäßig verweist das $ (VCTargetsPath)-Makro auf dieses Verzeichnis.|  
|*Laufwerk*: \Program Files\MSBuild\Microsoft.Cpp\v4.0\\*Version*\Platforms\\*Plattform*\|Enthält plattformspezifische Ziel- und Eigenschaftsdateien, die die Ziele und Eigenschaften im übergeordneten Verzeichnis außer Kraft setzen. Dieses Verzeichnis enthält auch eine DLL-Datei, die die von den Zielen in diesem Verzeichnis verwendeten Aufgaben definiert.<br /><br /> Die *Plattform* Platzhalter steht für die `ARM`, `Win32`, oder `x64` Unterverzeichnis.|  
|*Laufwerk*: \Program Files\MSBuild\Microsoft.Cpp\v4.0\\*Version*\Platforms\\*Plattform*\PlatformToolsets\\*Toolset*\|Enthält die Verzeichnisse, mit denen den Build Visual C++-Anwendung mit dem angegebenen generieren *Version* des Toolsets.<br /><br /> Die *Plattform* Platzhalter steht für die `ARM`, `Win32`, oder `x64` Unterverzeichnis. Die *Toolset* Platzhalter stellt das Toolsetunterverzeichnis für Windows, Windows XP oder Windows Phone-apps erstellen.|  
|*Laufwerk*: \Program Files\MSBuild\Microsoft.Cpp\v4.0\Platforms\\*Plattform*\PlatformToolsets\\*Toolset*\|Enthält die Verzeichnisse, mit denen der Build Visual C++ 9.0 oder 10.0-Anwendungen generieren kann.<br /><br /> Die *Plattform* Platzhalter steht für die `Itanium`, `Win32`, oder `x64` Unterverzeichnis. Die *Toolset* Platzhalter steht für die `v90` oder `v100` Toolset-Unterverzeichnisse.|  
  
### <a name="support-files"></a>Supportdateien  
 Die Supportdateiverzeichnisse enthalten Dateien mit den folgenden Erweiterungen.  
  
|Erweiterung|Beschreibung|  
|---------------|-----------------|  
|TARGETS|Enthält `Target`-XML-Elemente, die die vom Ziel ausgeführten Aufgaben angeben. Enthält auch `Property Group`-, `Item Group`- und `Item Definition Group`-Elemente sowie benutzerdefinierte `Item`-Elemente, die zum Zuweisen von Dateien und Befehlszeilenoptionen zu Aufgabenparametern verwendet werden.<br /><br /> Weitere Informationen finden Sie unter [Target-Element (MSBuild)](../Topic/Target%20Element%20\(MSBuild\).md).|  
|PROPS|Enthält `Property Group`-XML-Elemente und benutzerdefinierte `Property`-XML-Elemente, die während eines Builds verwendete Datei- und Parametereinstellungen angeben.<br /><br /> Enthält auch `Item Definition Group`-XML-Elemente und benutzerdefinierte `Item`-XML-Elemente, die zusätzliche Einstellungen angeben. In einer Elementdefinitionsgruppe definierte Elemente ähneln Eigenschaften, allerdings kann in der Befehlszeile nicht auf sie zugegriffen werden. Visual C++-Projektdateien verwenden häufig Elemente statt Eigenschaften, um Einstellungen darzustellen.<br /><br /> Weitere Informationen finden Sie unter [ItemGroup-Element (MSBuild)](../Topic/ItemGroup%20Element%20\(MSBuild\).md), [ItemDefinitionGroup-Element (MSBuild)](../Topic/ItemDefinitionGroup%20Element%20\(MSBuild\).md), und [Item-Element (MSBuild)](../Topic/Item%20Element%20\(MSBuild\).md).|  
|.xml|Enthält XML-Elemente, die IDE-Benutzeroberflächenelemente, z. B. Eigenschaftenblätter, Eigenschaftenseiten oder Textfeld- bzw. Listenfeldsteuerelemente, deklarieren und initialisieren.<br /><br /> Die XML-Dateien unterstützen direkt die IDE, nicht MSBuild. Die Werte von IDE-Eigenschaften werden jedoch zur Erstellung von Eigenschaften und Elementen verwendet.<br /><br /> Die meisten XML-Dateien befinden sich in einem gebietsschemaspezifischen Unterverzeichnis. Z. B. $(VCTargetsPath) \1033 Dateien für den Englisch-amerikanischen Bereich sind\\.|  
  
## <a name="user-targets-and-properties"></a>Benutzerziele und -eigenschaften  
 Es ist hilfreich zu wissen, welche Eigenschaften und Ziele nützlich und relevant sind, um MSBuild in der Befehlszeile am effektivsten verwenden zu können. Die meisten Eigenschaften und Ziele dienen der Implementierung des Visual C++-Buildsystems und sind daher für den Benutzer nicht relevant. In diesem Abschnitt werden einige lohnende benutzerorientierte Eigenschaften und Ziele beschrieben.  
  
### <a name="platformtoolset-property"></a>PlatformToolset-Eigenschaft  
 Die `PlatformToolset`-Eigenschaft bestimmt, welches Visual C++-Toolset im Build verwendet wird. Der Wert der Eigenschaft wird mit Literalzeichenfolgen verkettet, um den Pfad eines Verzeichnisses zu bilden, das die für die Erstellung eines Projekts für eine bestimmte Plattform erforderlichen Eigenschafts- und Zieldateien enthält.  
  
 Legen Sie die `PlatformToolset` Eigenschaft `v110` verwenden [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] Tools und Bibliotheken zum Erstellen der Anwendung.  
  
 `msbuild myProject.vcxproj /p:PlatformToolset=v110`  
  
 Legen Sie die `PlatformToolset` Eigenschaft `v100` verwenden [!INCLUDE[cpp_dev10_long](../build/includes/cpp_dev10_long_md.md)] Tools und Bibliotheken zum Erstellen der Anwendung.  
  
 `msbuild myProject.vcxproj /p:PlatformToolset=v100`  
  
 Legen Sie die `PlatformToolset` Eigenschaft `v90` Visual C++ 2008-Tools und Bibliotheken verwenden, um die Anwendung zu erstellen. Das Visual C++ 2008-Toolset muss bereits auf dem Computer installiert sein, damit diese Eigenschaft wirksam ist.  
  
 `msbuild myProject.vcxproj /p:PlatformToolset=v90`  
  
### <a name="preferredtoolarchitecture-property"></a>PreferredToolArchitecture-Eigenschaft  
 Die `PreferredToolArchitecture`-Eigenschaft bestimmt, ob der 32-Bit- oder 64-Bit-Compiler sowie die entsprechenden Tools im Build verwendet werden. Diese Eigenschaft beeinflusst nicht die Ausgabeplattformarchitektur oder Konfiguration. Standardmäßig verwendet die X86 MSBuild-Version des Compilers und der Tools, wenn diese Eigenschaft nicht festgelegt ist, oder legen Sie auf einen beliebigen Wert außer `x64`.  
  
 Legen Sie die `PreferredToolArchitecture` -Eigenschaft auf `x64` auf dem 64-Bit-Compiler und Tools verwenden, um Ihre Anwendung zu erstellen.  
  
 `msbuild myProject.vcxproj /p:PreferredToolArchitecture=x64`  
  
### <a name="useenv-property"></a>UseEnv-Eigenschaft  
 Standardmäßig setzen die plattformspezifischen Einstellungen für das aktuelle Projekt die PATH-, INCLUDE-, LIB-, LIBPATH-, CONFIGURATION- und PLATFORM-Umgebungsvariablen außer Kraft. Legen Sie die `UseEnv`-Eigenschaft auf `true` fest, um zu gewährleisten, dass die Umgebungsvariablen nicht überschrieben werden.  
  
 `msbuild myProject.vcxproj /p:UseEnv=true`  
  
### <a name="targets"></a>Ziele  
 In den Visual C++-Supportdateien sind Hunderte von Zielen enthalten. Die meisten sind jedoch systemorientierte Ziele, die der Benutzer ignorieren kann. Den meisten Systemzielen wird ein Unterstrich (_) vorangestellt oder sie verfügen über einen Namen, der mit "PrepareFor", "Compute", "Before", "After", "Pre" oder "Post" beginnt.  
  
 In der folgenden Tabelle sind mehrere lohnende benutzerorientierte Ziele aufgeführt.  
  
|Ziel|Beschreibung|  
|------------|-----------------|  
|BscMake|Führt das Microsoft-Wartungshilfsprogramm zum Durchsuchen von Informationen aus ("bscmake.exe").|  
|Build|Erstellt das Projekt.<br /><br /> Dies ist das Standardziel für ein Projekt.|  
|ClCompile|Führt das Visual C++-Compilertool ("cl.exe") aus.|  
|Bereinigen|Löscht temporäre und zwischengespeicherte Builddateien.|  
|Lib|Führt das 32-Bit-Tool von Microsoft zur Bibliotheksverwaltung ("lib.exe") aus.|  
|Link|Führt das Visual C++-Linkertool ("link.exe") aus.|  
|ManifestResourceCompile|Extrahiert eine Liste der Ressourcen aus einem Manifest und führt das Microsoft Windows-Ressourcencompilertool ("rc.exe") aus.|  
|Midl|Führt das MIDL (Microsoft Interface Definition Language)-Compilertool ("midl.exe") aus.|  
|Neu erstellen|Bereinigt und erstellt das Projekt.|  
|ResourceCompile|Führt das Microsoft Windows-Ressourcencompilertool ("rc.exe") aus.|  
|XdcMake|Führt das XML-Dokumentationstool ("xdcmake.exe") aus.|  
|Xsd|Führt das XML-Schemadefinitionstool ("Xsd.exe") aus.|  
  
## <a name="see-also"></a>Siehe auch  
 [MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)