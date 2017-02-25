---
title: "AddCommonConfig | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "AddCommonConfig"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddCommonConfig-Methode"
ms.assetid: 16abad93-6dd0-4daa-bf76-91eb6ffbdffa
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# AddCommonConfig
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fügt dem Projekt die Standardkonfigurationen hinzu.  
  
## Syntax  
  
```  
  
      function AddCommonConfig(   
   oProj,   
   strProjectName    
);  
```  
  
#### Parameter  
 `oProj`  
 Das ausgewählte Projekt.  
  
 `strProjectName`  
 Der Name des Projekts.  
  
## Hinweise  
 Rufen Sie diese Funktion auf, um dem Projekt, das vom Assistenten erstellt wird, die Konfigurationen des Standardcodemodells hinzuzufügen.  Sie können entweder eine Releasekonfiguration oder eine Debugkonfiguration angeben.  In den folgenden Tabellen werden für jeden Konfigurationstyp die Standardeinstellungen der Codemodellobjekt\-Eigenschaften aufgelistet.  
  
### Visual C\+\+\-Compilertoolobjekt  
  
|Objekteigenschaft|Einstellung für Releasekonfiguration|Einstellung für Debugkonfiguration|  
|-----------------------|------------------------------------------|----------------------------------------|  
|<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader*>|pchUseUsingSpecific|pchUseUsingSpecific|  
|<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarningLevel*>|3|3|  
|<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.MinimalRebuild*>|Nicht zutreffend|true|  
|<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat*>|debugEnabled|debugEditAndContinue|  
|<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization*>|optimizeMaxSpeed|Nicht zutreffend|  
|<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BasicRuntimeChecks*>|Nicht zutreffend|runtimeBasicCheckAll|  
|<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Detect64BitPortabilityProblems*>|true|true|  
|<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers*>|true|Nicht zutreffend|  
|<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking*>|true|Nicht zutreffend|  
|<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StringPooling*>|true|Nicht zutreffend|  
  
### Visual C\+\+\-Konfigurationsobjekt  
  
|Objekteigenschaft|Einstellung für Releasekonfiguration|Einstellung für Debugkonfiguration|  
|-----------------------|------------------------------------------|----------------------------------------|  
|<xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.IntermediateDirectory*>|Release|Debug|  
|<xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.OutputDirectory*>|Release|Debug|  
  
### Visual C\+\+\-Linkertoolobjekt  
  
|Objekteigenschaft|Einstellung für Releasekonfiguration|Einstellung für Debugkonfiguration|  
|-----------------------|------------------------------------------|----------------------------------------|  
|<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SubSystem*>|subSystemWindows|subSystemWindows|  
|<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TargetMachine*>|machineX86|machineX86|  
|<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateDebugInformation*>|true|true|  
  
## Beispiel  
  
```  
// Create the Visual C++ project.  
selProj = CreateProject(strProjectName, strProjectPath);  
// Add the common configuration to the project.  
   AddCommonConfig(selProj, strProjectName);  
   selProj.Object.keyword = "MyProj";  
```  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)