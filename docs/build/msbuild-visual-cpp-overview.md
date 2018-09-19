---
title: Übersicht über MSBuild (Visual C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MSBuild overview
ms.assetid: dd258f6f-ab51-48d9-b274-f7ba911d05ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad6feef707d991d07fa4e086bc8535f32b991825
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716857"
---
# <a name="msbuild-visual-c-overview"></a>Übersicht über MSBuild (Visual C++)

MSBuild ist das Standardbuildsystem für Visual C++-Projekte. Wenn Sie ein Projekt in der integrierten Entwicklungsumgebung von Visual Studio (IDE) erstellen, werden das Tool "msbuild.exe", eine XML-basierte Projektdatei und optionale Einstellungsdateien verwendet. Obwohl Sie "msbuild.exe" und eine Projektdatei in der Befehlszeile verwenden können, stellt die IDE eine Benutzeroberfläche zur leichteren Konfiguration von Einstellungen und Erstellung von Projekten bereit. In dieser Übersicht wird beschrieben, wie Visual C++ das MSBuild-System verwendet.

## <a name="prerequisites"></a>Erforderliche Komponenten

Lesen Sie die folgenden Dokumente zu MSBuild.

- [MSBuild](/visualstudio/msbuild/msbuild) Übersicht der MSBuild-Konzepte.

- [MSBuild-Referenz](/visualstudio/msbuild/msbuild-reference) Referenzinformationen zum MSBuild-System.

- [Projekt-Verweis auf Konfigurationsdateischema](/visualstudio/msbuild/msbuild-project-file-schema-reference) werden die MSBuild-XML-Schema-Elemente, sowie ihre Attribute sowie die übergeordneten und untergeordneten Elementen aufgelistet. Beachten Sie insbesondere die [ItemGroup](/visualstudio/msbuild/itemgroup-element-msbuild), [PropertyGroup](/visualstudio/msbuild/propertygroup-element-msbuild), [Ziel](/visualstudio/msbuild/target-element-msbuild), und [Aufgabe](/visualstudio/msbuild/task-element-msbuild) Elemente.

- [Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference) beschreibt die Befehlszeilenargumente und die Optionen, mit denen Sie mit msbuild.exe.

- [Task Reference](/visualstudio/msbuild/msbuild-task-reference) Beschreibt MSBuild-Aufgaben. Beachten Sie insbesondere diese Aufgaben, die Visual C++-spezifisch sind: [BscMake-Aufgabe](/visualstudio/msbuild/bscmake-task), [CL-Aufgabe](/visualstudio/msbuild/cl-task), [CPPClean-Aufgabe](/visualstudio/msbuild/cppclean-task), [LIB-Aufgabe](/visualstudio/msbuild/lib-task), [Link-Aufgabe](/visualstudio/msbuild/link-task), [MIDL-Aufgabe](/visualstudio/msbuild/midl-task), [MT-Aufgabe](/visualstudio/msbuild/mt-task), [RC-Aufgabe](/visualstudio/msbuild/rc-task), [SetEnv-Aufgabe](/visualstudio/msbuild/setenv-task), [ VCMessage-Aufgabe](/visualstudio/msbuild/vcmessage-task), [XDCMake-Aufgabe](/visualstudio/msbuild/xdcmake-task), [XSD-Aufgabe](/visualstudio/msbuild/xsd-task).

## <a name="msbuild-on-the-command-line"></a>MSBuild in der Befehlszeile

Die folgende Anweisung aus der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference) veranschaulicht, dass das Tool "msbuild.exe" ein implizites oder explizites nimmt *Project_file* Argument (eine VCXPROJ-Datei für Visual C++-Projekte) und 0 (null) oder mehr Befehlszeile *Optionen* Argumente.

> **MSBuild.exe** [ *Project_file* ] [ *Optionen* ]

Verwenden der **/target** (oder **/t /**) und **"/ Property"** (oder **/p**) außer Kraft setzen, bestimmte Eigenschaften und Ziele, die Befehlszeilenoptionen in der Projektdatei angegeben.

Eine wesentliche Funktion der Projektdatei ist an eine *Ziel*, d.h., dass eine bestimmte Operation zu Ihrem Projekt, und die Eingaben und Ausgaben, die zum Ausführen dieses Vorgangs erforderlich sind. Eine Projektdatei kann ein oder mehrere Ziele angeben, zu denen auch ein Standardziel gehören kann.

Jedes Ziel besteht aus einer Sequenz von einem oder mehreren *Aufgaben*. Jede Aufgabe wird durch eine .NET Framework-Klasse dargestellt, die einen ausführbaren Befehl enthält. Z. B. die [CL-Aufgabe](/visualstudio/msbuild/cl-task) enthält die [cl.exe](../build/reference/compiling-a-c-cpp-program.md) Befehl.

Ein *Aufgabenparameter* ist eine Eigenschaft der Klassenaufgabe und stellt in der Regel eine Befehlszeilenoption des ausführbaren Befehls dar. Z. B. die `FavorSizeOrSpeed` Parameter, der die `CL` Task entspricht der **/OS** und **/Ot** Compileroptionen.

Zusätzliche Aufgabenparameter unterstützen die MSBuild-Infrastruktur. Der `Sources`-Aufgabenparameter gibt z. B. einen Satz von Aufgaben an, die von anderen Aufgaben genutzt werden können. Weitere Informationen zu MSBuild-Aufgaben, finden Sie unter [Aufgabenreferenz](/visualstudio/msbuild/msbuild-task-reference).

Die meisten Aufgaben erfordern Eingaben und Ausgaben, z. B. Dateinamen, Pfade und Zeichenfolgenparameter bzw. numerische oder boolesche Parameter. Eine allgemeine Eingabe ist z. B. der Name einer zu kompilierenden CPP-Quelldatei. Ein wichtiger Eingabeparameter ist eine Zeichenfolge, der angibt, die Buildkonfiguration und Plattform, z. B. "Debug\|Win32". Eingaben und Ausgaben werden von einem oder mehreren benutzerdefinierten XML-`Item`-Elementen angegeben, die in einem `ItemGroup`-Element enthalten sind.

Eine Projektdatei kann auch angeben, eine benutzerdefinierte *Eigenschaften* und `ItemDefinitionGroup` *Elemente*. Eigenschaften und Elemente bilden Name-Wert-Paare, die als Variablen im Build verwendet werden können. Die Namenskomponente eines Paars definiert ein *Makro*, und die Wertkomponente deklariert den *Makrowert*. Ein erfolgt mithilfe von $(*Namen*)-Notation ein, und ein Elementmakro erfolgt mithilfe der %(*Namen*) Notation.

Andere XML-Elemente in einer Projektdatei können Makros testen und anschließend den Wert eines Makros bedingt festlegen oder die Ausführung des Builds steuern. Makronamen und Literalzeichenfolgen können verkettet werden, um Konstrukte, wie z. B. einen Pfad oder einen Dateinamen, zu generieren. In der Befehlszeile die **"/ Property"** Option legt fest oder überschreibt eine Projekteigenschaft. Auf Elemente kann in der Befehlszeile nicht verwiesen werden.

Das MSBuild-System kann vor bzw. nach einem anderen Ziel ein Ziel bedingt ausführen. Das System kann außerdem ein Ziel aufgrund dessen erstellen, ob die Dateien, die das Ziel nutzt, neuer als die vom Ziel ausgegebenen Dateien sind.

## <a name="msbuild-in-the-ide"></a>MSBuild in der IDE

Wenn Sie Projekteigenschaften in der IDE festlegen und dann das Projekt speichern, schreibt Visual C++ die Projekteinstellungen in die Projektdatei. Die Projektdatei enthält Einstellungen, die sich eindeutig auf das Projekt beziehen. Sie enthält aber nicht alle Einstellungen, die zur Erstellung des Projekts erforderlich sind. Die Projektdatei enthält `Import` Elemente, die einen Netzwerk zusätzlicher enthalten *Unterstützungsdateien.* Die Supportdateien enthalten die übrigen Eigenschaften, Ziele und Einstellungen, die erforderlich sind, um das Projekt zu erstellen.

Die meisten Ziele und Eigenschaften in den Unterstützungsdateien dienen ausschließlich der Implementierung des Buildsystems. Im folgenden Abschnitt werden einige nützliche Ziele und Eigenschaften erläutert, die Sie in der MSBuild-Befehlszeile angeben können. Durchsuchen Sie die Dateien in den Unterstützungsdateiverzeichnissen, um mehr Ziele und Eigenschaften zu ermitteln.

### <a name="support-file-directories"></a>Supportdateiverzeichnisse

Standardmäßig befinden sich die primären Visual C++-Supportdateien in den folgenden Verzeichnissen. Die Verzeichnisse unter Microsoft Visual Studio werden von Visual Studio 2017 und höheren Versionen werden verwendet, während die Verzeichnisse unter MSBuild von Visual Studio 2015 und früheren Versionen verwendet werden.

|Verzeichnis|Beschreibung|
|---------------|-----------------|
|*Laufwerk*: \Program Files *(x86)* \Microsoft Visual Studio\\*Jahr*\\*Edition*\Common7\IDE\VC\VCTargets\ <br /><br />*Laufwerk*: \Program Files *(x86)* \MSBuild\Microsoft.Cpp (x86) \v4.0\\*Version*\ |Enthält die primären Zieldateien (TARGETS-Format) und Eigenschaftendateien (PROPS-Format), die von den Zielen verwendet werden. Standardmäßig verweist das $ (VCTargetsPath)-Makro auf dieses Verzeichnis.|
|*Laufwerk*: \Program Files *(x86)* \Microsoft Visual Studio\\*Jahr*\\*Edition*\Common7\IDE\VC\VCTargets\ Plattformen\\*Plattform*\ <br /><br />*Laufwerk*: \Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\\*Version*\Platforms\\*Plattform*\ |Enthält plattformspezifische Ziel- und Eigenschaftsdateien, die die Ziele und Eigenschaften im übergeordneten Verzeichnis außer Kraft setzen. Dieses Verzeichnis enthält auch eine DLL, die Aufgaben definiert, die von den Zielen in diesem Verzeichnis verwendet werden.<br /><br /> Die *Plattform* steht für die ARM, Win32 oder X64 Unterverzeichnis.|
|*Laufwerk*: \Program Files *(x86)* \Microsoft Visual Studio\\*Jahr*\\*Edition*\Common7\IDE\VC\VCTargets\ Plattformen\\*Plattform*\PlatformToolsets\\*Toolset*\ <br /><br />*Laufwerk*: \Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\\*Version*\Platforms\\*Plattform*\ \PlatformToolsets\\*Toolset*\ <br /><br />*Laufwerk*: \Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\Platforms\\*Plattform*\PlatformToolsets\\*Toolset*\ |Enthält die Verzeichnisse, mit denen das Build Visual C++-Anwendungen zu generieren, indem Sie mit dem angegebenen *Toolset*.<br /><br /> Die *Jahr* und *Edition* Platzhalter von Visual Studio 2017 und höhere Editionen verwendet werden. Die *Version* Platzhalter ist V110 für Visual Studio 2012, V120 für Visual Studio 2013 oder V140 für Visual Studio 2015. Die *Plattform* steht für die ARM, Win32 oder X64 Unterverzeichnis. Die *Toolset* Platzhalter stellt das Toolsetunterverzeichnis, z. B. v140 zum Erstellen von Windows-apps mit dem Visual Studio 2015-Toolset, v120_xp für Windows XP mit dem Toolset von Visual Studio 2013 oder v110_wp80 zu erstellen. Erstellen von Windows Phone 8.0-apps mit dem Toolset von Visual Studio 2012.<br /><br />Der Pfad, der die Verzeichnisse enthält, mit denen den Build entweder Visual C++ 2008 oder Visual C++ 2010-Anwendungen generieren nicht umfassen die *Version*, und die *Plattform* Platzhalter darstellt. die Itanium, Win32 oder X64 Unterverzeichnis. Die *Toolset* -Platzhalter stellt das Toolsetunterverzeichnis v90 oder v100 dar.|

### <a name="support-files"></a>Supportdateien

Die Supportdateiverzeichnisse enthalten Dateien mit diesen Erweiterungen:

|Erweiterung|Beschreibung|
|---------------|-----------------|
|TARGETS|Enthält `Target`-XML-Elemente, die die vom Ziel ausgeführten Aufgaben angeben. Enthält auch `PropertyGroup`-, `ItemGroup`- und `ItemDefinitionGroup`-Elemente sowie benutzerdefinierte `Item`-Elemente, die zum Zuweisen von Dateien und Befehlszeilenoptionen zu Aufgabenparametern verwendet werden.<br /><br /> Weitere Informationen finden Sie unter [Target-Element (MSBuild)](/visualstudio/msbuild/target-element-msbuild).|
|PROPS|Enthält `Property Group`-XML-Elemente und benutzerdefinierte `Property`-XML-Elemente, die während eines Builds verwendete Datei- und Parametereinstellungen angeben.<br /><br /> Enthält auch `ItemDefinitionGroup`-XML-Elemente und benutzerdefinierte `Item`-XML-Elemente, die zusätzliche Einstellungen angeben. In einer Elementdefinitionsgruppe definierte Elemente ähneln Eigenschaften, allerdings kann in der Befehlszeile nicht auf sie zugegriffen werden. Visual C++-Projektdateien verwenden häufig Elemente statt Eigenschaften, um Einstellungen darzustellen.<br /><br /> Weitere Informationen finden Sie unter [ItemGroup-Element (MSBuild)](/visualstudio/msbuild/itemgroup-element-msbuild), [ItemDefinitionGroup-Element (MSBuild)](/visualstudio/msbuild/itemdefinitiongroup-element-msbuild), und [Item-Element (MSBuild)](/visualstudio/msbuild/item-element-msbuild).|
|.xml|Enthält XML-Elemente, die IDE-Benutzeroberflächenelemente, z. B. Eigenschaftenblätter, Eigenschaftenseiten oder Textfeld- bzw. Listenfeldsteuerelemente, deklarieren und initialisieren.<br /><br /> Die XML-Dateien unterstützen direkt die IDE, nicht MSBuild. Die Werte von IDE-Eigenschaften werden jedoch zur Erstellung von Eigenschaften und Elementen verwendet.<br /><br /> Die meisten XML-Dateien befinden sich in einem gebietsschemaspezifischen Unterverzeichnis. Beispielsweise sind die Dateien für die US-Englisch-Region in der $(%%VCTargetsPath%%) \1033\\.|

## <a name="user-targets-and-properties"></a>Benutzerziele und -eigenschaften

Es ist hilfreich zu wissen, welche Eigenschaften und Ziele nützlich und relevant sind, um MSBuild in der Befehlszeile am effektivsten verwenden zu können. Die meisten Eigenschaften und Ziele dienen der Implementierung des Visual C++-Buildsystems und sind daher für den Benutzer nicht relevant. In diesem Abschnitt werden einige lohnende benutzerorientierte Eigenschaften und Ziele beschrieben.

### <a name="platformtoolset-property"></a>PlatformToolset-Eigenschaft

Die `PlatformToolset`-Eigenschaft bestimmt, welches Visual C++-Toolset im Build verwendet wird. Standardmäßig wird das aktuelle Toolset verwendet. Wenn diese Eigenschaft festgelegt ist, verkettet der Wert der Eigenschaft wird mit Literalzeichenfolgen, um den Pfad eines Verzeichnisses zu bilden, das die, die zum Erstellen eines Projekts für eine bestimmte Plattform erforderlichen Eigenschafts- und Zieldateien enthält. Das Plattformtoolset muss installiert sein, um mithilfe dieser Plattform-Toolsetversion zu erstellen.

Legen Sie z. B. die `PlatformToolset` Eigenschaft `v140` Visual C++ 2015 Tools und Bibliotheken zu verwenden, um Ihre Anwendung zu erstellen:

`msbuild myProject.vcxproj /p:PlatformToolset=v140`

### <a name="preferredtoolarchitecture-property"></a>PreferredToolArchitecture-Eigenschaft

Die `PreferredToolArchitecture`-Eigenschaft bestimmt, ob der 32-Bit- oder 64-Bit-Compiler sowie die entsprechenden Tools im Build verwendet werden. Diese Eigenschaft beeinflusst nicht die Ausgabeplattformarchitektur oder Konfiguration. Standardmäßig verwendet MSBuild die X86 Version des Compilers und der Tools, wenn diese Eigenschaft nicht festgelegt ist.

Legen Sie z. B. die `PreferredToolArchitecture` Eigenschaft `x64` auf dem 64-Bit-Compiler und Tools zu verwenden, um Ihre Anwendung zu erstellen:

`msbuild myProject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="useenv-property"></a>UseEnv-Eigenschaft

Standardmäßig setzen die plattformspezifischen Einstellungen für das aktuelle Projekt die PATH-, INCLUDE-, LIB-, LIBPATH-, CONFIGURATION- und PLATFORM-Umgebungsvariablen außer Kraft. Legen Sie die `UseEnv`-Eigenschaft auf `true` fest, um zu gewährleisten, dass die Umgebungsvariablen nicht überschrieben werden.

`msbuild myProject.vcxproj /p:UseEnv=true`

### <a name="targets"></a>Ziele

In den Visual C++-Supportdateien sind Hunderte von Zielen enthalten. Die meisten sind jedoch systemorientierte Ziele, die der Benutzer ignorieren kann. Den meisten Systemzielen wird ein Unterstrich (_) vorangestellt oder sie verfügen über einen Namen, der mit "PrepareFor", "Compute", "Before", "After", "Pre" oder "Post" beginnt.

Die folgende Tabelle enthält einige nützliche benutzerorientierte Ziele.

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
|Xsd|Führt das XML-Schemadefinitionstool ("Xsd.exe") aus. *Siehe den Hinweis unten.*|

> [!NOTE]
> In Visual Studio 2017, C++-Projekt Unterstützung für **Xsd** Dateien ist veraltet. Sie können weiterhin verwenden **Microsoft.VisualC.CppCodeProvider** durch Hinzufügen von **CppCodeProvider.dll** manuell in den GAC.

## <a name="see-also"></a>Siehe auch

[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)
