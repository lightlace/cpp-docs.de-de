---
title: MSBuild-Interna für C++-Projekte in Visual Studio
ms.date: 05/16/2019
helpviewer_keywords:
- MSBuild overview
ms.assetid: dd258f6f-ab51-48d9-b274-f7ba911d05ca
ms.openlocfilehash: b3348320a1468fea03f39e43cc847f1085f3d319
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837229"
---
# <a name="msbuild-internals-for-c-projects"></a>MSBuild-Interna für C++-Projekte

Wenn Sie Projekteigenschaften in der IDE festlegen und dann das Projekt speichern, schreibt Visual Studio die Projekteinstellungen in die Projektdatei. Die Projektdatei enthält Einstellungen, die sich eindeutig auf das Projekt beziehen. Sie enthält aber nicht alle Einstellungen, die zur Erstellung des Projekts erforderlich sind. Die Projektdatei enthält `Import`-Elemente, die ein Netzwerk zusätzlicher *Supportdateien* beinhalten. Die Supportdateien enthalten die übrigen Eigenschaften, Ziele und Einstellungen, die erforderlich sind, um das Projekt zu erstellen.

Die meisten Ziele und Eigenschaften in den Unterstützungsdateien dienen ausschließlich der Implementierung des Buildsystems. Im folgenden Abschnitt werden einige nützliche Ziele und Eigenschaften erläutert, die Sie in der MSBuild-Befehlszeile angeben können. Durchsuchen Sie die Dateien in den Unterstützungsdateiverzeichnissen, um mehr Ziele und Eigenschaften zu ermitteln.

## <a name="support-file-directories"></a>Supportdateiverzeichnisse

Standardmäßig befinden sich die primären Visual Studio-Supportdateien in den folgenden Verzeichnissen. Die Verzeichnisse unter Microsoft Visual Studio werden von Visual Studio 2017 und höheren Versionen verwendet, während die Verzeichnisse unter MSBuild von Visual Studio 2015 und früheren Versionen verwendet werden.

|Verzeichnis|Beschreibung|
|---------------|-----------------|
|*Laufwerk*:\Programme *(x86)* \Microsoft Visual Studio\\*Jahr*\\*Edition*\Common7\IDE\VC\VCTargets\ <br /><br />*Laufwerk*:\Programme *(x86)* \MSBuild\Microsoft.Cpp (x86)\v4.0\\*Version*\ |Enthält die primären Zieldateien (TARGETS-Format) und Eigenschaftendateien (PROPS-Format), die von den Zielen verwendet werden. Standardmäßig verweist das $ (VCTargetsPath)-Makro auf dieses Verzeichnis.|
|*Laufwerk*:\Programme *(x86)* \Microsoft Visual Studio\\*Jahr*\\*Edition*\Common7\IDE\VC\VCTargets\Platforms\\*Plattform*\ <br /><br />*Laufwerk*:\Programme *(x86)* \MSBuild\Microsoft.Cpp\v4.0\\*Version*\Platforms\\*Plattform*\ |Enthält plattformspezifische Ziel- und Eigenschaftsdateien, die die Ziele und Eigenschaften im übergeordneten Verzeichnis außer Kraft setzen. Dieses Verzeichnis enthält außerdem eine DLL, die die von den Zielen in diesem Verzeichnis verwendeten Aufgaben definiert.<br /><br /> Der Platzhalter *Plattform* steht für das ARM-, Win32- oder x64-Unterverzeichnis.|
|*Laufwerk*:\Programme *(x86)* \Microsoft Visual Studio\\*Jahr*\\*Edition*\Common7\IDE\VC\VCTargets\Platforms\\*Plattform*\PlatformToolsets\\*Toolset*\ <br /><br />*Laufwerk*:\Programme *(x86)* \MSBuild\Microsoft.Cpp\v4.0\\*Version*\Platforms\\*Plattform*\PlatformToolsets\\*Toolset*\ <br /><br />*Laufwerk*:\Programme *(x86)* \MSBuild\Microsoft.Cpp\v4.0\Platforms\\*Plattform*\PlatformToolsets\\*Toolset*\ |Enthält die Verzeichnisse, die es dem Build ermöglichen, C++-Anwendungen mit dem angegebenen *Toolset* zu generieren.<br /><br /> Die Platzhalter *Jahr* und *Edition* werden von Visual Studio 2017 und späteren Editionen verwendet. Der Platzhalter *Version* ist V110 für Visual Studio 2012, V120 für Visual Studio 2013, V140 für Visual Studio 2015, v141 für Visual Studio 2017 und v142 für Visual Studio 2019. Der Platzhalter *Plattform* steht für das ARM-, Win32- oder x64-Unterverzeichnis. Der Platzhalter *Toolset* stellt das Toolsetunterverzeichnis dar, beispielsweise v140 zum Erstellen von Windows-Apps mithilfe des Visual Studio 2015-Toolsets, v120_xp zum Erstellen von Builds für Windows XP mit dem Visual Studio 2013-Toolset.<br /><br />Der Pfad, der die Verzeichnisse enthält, die es dem Build ermöglichen, entweder Visual Studio 2008- oder Visual Studio 2010-Anwendungen zu generieren, schließt *Version* nicht ein, und der Platzhalter *Plattform* stellt das Itanium-, Win32- oder x64-Unterverzeichnis dar. Der *Toolset*-Platzhalter stellt das Toolsetunterverzeichnis v90 oder v100 dar.|

## <a name="support-files"></a>Supportdateien

Die Supportdateiverzeichnisse enthalten Dateien mit diesen Erweiterungen:

|Erweiterung|Beschreibung|
|---------------|-----------------|
|TARGETS|Enthält `Target`-XML-Elemente, die die vom Ziel ausgeführten Aufgaben angeben. Enthält auch `PropertyGroup`-, `ItemGroup`- und `ItemDefinitionGroup`-Elemente sowie benutzerdefinierte `Item`-Elemente, die zum Zuweisen von Dateien und Befehlszeilenoptionen zu Aufgabenparametern verwendet werden.<br /><br /> Weitere Informationen finden Sie unter [Zielelement (MSBuild)](/visualstudio/msbuild/target-element-msbuild).|
|PROPS|Enthält `Property Group`-XML-Elemente und benutzerdefinierte `Property`-XML-Elemente, die während eines Builds verwendete Datei- und Parametereinstellungen angeben.<br /><br /> Enthält auch `ItemDefinitionGroup`-XML-Elemente und benutzerdefinierte `Item`-XML-Elemente, die zusätzliche Einstellungen angeben. In einer Elementdefinitionsgruppe definierte Elemente ähneln Eigenschaften, allerdings kann in der Befehlszeile nicht auf sie zugegriffen werden. Visual Studio-Projektdateien verwenden häufig Elemente statt Eigenschaften, um Einstellungen darzustellen.<br /><br /> Weitere Informationen finden Sie unter [ItemGroup-Element (MSBuild)](/visualstudio/msbuild/itemgroup-element-msbuild), 
[ItemDefinitionGroup-Element (MSBuild)](/visualstudio/msbuild/itemdefinitiongroup-element-msbuild) und [Item-Element (MSBuild)](/visualstudio/msbuild/item-element-msbuild).|
|.xml|Enthält XML-Elemente, die IDE-Benutzeroberflächenelemente, z. B. Eigenschaftenblätter, Eigenschaftenseiten oder Textfeld- bzw. Listenfeldsteuerelemente, deklarieren und initialisieren.<br /><br /> Die XML-Dateien unterstützen direkt die IDE, nicht MSBuild. Die Werte von IDE-Eigenschaften werden jedoch zur Erstellung von Eigenschaften und Elementen verwendet.<br /><br /> Die meisten XML-Dateien befinden sich in einem gebietsschemaspezifischen Unterverzeichnis. Dateien für den englisch-amerikanischen Bereich befinden sich z. B. in $(VCTargetsPath)\1033\\.|

## <a name="user-targets-and-properties"></a>Benutzerziele und -eigenschaften

Es ist hilfreich zu wissen, welche Eigenschaften und Ziele nützlich und relevant sind, um MSBuild in der Befehlszeile am effektivsten verwenden zu können. Die meisten Eigenschaften und Ziele dienen der Implementierung des Visual Studio-Buildsystems und sind daher für den Benutzer nicht relevant. In diesem Abschnitt werden einige lohnende benutzerorientierte Eigenschaften und Ziele beschrieben.

### <a name="platformtoolset-property"></a>PlatformToolset-Eigenschaft

Die `PlatformToolset`-Eigenschaft bestimmt, welches MSVC-Toolset im Build verwendet wird. Standardmäßig wird das aktuelle Toolset verwendet. Wenn diese Eigenschaft festgelegt ist, wird der Wert der Eigenschaft mit Literalzeichenfolgen verkettet, um den Pfad eines Verzeichnisses zu bilden, das die für die Erstellung eines Projekts für eine bestimmte Plattform erforderlichen Eigenschafts- und Zieldateien enthält. Das Plattformtoolset muss installiert sein, um Builds mithilfe dieser Plattform-Toolsetversion zu erstellen.

Legen Sie beispielsweise die `PlatformToolset`-Eigenschaft auf `v140` fest, um zur Erstellung der Anwendung Visual Studio 2015-Tools und Bibliotheken zu verwenden:

`msbuild myProject.vcxproj /p:PlatformToolset=v140`

### <a name="preferredtoolarchitecture-property"></a>PreferredToolArchitecture-Eigenschaft

Die `PreferredToolArchitecture`-Eigenschaft bestimmt, ob der 32-Bit- oder 64-Bit-Compiler sowie die entsprechenden Tools im Build verwendet werden. Diese Eigenschaft beeinflusst nicht die Ausgabeplattformarchitektur oder Konfiguration. Standardmäßig verwendet MSBuild die x86-Version des Compilers und der Tools, wenn diese Eigenschaft nicht festgelegt wird.

Legen Sie beispielsweise die `PreferredToolArchitecture`-Eigenschaft auf `x64` fest, um den 64-Bit-Compiler und 64-Bit-Tools zum Erstellen Ihrer Anwendung zu verwenden:

`msbuild myProject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="useenv-property"></a>UseEnv-Eigenschaft

Standardmäßig setzen die plattformspezifischen Einstellungen für das aktuelle Projekt die PATH-, INCLUDE-, LIB-, LIBPATH-, CONFIGURATION- und PLATFORM-Umgebungsvariablen außer Kraft. Legen Sie die `UseEnv`-Eigenschaft auf **true** fest, um zu gewährleisten, dass die Umgebungsvariablen nicht überschrieben werden.

`msbuild myProject.vcxproj /p:UseEnv=true`

### <a name="targets"></a>Ziele

In den Visual Studio-Supportdateien sind Hunderte von Zielen enthalten. Die meisten sind jedoch systemorientierte Ziele, die der Benutzer ignorieren kann. Den meisten Systemzielen wird ein Unterstrich (_) vorangestellt oder sie verfügen über einen Namen, der mit "PrepareFor", "Compute", "Before", "After", "Pre" oder "Post" beginnt.

In der folgenden Tabelle sind mehrere nützliche benutzerorientierte Ziele aufgeführt.

|Target|Beschreibung|
|------------|-----------------|
|BscMake|Führt das Microsoft-Wartungshilfsprogramm zum Durchsuchen von Informationen aus ("bscmake.exe").|
|Build|Erstellt das Projekt.<br /><br /> Dies ist das Standardziel für ein Projekt.|
|ClCompile|Führt das MSVC-Compilertool („cl.exe“) aus.|
|Bereinigen|Löscht temporäre und zwischengespeicherte Builddateien.|
|Lib|Führt das 32-Bit-Tool von Microsoft zur Bibliotheksverwaltung ("lib.exe") aus.|
|Link|Führt das MSVC-Linkertool („link.exe“) aus.|
|ManifestResourceCompile|Extrahiert eine Liste der Ressourcen aus einem Manifest und führt das Microsoft Windows-Ressourcencompilertool ("rc.exe") aus.|
|Midl|Führt das MIDL (Microsoft Interface Definition Language)-Compilertool ("midl.exe") aus.|
|Neu erstellen|Bereinigt und erstellt das Projekt.|
|ResourceCompile|Führt das Microsoft Windows-Ressourcencompilertool ("rc.exe") aus.|
|XdcMake|Führt das XML-Dokumentationstool ("xdcmake.exe") aus.|
|Xsd|Führt das XML-Schemadefinitionstool ("Xsd.exe") aus. *Siehe den Hinweis unten.*|

> [!NOTE]
> In Visual Studio 2017 und höher ist die Unterstützung von C++-Projekten für **xsd**-Dateien veraltet. Sie können **Microsoft.VisualC.CppCodeProvider** weiterhin verwenden, indem Sie die Datei **CppCodeProvider.dll** manuell dem globalen Assemblycache hinzufügen.

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
