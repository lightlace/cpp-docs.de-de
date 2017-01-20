---
title: "Makros f&#252;r Buildbefehle und -eigenschaften"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles"
  - "VC.Project.VCCLCompilerTool.XMLDocumentationFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "$(ConfigurationName)-Makro"
  - "$(DevEnvDir)-Makro"
  - "$(FrameworkDir)-Makro"
  - "$(FrameworkSDKDir)-Makro"
  - "$(FrameworkVersion)-Makro"
  - "$(FxCopDir)-Makro"
  - "$(Inherit)-Makro"
  - "$(InputDir)-Makro"
  - "$(InputExt)-Makro"
  - "$(InputFileName)-Makro"
  - "$(InputName)-Makro"
  - "$(InputPath)-Makro"
  - "$(IntDir)-Makro"
  - "$(NoInherit)-Makro"
  - "$(OutDir)-Makro"
  - "$(ParentName)-Makro"
  - "$(PlatformName)-Makro"
  - "$(ProjectDir)-Makro"
  - "$(ProjectExt)-Makro"
  - "$(ProjectFileName)-Makro"
  - "$(ProjectName)-Makro"
  - "$(ProjectPath)-Makro"
  - "$(References)-Makro"
  - "$(RemoteMachine)-Makro"
  - "$(RootNamespace)-Makro"
  - "$(SafeRootNamespace)-Makro"
  - "$(SolutionDir)-Makro"
  - "$(SolutionExt)-Makro"
  - "$(SolutionFileName)-Makro"
  - "$(SolutionName)-Makro"
  - "$(SolutionPath)-Makro"
  - "$(StopEvaluating)-Makro"
  - "$(TargetDir)-Makro"
  - "$(TargetExt)-Makro"
  - "$(TargetFileName)-Makro"
  - "$(TargetName)-Makro"
  - "$(TargetPath)-Makro"
  - "$(VCInstallDir)-Makro"
  - "$(VSInstallDir)-Makro"
  - "$(WebDeployPath)-Makro"
  - "$(WebDeployRoot)-Makro"
  - "Buildmakros [C++]"
  - "Builds [C++], Makros"
  - "ConfigurationName-Makro $(ConfigurationName)"
  - "DevEnvDir-Makro $(DevEnvDir)"
  - "FrameworkDir-Makro $(FrameworkDir)"
  - "FrameworkSDKDir-Makro $(FrameworkSDKDir)"
  - "FrameworkVersion-Makro $(FrameworkVersion)"
  - "FxCopDir-Makro $(FxCopDir)"
  - "Inherit-Makro $(Inherit)"
  - "InputDir-Makro $(InputDir)"
  - "InputExt-Makro $(InputExt)"
  - "InputFileName-Makro $(InputFileName)"
  - "InputName-Makro $(InputName)"
  - "InputPath-Makro $(InputPath)"
  - "IntDir-Makro $(IntDir)"
  - "Makros [C++], Buildmakros"
  - "NoInherit-Makro $(NoInherit)"
  - "OutDir-Makro $(OutDir)"
  - "ParentName-Makro $(ParentName)"
  - "PlatformName-Makro $(PlatformName)"
  - "ProjectDir-Makro $(ProjectDir)"
  - "ProjectExt-Makro $(ProjectExt)"
  - "ProjectFileName-Makro $(ProjectFileName)"
  - "ProjectName-Makro $(ProjectName)"
  - "ProjectPath-Makro $(ProjectPath)"
  - "Eigenschaften [C++], Buildeigenschaftenmakros"
  - "References-Makro $(References)"
  - "RemoteMachine-Makro $(RemoteMachine)"
  - "RootNamespace-Makro $(RootNamespace)"
  - "SafeRootNamespace-Makro $(SafeRootNamespace)"
  - "SolutionDir-Makro $(SolutionDir)"
  - "SolutionExt-Makro $(SolutionExt)"
  - "SolutionFileName-Makro $(SolutionFileName)"
  - "SolutionName-Makro $(SolutionName)"
  - "SolutionPath-Makro $(SolutionPath)"
  - "StopEvaluating-Makro $(StopEvaluating)"
  - "TargetDir-Makro $(TargetDir)"
  - "TargetExt-Makro $(TargetExt)"
  - "TargetFileName-Makro $(TargetFileName)"
  - "TargetName-Makro $(TargetName)"
  - "TargetPath-Makro $(TargetPath)"
  - "VCInstallDir-Makro $(VCInstallDir)"
  - "VSInstallDir-Makro $(VSInstallDir)"
  - "WebDeployPath-Makro $(WebDeployPath)"
  - "WebDeployRoot-Makro $(WebDeployRoot)"
ms.assetid: 239bd708-2ea9-4687-b264-043f1febf98b
caps.latest.revision: 22
caps.handback.revision: "18"
ms.author: "corob"
manager: "ghogen"
---
# Makros f&#252;r Buildbefehle und -eigenschaften
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können diese Makros an einer beliebigen Stelle im Dialogfeld **Eigenschaftenseiten** eines Projekts verwenden, an der Zeichenfolgen akzeptiert werden. Bei diesen Makros wird keine Groß\-\/Kleinschreibung berücksichtigt.  
  
 Um die derzeit verfügbaren Makros in der Spalte rechts neben einem Eigenschaftennamen anzuzeigen, klicken Sie auf den Dropdownpfeil. Wenn **Bearbeiten** verfügbar ist, klicken Sie auf diese Option, und klicken Sie dann im Dialogfeld „Bearbeiten“ auf **Makros**. Weitere Informationen finden Sie unter **Specifying User\-Defined Values** im Abschnitt [Eigenschaftenseiten](../ide/property-pages-visual-cpp.md).  
  
 Makros, die als „Veraltet“ markiert sind, wenn nicht länger verwendet oder wurden durch ein entsprechendes [Elementmetadatenmakro](../Topic/ItemMetadata%20Element%20\(MSBuild\).md) \(**%\(***Name***\)**\) ersetzt. Als „Veraltet; Migriert“ markierte Makros sind ebenfalls veraltet. Wenn das Projekt, das das Makro enthält, zudem von Visual Studio 2008 migriert wird, konvertiert Visual Studio das Makro in das entsprechende aktuelle Makro.  
  
|Makro|Beschreibung|  
|-----------|------------------|  
|**$\(RemoteMachine\)**|Auf der Debugeigenschaftenseite auf den Wert der **Remote Machine** \-Eigenschaft festgelegt. Weitere Informationen finden Sie unter [Projekteinstellungen für eine C\- oder C\+\+\-Debugkonfiguration](../Topic/Project%20Settings%20for%20a%20C++%20Debug%20Configuration.md).|  
|**$\(Configuration\)**|Der Name der aktuellen Projektkonfiguration \(z. B. „Debug“\).|  
|**$\(Platform\)**|Der Name der aktuellen Projektplattform \(z. B. „Win32“\).|  
|**$\(ParentName\)**|\(Veraltet.\) Der Name des Elements, das dieses Projektelement enthält. Dies wird der Name des übergeordneten Ordners oder der Projektname sein.|  
|**$\(RootNameSpace\)**|Der Namespace, falls vorhanden, der die Anwendung enthält.|  
|**$\(IntDir\)**|Der Pfad zum Verzeichnis, das für Zwischendateien angegeben wurde. Ist dies ein relativer Pfad, gelangen die Zwischendateien in diesen Pfad, der an das Projektverzeichnis angefügt wird. Dieser Pfad sollte über einen nachgestellten Schrägstrich verfügen. Dies wird in den Wert für die **Intermediate Directory**\-Eigenschaft aufgelöst. Verwenden Sie nicht **$\(OutDir\)**, um diese Eigenschaft zu definieren.|  
|**$\(OutDir\)**|Der Pfad zum Ausgabedateiverzeichnis. Ist dies ein relativer Pfad, gelangen die Ausgabedateien in diesen Pfad, der an das Projektverzeichnis angefügt wird. Dieser Pfad sollte über einen nachgestellten Schrägstrich verfügen. Dies wird in den Wert für die **Output Directory**\-Eigenschaft aufgelöst. Verwenden Sie nicht **$\(IntDir\)**, um diese Eigenschaft zu definieren.|  
|**$\(DevEnvDir\)**|Das Installationsverzeichnis von Visual Studio \(als „Laufwerk \+ Pfad“ definiert\). Es enthält den nachgestellten umgekehrten Schrägstrich „\\“.|  
|**$\(InputDir\)**|\(Veraltet; Migriert\) Das Verzeichnis der Eingabedatei \(als „Laufwerk \+ Pfad“ definiert\). Es enthält den nachgestellten umgekehrten Schrägstrich „\\“. Wenn das Projekt die Eingabe darstellt, entspricht dieses Makro **$\(ProjectDir\)**.|  
|**$\(InputPath\)**|\(Veraltet; Migriert\) Der absolute Pfadname der Eingabedatei \(als „Laufwerk \+ Pfad \+ Basisname \+ Dateierweiterung“ definiert\). Wenn das Projekt die Eingabe darstellt, entspricht dieses Makro **$\(ProjectPath\)**.|  
|**$\(InputName\)**|\(Veraltet; Migriert\) Der Basisname der Eingabedatei. Wenn das Projekt die Eingabe darstellt, entspricht dieses Makro **$\(ProjectName\)**.|  
|**$\(InputFileName\)**|\(Veraltet; Migriert\) Der Dateiname der Eingabedatei \(als „Basisname \+ Dateierweiterung“ definiert\). Wenn das Projekt die Eingabe darstellt, entspricht dieses Makro **$\(ProjectFileName\)**.|  
|**$\(InputExt\)**|\(Veraltet; Migriert\) Die Dateierweiterung der Eingabedatei. Sie umfasst den „.“ vor der Dateierweiterung. Wenn das Projekt die Eingabe darstellt, entspricht dieses Makro **$\(ProjectExt\)**.|  
|**$\(ProjectDir\)**|Das Verzeichnis des Projekts \(als „Laufwerk \+ Pfad“ definiert\). Es enthält den nachgestellten umgekehrten Schrägstrich „\\“.|  
|**$\(ProjectPath\)**|Der absolute Pfadname des Projekts \(als „Laufwerk \+ Pfad \+ Basisname \+ Dateierweiterung“ definiert\).|  
|**$\(ProjectName\)**|Der Basisname des Projekts.|  
|**$\(ProjectFileName\)**|Der Dateiname des Projekts \(als „Basisname \+ Dateierweiterung“ definiert\).|  
|**$\(ProjectExt\)**|Die Dateierweiterung des Projekts. Sie umfasst den „.“ vor der Dateierweiterung.|  
|**$\(SolutionDir\)**|Das Verzeichnis der Projektmappe \(als „Laufwerk \+ Pfad“ definiert\). Es enthält den nachgestellten umgekehrten Schrägstrich „\\“.|  
|**$\(SolutionPath\)**|Der absolute Pfadname der Projektmappe \(als „Laufwerk \+ Pfad \+ Basisname \+ Dateierweiterung“ definiert\).|  
|**$\(SolutionName\)**|Der Basisname der Projektmappe.|  
|**$\(SolutionFileName\)**|Der Dateiname der Projektmappe \(als „Basisname \+ Dateierweiterung“ definiert\).|  
|**$\(SolutionExt\)**|Die Dateierweiterung der Projektmappe. Sie umfasst den „.“ vor der Dateierweiterung.|  
|**$\(TargetDir\)**|Das Verzeichnis der primären Ausgabedatei für den Build \(als „Laufwerk \+ Pfad“ definiert\). Es enthält den nachgestellten umgekehrten Schrägstrich „\\“.|  
|**$\(TargetPath\)**|Der absolute Pfadname der primären Ausgabedatei für den Build \(als „Laufwerk \+ Pfad \+ Basisname \+ Dateierweiterung“ definiert\).|  
|**$\(TargetName\)**|Der Basisname der primären Ausgabedatei für den Build.|  
|**$\(TargetFileName\)**|Der Dateiname der primären Ausgabedatei für den Build \(als „Basisname \+ Dateierweiterung“ definiert\).|  
|**$\(TargetExt\)**|Die Dateierweiterung der primären Ausgabedatei für den Build. Sie umfasst den „.“ vor der Dateierweiterung.|  
|**$\(VSInstallDir\)**|Das Verzeichnis, in dem Visual Studio installiert wurde.<br /><br /> Diese Eigenschaft enthält die Version der Visual Studio\-Zielversion, die sich möglicherweise vom Visual Studio\-Host unterscheidet. Beim Erstellen mit `$(PlatformToolset) = v110`, enthält **$\(VSInstallDir\)** z. B. den Pfad zur Installation von Visual Studio 2012.|  
|**$\(VCInstallDir\)**|Das Verzeichnis, in dem Visual C\+\+ installiert wurde.<br /><br /> Diese Eigenschaft enthält die Version der Visual C\+\+\-Zielversion, die sich möglicherweise vom Visual Studio\-Host unterscheidet. Beim Erstellen mit `$(PlatformToolset) = v90`, enthält **$\(VCInstallDir\)** z. B. den Pfad zur Installation von Visual C\+\+ 2008.|  
|**$\(FrameworkDir\)**|Das Verzeichnis, in dem .NET Framework installiert wurde.|  
|**$\(FrameworkVersion\)**|Die Version von .NET Framework, die von Visual Studio verwendet wurde. In Kombination mit **$\(FrameworkDir\)** stellt dies den vollständigen Pfad zu der Version von .NET Framework dar, die von Visual Studio verwendet wurde.|  
|**$\(FrameworkSDKDir\)**|Das Verzeichnis, in dem Sie .NET Framework installiert haben. .NET Framework könnte als Teil von Visual Studio oder separat installiert worden sein.|  
|**$\(WebDeployPath\)**|Der relative Pfad vom Stamm der Webbereitstellung zum Speicherort der Projektausgaben. Gibt denselben Wert zurück wie <xref:Microsoft.VisualStudio.VCProjectEngine.VCWebDeploymentTool.RelativePath*>.|  
|**$\(WebDeployRoot\)**|Der absolute Pfad zum Speicherort von **\<localhost\>**. Beispiel: „c:\\inetpub\\wwwroot“.|  
|**$\(SafeParentName\)**|\(Veraltet.\) Der Name des unmittelbar übergeordneten Elements im gültigen Namensformat. Ein Formular ist beispielsweise das übergeordnete Element einer RESX\-Datei.|  
|**$\(SafeInputName\)**|\(Veraltet.\) Der Name der Datei als gültiger Klassenname, ohne die Dateierweiterung.|  
|**$\(SafeRootNamespace\)**|\(Veraltet.\) Der Namespacename, in dem die Projekt\-Assistenten Code hinzufügen. Dieser Namespacename darf nur Zeichen enthalten, die in einem gültigen C\+\+\-Bezeichner zulässig sind.|  
|**$\(FxCopDir\)**|Der Pfad zur Datei „fxcop.cmd“. Die Datei „fxcop.cmd“ wird nicht mit allen Editionen von Visual C\+\+ installiert.|  
  
## Siehe auch  
 [Erstellen von C\+\+\-Projekten in Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)