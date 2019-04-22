---
title: Merkmale von MSBuild für C++-Projekte in Visual Studio
ms.date: 12/08/2018
helpviewer_keywords:
- MSBuild overview
ms.assetid: dd258f6f-ab51-48d9-b274-f7ba911d05ca
ms.openlocfilehash: 6c8e891f6bf6ed6b3bb3d1c84dbc13b64ab7b868
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59021903"
---
# <a name="msbuild-internals-for-c-projects"></a>Merkmale von MSBuild für C++-Projekte

Wenn Sie Projekteigenschaften, in der IDE festlegen, und speichern Sie das Projekt, schreibt Visual Studio die projekteinstellungen in Ihrer Projektdatei hinzu. Die Projektdatei enthält Einstellungen, die sich eindeutig auf das Projekt beziehen. Sie enthält aber nicht alle Einstellungen, die zur Erstellung des Projekts erforderlich sind. Die Projektdatei enthält `Import` Elemente, die einen Netzwerk zusätzlicher enthalten *Unterstützungsdateien.* Die Supportdateien enthalten die übrigen Eigenschaften, Ziele und Einstellungen, die erforderlich sind, um das Projekt zu erstellen.

Die meisten Ziele und Eigenschaften in den Unterstützungsdateien dienen ausschließlich der Implementierung des Buildsystems. Im folgenden Abschnitt werden einige nützliche Ziele und Eigenschaften erläutert, die Sie in der MSBuild-Befehlszeile angeben können. Durchsuchen Sie die Dateien in den Unterstützungsdateiverzeichnissen, um mehr Ziele und Eigenschaften zu ermitteln.

## <a name="support-file-directories"></a>Supportdateiverzeichnisse

Standardmäßig befinden sich die primären Visual Studio-Unterstützungsdateien in den folgenden Verzeichnissen. Die Verzeichnisse unter Microsoft Visual Studio werden von Visual Studio 2017 und höheren Versionen werden verwendet, während die Verzeichnisse unter MSBuild von Visual Studio 2015 und früheren Versionen verwendet werden.

|Verzeichnis|Beschreibung|
|---------------|-----------------|
|*Laufwerk*: \Program Files *(x86)* \Microsoft Visual Studio\\*Jahr*\\*Edition*\Common7\IDE\VC\VCTargets\ <br /><br />*Laufwerk*: \Program Files *(x86)* \MSBuild\Microsoft.Cpp (x86) \v4.0\\*Version*\ |Enthält die primären Zieldateien (TARGETS-Format) und Eigenschaftendateien (PROPS-Format), die von den Zielen verwendet werden. Standardmäßig verweist das $ (VCTargetsPath)-Makro auf dieses Verzeichnis.|
|*Laufwerk*: \Program Files *(x86)* \Microsoft Visual Studio\\*Jahr*\\*Edition*\Common7\IDE\VC\VCTargets\ Plattformen\\*Plattform*\ <br /><br />*drive*:\Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\\*version*\Platforms\\*platform*\ |Enthält plattformspezifische Ziel- und Eigenschaftsdateien, die die Ziele und Eigenschaften im übergeordneten Verzeichnis außer Kraft setzen. Dieses Verzeichnis enthält auch eine DLL, die Aufgaben definiert, die von den Zielen in diesem Verzeichnis verwendet werden.<br /><br /> Die *Plattform* steht für die ARM, Win32 oder X64 Unterverzeichnis.|
|*Laufwerk*: \Program Files *(x86)* \Microsoft Visual Studio\\*Jahr*\\*Edition*\Common7\IDE\VC\VCTargets\ Plattformen\\*Plattform*\PlatformToolsets\\*Toolset*\ <br /><br />*drive*:\Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\\*version*\Platforms\\*platform*\PlatformToolsets\\*toolset*\ <br /><br />*Laufwerk*: \Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\Platforms\\*Plattform*\PlatformToolsets\\*Toolset*\ |Enthält die Verzeichnisse, mit denen das Build, um C++-Anwendungen zu generieren, mit dem angegebenen *Toolset*.<br /><br /> Die *Jahr* und *Edition* Platzhalter von Visual Studio 2017 und höhere Editionen verwendet werden. Die *Version* Platzhalter ist V110 für Visual Studio 2012, V120 für Visual Studio 2013 oder V140 für Visual Studio 2015. Die *Plattform* steht für die ARM, Win32 oder X64 Unterverzeichnis. Die *Toolset* Platzhalter stellt das Toolsetunterverzeichnis, z. B. v140 zum Erstellen von Windows-apps mit dem Visual Studio 2015-Toolset, v120_xp für Windows XP mit dem Toolset von Visual Studio 2013 oder v110_wp80 zu erstellen. Erstellen von Windows Phone 8.0-apps mit dem Toolset von Visual Studio 2012.<br /><br />Der Pfad, der die Verzeichnisse enthält, mit denen den Build entweder Visual Studio 2008 oder Visual Studio 2010-Anwendungen generieren nicht umfassen die *Version*, und die *Plattform* Platzhalter Stellt den Itanium, Win32 oder X64 Unterverzeichnis. Die *Toolset* -Platzhalter stellt das Toolsetunterverzeichnis v90 oder v100 dar.|

## <a name="support-files"></a>Supportdateien

Die Supportdateiverzeichnisse enthalten Dateien mit diesen Erweiterungen:

|Erweiterung|Beschreibung|
|---------------|-----------------|
|TARGETS|Enthält `Target`-XML-Elemente, die die vom Ziel ausgeführten Aufgaben angeben. Enthält auch `PropertyGroup`-, `ItemGroup`- und `ItemDefinitionGroup`-Elemente sowie benutzerdefinierte `Item`-Elemente, die zum Zuweisen von Dateien und Befehlszeilenoptionen zu Aufgabenparametern verwendet werden.<br /><br /> Weitere Informationen finden Sie unter [Target-Element (MSBuild)](/visualstudio/msbuild/target-element-msbuild).|
|PROPS|Enthält `Property Group`-XML-Elemente und benutzerdefinierte `Property`-XML-Elemente, die während eines Builds verwendete Datei- und Parametereinstellungen angeben.<br /><br /> Enthält auch `ItemDefinitionGroup`-XML-Elemente und benutzerdefinierte `Item`-XML-Elemente, die zusätzliche Einstellungen angeben. In einer Elementdefinitionsgruppe definierte Elemente ähneln Eigenschaften, allerdings kann in der Befehlszeile nicht auf sie zugegriffen werden. Visual Studio-Projektdateien verwenden häufig Elemente statt Eigenschaften um Einstellungen darzustellen.<br /><br /> Weitere Informationen finden Sie unter [ItemGroup-Element (MSBuild)](/visualstudio/msbuild/itemgroup-element-msbuild), 
[ItemDefinitionGroup-Element (MSBuild)](/visualstudio/msbuild/itemdefinitiongroup-element-msbuild), und [Item-Element (MSBuild)](/visualstudio/msbuild/item-element-msbuild).|
|.xml|Enthält XML-Elemente, die IDE-Benutzeroberflächenelemente, z. B. Eigenschaftenblätter, Eigenschaftenseiten oder Textfeld- bzw. Listenfeldsteuerelemente, deklarieren und initialisieren.<br /><br /> Die XML-Dateien unterstützen direkt die IDE, nicht MSBuild. Die Werte von IDE-Eigenschaften werden jedoch zur Erstellung von Eigenschaften und Elementen verwendet.<br /><br /> Die meisten XML-Dateien befinden sich in einem gebietsschemaspezifischen Unterverzeichnis. Beispielsweise sind die Dateien für die US-Englisch-Region in der $(%%VCTargetsPath%%) \1033\\.|

## <a name="user-targets-and-properties"></a>Benutzerziele und-Eigenschaften

Es ist hilfreich zu wissen, welche Eigenschaften und Ziele nützlich und relevant sind, um MSBuild in der Befehlszeile am effektivsten verwenden zu können. Die meisten Eigenschaften und Ziele unterstützen, implementieren Sie das Visual Studio-Buildsystem und sind daher nicht für den Benutzer relevant. In diesem Abschnitt werden einige lohnende benutzerorientierte Eigenschaften und Ziele beschrieben.

### <a name="platformtoolset-property"></a>PlatformToolset-Eigenschaft

Die `PlatformToolset` Eigenschaft bestimmt, welche MSVC-Toolset im Build verwendet wird. Standardmäßig wird das aktuelle Toolset verwendet. Wenn diese Eigenschaft festgelegt ist, verkettet der Wert der Eigenschaft wird mit Literalzeichenfolgen, um den Pfad eines Verzeichnisses zu bilden, das die, die zum Erstellen eines Projekts für eine bestimmte Plattform erforderlichen Eigenschafts- und Zieldateien enthält. Das Plattformtoolset muss installiert sein, um mithilfe dieser Plattform-Toolsetversion zu erstellen.

Legen Sie z. B. die `PlatformToolset` Eigenschaft `v140` zu Visual Studio 2015-Tools und Bibliotheken zu verwenden, um Ihre Anwendung zu erstellen:

`msbuild myProject.vcxproj /p:PlatformToolset=v140`

### <a name="preferredtoolarchitecture-property"></a>PreferredToolArchitecture-Eigenschaft

Die `PreferredToolArchitecture`-Eigenschaft bestimmt, ob der 32-Bit- oder 64-Bit-Compiler sowie die entsprechenden Tools im Build verwendet werden. Diese Eigenschaft beeinflusst nicht die Ausgabeplattformarchitektur oder Konfiguration. Standardmäßig verwendet MSBuild die X86 Version des Compilers und der Tools, wenn diese Eigenschaft nicht festgelegt ist.

Legen Sie z. B. die `PreferredToolArchitecture` Eigenschaft `x64` auf dem 64-Bit-Compiler und Tools zu verwenden, um Ihre Anwendung zu erstellen:

`msbuild myProject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="useenv-property"></a>UseEnv-Eigenschaft

Standardmäßig setzen die plattformspezifischen Einstellungen für das aktuelle Projekt die PATH-, INCLUDE-, LIB-, LIBPATH-, CONFIGURATION- und PLATFORM-Umgebungsvariablen außer Kraft. Legen Sie die `UseEnv` Eigenschaft **"true"** um sicherzustellen, dass die Umgebungsvariablen nicht überschrieben werden.

`msbuild myProject.vcxproj /p:UseEnv=true`

### <a name="targets"></a>Ziele

Es gibt Hunderte von Zielen in den Visual Studio-Unterstützungsdateien. Die meisten sind jedoch systemorientierte Ziele, die der Benutzer ignorieren kann. Den meisten Systemzielen wird ein Unterstrich (_) vorangestellt oder sie verfügen über einen Namen, der mit "PrepareFor", "Compute", "Before", "After", "Pre" oder "Post" beginnt.

Die folgende Tabelle enthält einige nützliche benutzerorientierte Ziele.

|Target|Beschreibung|
|------------|-----------------|
|BscMake|Führt das Microsoft-Wartungshilfsprogramm zum Durchsuchen von Informationen aus ("bscmake.exe").|
|Build|Erstellt das Projekt.<br /><br /> Dies ist das Standardziel für ein Projekt.|
|ClCompile|Führt das MSVC-Compilertool cl.exe.|
|Bereinigen|Löscht temporäre und zwischengespeicherte Builddateien.|
|Lib|Führt das 32-Bit-Tool von Microsoft zur Bibliotheksverwaltung ("lib.exe") aus.|
|Link|Führt das MSVC-Linkertool link.exe.|
|ManifestResourceCompile|Extrahiert eine Liste der Ressourcen aus einem Manifest und führt das Microsoft Windows-Ressourcencompilertool ("rc.exe") aus.|
|Midl|Führt das MIDL (Microsoft Interface Definition Language)-Compilertool ("midl.exe") aus.|
|Neu erstellen|Bereinigt und erstellt das Projekt.|
|ResourceCompile|Führt das Microsoft Windows-Ressourcencompilertool ("rc.exe") aus.|
|XdcMake|Führt das XML-Dokumentationstool ("xdcmake.exe") aus.|
|Xsd|Führt das XML-Schemadefinitionstool ("Xsd.exe") aus. *Siehe den Hinweis unten.*|

> [!NOTE]
> In Visual Studio 2017, C++-Projekt Unterstützung für **Xsd** Dateien ist veraltet. Sie können weiterhin verwenden **Microsoft.VisualC.CppCodeProvider** durch Hinzufügen von **CppCodeProvider.dll** manuell in den GAC.

## <a name="see-also"></a>Siehe auch

[Referenz zu MSBuild-Aufgaben](/visualstudio/msbuild/msbuild-task-reference)<br/>
[BscMake-Aufgabe](/visualstudio/msbuild/bscmake-task)<br/>
[CL-Aufgabe](/visualstudio/msbuild/cl-task)<br/>
[CPPClean-Aufgabe](/visualstudio/msbuild/cppclean-task)<br/>
[LIB-Aufgabe](/visualstudio/msbuild/lib-task)<br/>
[Link-Aufgabe](/visualstudio/msbuild/link-task)<br/>
[MIDL-Aufgabe](/visualstudio/msbuild/midl-task)<br/>
[MT-Aufgabe](/visualstudio/msbuild/mt-task)<br/>
[RC-Aufgabe](/visualstudio/msbuild/rc-task)<br/>
[SetEnv Task](/visualstudio/msbuild/setenv-task)<br/>
[VCMessage-Aufgabe](/visualstudio/msbuild/vcmessage-task)<br/>
[XDCMake-Aufgabe](/visualstudio/msbuild/xdcmake-task)<br/>
