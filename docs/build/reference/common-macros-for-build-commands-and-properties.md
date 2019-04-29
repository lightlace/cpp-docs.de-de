---
title: Gängige Makros für MSBuild-Befehlen und Eigenschaften
ms.date: 03/20/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
helpviewer_keywords:
- $(FrameworkSDKDir) macro
- ProjectName macro $(ProjectName)
- DevEnvDir macro $(DevEnvDir)
- $(DevEnvDir) macro
- TargetPath macro $(TargetPath)
- VSInstallDir macro $(VSInstallDir)
- $(InputFileName) macro
- $(SolutionFileName) macro
- macros [C++], build macros
- InputFileName macro $(InputFileName)
- $(VCInstallDir) macro
- $(IntDir) macro
- $(ConfigurationName) macro
- SolutionDir macro $(SolutionDir)
- $(TargetPath) macro
- $(Inherit) macro
- $(SolutionPath) macro
- WebDeployRoot macro $(WebDeployRoot)
- WebDeployPath macro $(WebDeployPath)
- StopEvaluating macro $(StopEvaluating)
- $(RootNamespace) macro
- $(WebDeployRoot) macro
- ProjectPath macro $(ProjectPath)
- $(ProjectPath) macro
- $(InputDir) macro
- SolutionName macro $(SolutionName)
- ProjectExt macro $(ProjectExt)
- $(TargetExt) macro
- $(ProjectFileName) macro
- TargetName macro $(TargetName)
- $(References) macro
- References macro $(References)
- TargetExt macro $(TargetExt)
- ProjectDir macro $(ProjectDir)
- $(TargetDir) macro
- SolutionExt macro $(SolutionExt)
- $(SolutionDir) macro
- ProjectFileName macro $(ProjectFileName)
- VCInstallDir macro $(VCInstallDir)
- $(InputExt) macro
- $(TargetFileName) macro
- $(SolutionExt) macro
- PlatformName macro $(PlatformName)
- IntDir macro $(IntDir)
- $(FrameworkVersion) macro
- $(ProjectDir) macro
- build macros [C++]
- InputPath macro $(InputPath)
- $(VSInstallDir) macro
- $(WebDeployPath) macro
- TargetFileName macro $(TargetFileName)
- NoInherit macro $(NoInherit)
- ConfigurationName macro $(ConfigurationName)
- $(ProjectExt) macro
- TargetDir macro $(TargetDir)
- InputName macro $(InputName)
- $(ProjectName) macro
- FrameworkSDKDir macro $(FrameworkSDKDir)
- $(ParentName) macro
- InputExt macro $(InputExt)
- $(SafeRootNamespace) macro
- InputDir macro $(InputDir)
- $(FxCopDir) macro
- $(RemoteMachine) macro
- Inherit macro $(Inherit)
- FrameworkVersion macro $(FrameworkVersion)
- $(StopEvaluating) macro
- $(OutDir) macro
- FrameworkDir macro $(FrameworkDir)
- SolutionFileName macro $(SolutionFileName)
- $(NoInherit) macro
- RemoteMachine macro $(RemoteMachine)
- properties [C++], build property macros
- $(TargetName) macro
- $(SolutionName) macro
- $(InputPath) macro
- ParentName macro $(ParentName)
- OutDir macro $(OutDir)
- SafeRootNamespace macro $(SafeRootNamespace)
- FxCopDir macro $(FxCopDir)
- $(InputName) macro
- RootNamespace macro $(RootNamespace)
- builds [C++], macros
- $(FrameworkDir) macro
- $(PlatformName) macro
- $(PlatformShortName) macro
- SolutionPath macro $(SolutionPath)
ms.assetid: 239bd708-2ea9-4687-b264-043f1febf98b
ms.openlocfilehash: 46fdd5e356ded96388a154ff459ef4cc3c02267f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294439"
---
# <a name="common-macros-for-msbuild-commands-and-properties"></a>Gängige Makros für MSBuild-Befehlen und Eigenschaften

Je nach Ihrer Installationsoptionen kann Visual Studio Hunderte von Makros für Sie in einem Visual Studio-Projekt (basierend auf MSBuild) zur Verfügung. Diese entsprechen den MSBuild-Eigenschaften, die standardmäßig, in PROPS- oder TARGETS-Dateien oder in Ihren Projekteinstellungen festgelegt sind. Sie können diese Makros an einer beliebigen Stelle im Dialogfeld **Eigenschaftenseiten** eines Projekts verwenden, an der Zeichenfolgen akzeptiert werden. Bei diesen Makros wird keine Groß-/Kleinschreibung berücksichtigt.

## <a name="view-the-current-properties-and-macros"></a>Anzeigen der aktuellen Eigenschaften und Makros

Zum Anzeigen aller derzeit verfügbaren Makros, in der **Eigenschaftenseiten** Dialogfeld unter **VC++-Verzeichnisse**, wählen Sie den Dropdown-Pfeil am Ende der Zeile mit einer Eigenschaft. Klicken Sie auf **bearbeiten** und wählen Sie dann im Dialogfeld "Bearbeiten" die **Makros** Schaltfläche. Die aktuell für Visual Studio sichtbaren Eigenschaften und Makros werden jeweils zusammen mit dem aktuellen Wert aufgeführt. Weitere Informationen finden Sie unter den **Specifying User-Defined Werte** Abschnitt [C++-Projekt Referenz zur](property-pages-visual-cpp.md).

![Schaltfläche für VC++-Makros](../media/vcppdir_libdir_macros.png "\"Makros\"")

## <a name="list-of-common-macros"></a>Liste der häufig verwendeten Makros

Diese Tabelle wird beschrieben, eine häufig verwendete Teilmenge der verfügbaren Makros; Es gibt viele der hier nicht mehr aufgeführt. Wechseln Sie zu der **Makros** Dialogfeld, um alle Eigenschaften und deren aktuelle Werte in Ihrem Projekt angezeigt. Ausführliche Informationen zum Erstellen von MSBuild-Eigenschaftsdefinitionen und wie diese als Makros in PROPS, TARGETS und VCXPROJ-Dateien verwendet werden, finden Sie unter [MSBuild-Eigenschaften](/visualstudio/msbuild/msbuild-properties).

|Makro|Beschreibung|
|-----------|-----------------|
|**$(Configuration)**|Der Name der aktuellen Projektkonfiguration, z.B. „Debug“.|
|**$(DevEnvDir)**|Das Installationsverzeichnis von Visual Studio (als „Laufwerk + Pfad“ definiert). Es enthält den nachgestellten umgekehrten Schrägstrich „\\“.|
|**$(FrameworkDir)**|Das Verzeichnis, in dem .NET Framework installiert wurde.|
|**$(FrameworkSDKDir)**|Das Verzeichnis, in dem Sie .NET Framework installiert haben. .NET Framework könnte als Teil von Visual Studio oder separat installiert worden sein.|
|**$(FrameworkVersion)**|Die Version von .NET Framework, die von Visual Studio verwendet wurde. In Kombination mit **$(FrameworkDir)** stellt dies den vollständigen Pfad zu der Version von .NET Framework dar, die von Visual Studio verwendet wurde.|
|**$(FxCopDir)**|Der Pfad zur Datei „fxcop.cmd“. Die Datei „fxcop.cmd“ wird nicht mit allen Editionen von Visual C++ installiert.|
|**$(IntDir)**|Der Pfad zum Verzeichnis, das für Zwischendateien angegeben wurde. Ist dies ein relativer Pfad, gelangen die Zwischendateien in diesen Pfad, der an das Projektverzeichnis angefügt wird. Dieser Pfad sollte über einen nachgestellten Schrägstrich verfügen. Dies wird in den Wert für die **Intermediate Directory** -Eigenschaft aufgelöst. Verwenden Sie nicht **$(OutDir)** , um diese Eigenschaft zu definieren.|
|**$(OutDir)**|Der Pfad zum Ausgabedateiverzeichnis. Ist dies ein relativer Pfad, gelangen die Ausgabedateien in diesen Pfad, der an das Projektverzeichnis angefügt wird. Dieser Pfad sollte über einen nachgestellten Schrägstrich verfügen. Dies wird in den Wert für die **Output Directory** -Eigenschaft aufgelöst. Verwenden Sie nicht **$(IntDir)** , um diese Eigenschaft zu definieren.|
|**$(Platform)**|Der Name der aktuellen Projektplattform (z.B. „Win32“).|
|**$(PlatformShortName)**|Der Kurzname der aktuellen Architektur, z. B. "X86" oder "X64".|
|**$(ProjectDir)**|Das Verzeichnis des Projekts (als „Laufwerk + Pfad“ definiert). Es enthält den nachgestellten umgekehrten Schrägstrich „\\“.|
|**$(ProjectExt)**|Die Dateierweiterung des Projekts. Sie umfasst den „.“ vor der Dateierweiterung.|
|**$(ProjectFileName)**|Der Dateiname des Projekts (als „Basisname + Dateierweiterung“ definiert).|
|**$(ProjectName)**|Der Basisname des Projekts.|
|**$(ProjectPath)**|Der absolute Pfadname des Projekts (als „Laufwerk + Pfad + Basisname + Dateierweiterung“ definiert).|
|**$(RemoteMachine)**|Auf der Debugeigenschaftenseite auf den Wert der **Remote Machine** -Eigenschaft festgelegt. Weitere Informationen finden Sie unter [Projekteinstellungen für eine C- oder C++-Debugkonfiguration](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration) .|
|**$(RootNameSpace)**|Der Namespace, falls vorhanden, der die Anwendung enthält.|
|**$(SolutionDir)**|Das Verzeichnis der Projektmappe (als „Laufwerk + Pfad“ definiert). Es enthält den nachgestellten umgekehrten Schrägstrich „\\“. Wird nur bei der Erstellung einer Projektmappe in der IDE definiert.|
|**$(SolutionExt)**|Die Dateierweiterung der Projektmappe. Sie umfasst den „.“ vor der Dateierweiterung. Wird nur bei der Erstellung einer Projektmappe in der IDE definiert.|
|**$(SolutionFileName)**|Der Dateiname der Projektmappe (als „Basisname + Dateierweiterung“ definiert). Wird nur bei der Erstellung einer Projektmappe in der IDE definiert.|
|**$(SolutionName)**|Der Basisname der Projektmappe. Wird nur bei der Erstellung einer Projektmappe in der IDE definiert.|
|**$(SolutionPath)**|Der absolute Pfadname der Projektmappe (als „Laufwerk + Pfad + Basisname + Dateierweiterung“ definiert). Wird nur bei der Erstellung einer Projektmappe in der IDE definiert.|
|**$(TargetDir)**|Das Verzeichnis der primären Ausgabedatei für den Build (als „Laufwerk + Pfad“ definiert). Es enthält den nachgestellten umgekehrten Schrägstrich „\\“.|
|**$(TargetExt)**|Die Dateierweiterung der primären Ausgabedatei für den Build. Sie umfasst den „.“ vor der Dateierweiterung.|
|**$(TargetFileName)**|Der Dateiname der primären Ausgabedatei für den Build (als „Basisname + Dateierweiterung“ definiert).|
|**$(TargetName)**|Der Basisname der primären Ausgabedatei für den Build.|
|**$(TargetPath)**|Der absolute Pfadname der primären Ausgabedatei für den Build (als „Laufwerk + Pfad + Basisname + Dateierweiterung“ definiert).|
|**$(VCInstallDir)**|Das Verzeichnis, das den C++-Inhalt Ihrer Visual Studio-Installation enthält. Diese Eigenschaft enthält die Version des angezielten Visual C++-Toolsets, die sich möglicherweise vom Visual Studio-Host unterscheidet. Beim Erstellen mit `$(PlatformToolset) = v140` enthält **$(VCInstallDir)** z.B. den Pfad zur Installation von Visual C++ 2015.|
|**$(VSInstallDir)**|Das Verzeichnis, in dem Visual Studio installiert wurde. Diese Eigenschaft enthält die Version des angezielten Visual Studio-Toolsets, die sich möglicherweise vom Visual Studio-Host unterscheidet. Beim Erstellen mit `$(PlatformToolset) = v110`, enthält **$(VSInstallDir)** z. B. den Pfad zur Installation von Visual Studio 2012.|
|**$(WebDeployPath)**|Der relative Pfad vom Stamm der Webbereitstellung zum Speicherort der Projektausgaben. Gibt denselben Wert zurück wie <xref:Microsoft.VisualStudio.VCProjectEngine.VCWebDeploymentTool.RelativePath%2A>.|
|**$(WebDeployRoot)**|Der absolute Pfad zum Speicherort von **\<localhost>**. Beispiel: „c:\inetpub\wwwroot“.|

## <a name="obsolete-macros"></a>Veraltete Makros

Das Buildsystem wurde zwischen Visual Studio 2008 und Visual Studio 2010 erheblich geändert. Viele Makros, die in früheren Projekttypen verwendet wurden, wurden durch neue ersetzt. Diese Makros werden nicht mehr verwendet oder wurden durch mindestens eine entsprechende Eigenschaft oder ein Makro für [Elementmetadatenwerte](/visualstudio/msbuild/itemmetadata-element-msbuild) (**%(**_name_**)**) ersetzt. Makros, die als „Migriert“ markiert sind, können mithilfe des Migrationstools für Projekte aktualisiert werden. Wenn das Projekt, das das Makro enthält, zudem von Visual Studio 2008 oder früher zu Visual Studio 2010 migriert wird, konvertiert Visual Studio das Makro in das entsprechende aktuelle Makro. Höhere Versionen von Visual Studio können Projekte von Visual Studio 2008 und früher nicht in den neuen Projekttyp konvertieren. Sie müssen diese Projekte in zwei Schritten konvertieren. Konvertieren Sie sie zunächst in Visual Studio 2010, und konvertieren Sie das Ergebnis anschließend in ihre neuere Version von Visual Studio. Weitere Informationen finden Sie in der [Übersicht über potenzielle Probleme beim Upgrade](../../porting/overview-of-potential-upgrade-issues-visual-cpp.md).

|Makro|Beschreibung|
|-----------|-----------------|
|**$(InputDir)**|(Migriert) Das Verzeichnis der Eingabedatei (als „Laufwerk + Pfad“ definiert). Es enthält den nachgestellten umgekehrten Schrägstrich „\\“. Wenn das Projekt die Eingabe darstellt, entspricht dieses Makro **$(ProjectDir)**.|
|**$(InputExt)**|(Migriert) Die Dateierweiterung der Eingabedatei. Sie umfasst den „.“ vor der Dateierweiterung. Wenn das Projekt die Eingabe darstellt, entspricht dieses Makro **$(ProjectExt)**. Für Quelldateien entspricht dies **%(Extension)**.|
|**$(InputFileName)**|(Migriert) Der Dateiname der Eingabedatei (als „Basisname + Dateierweiterung“ definiert). Wenn das Projekt die Eingabe darstellt, entspricht dieses Makro **$(ProjectFileName)**. Für Quelldateien entspricht dies **%(Identity)**.|
|**$(InputName)**|(Migriert) Der Basisname der Eingabedatei. Wenn das Projekt die Eingabe darstellt, entspricht dieses Makro **$(ProjectName)**. Für Quelldateien entspricht dies **%(Filename)**.|
|**$(InputPath)**|(Migriert) Der absolute Pfadname der Eingabedatei (als „Laufwerk + Pfad + Basisname + Dateierweiterung“ definiert). Wenn das Projekt die Eingabe darstellt, entspricht dieses Makro **$(ProjectPath)**. Für Quelldateien entspricht dies **%(FullPath)**.|
|**$(ParentName)**|Der Name des Elements, das dieses Projektelement enthält. Dies wird der Name des übergeordneten Ordners oder der Projektname sein.|
|**$(SafeInputName)**|Der Name der Datei als gültiger Klassenname, ohne die Dateierweiterung. Für diese Eigenschaft gibt es keine genaue Entsprechung.|
|**$(SafeParentName)**|Der Name des unmittelbar übergeordneten Elements im gültigen Namensformat. Ein Formular ist beispielsweise das übergeordnete Element einer RESX-Datei. Für diese Eigenschaft gibt es keine genaue Entsprechung.|
|**$(SafeRootNamespace)**|Der Namespacename, in dem die Projekt-Assistenten Code hinzufügen. Dieser Namespacename darf nur Zeichen enthalten, die in einem gültigen C++-Bezeichner zulässig sind. Für diese Eigenschaft gibt es keine genaue Entsprechung.|

## <a name="see-also"></a>Siehe auch

- [Visual Studio-Projekte: C++](../creating-and-managing-visual-cpp-projects.md)
- [Visual C++-Handbuch: Portieren und Aktualisieren](../../porting/visual-cpp-porting-and-upgrading-guide.md)
- [Überblick über potenzielle Upgradeprobleme (Visual C++)](../../porting/overview-of-potential-upgrade-issues-visual-cpp.md)
