---
title: "SetCommonPchSettings | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SetCommonPchSettings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetCommonPchSettings-Methode"
ms.assetid: 12f5524b-f654-4222-b979-8ee0d9f58c14
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# SetCommonPchSettings
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Richtet die Einstellungen des vorkompilierten Headers für das Projekt ein.  
  
## Syntax  
  
```  
  
      function SetCommonPchSettings(   
   oProj    
);  
```  
  
#### Parameter  
 `oProj`  
 Das ausgewählte Projekt.  
  
## Hinweise  
 Rufen Sie diese Funktion auf, um die Einstellungen des vorkompilierten Headers für das Projekt einzurichten.  
  
 Diese Funktion legt die <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader*>\-Eigenschaft auf Folgendes fest:  
  
-   **pchUseUsingSpecific** Verwendet die Compilereinstellung [\/Yu \(Vorkompilierten Header verwenden\)](../build/reference/yu-use-precompiled-header-file.md).  
  
-   **pchCreateUsingSpecific** Verwendet die Compilereinstellung [\/Yc \(Datei der vorkompilierten Header erstellen\)](../build/reference/yc-create-precompiled-header-file.md).  
  
## Beispiel  
  
```  
if ((strAppType == "LIB" || ((strAppType == "CONSOLE") &&   
   wizard.FindSymbol(SUPPORT_MFC"))) && !Pch)  
   {  
      AddFilesToProject(selProj, strProjectName, InfFile);  
      SetNoCommonPchSettings(selProj);  
   }  
else  
   {  
      AddFilesToProject(selProj, strProjectName, InfFile);  
      SetcommonPchSettings(selProj);  
   }  
```  
  
## Siehe auch  
 [Anpassen von C\+\+\-Assistenten mit allgemeinen JScript\-Funktionen](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)   
 [SetNoPchSettings](../ide/setnopchsettings.md)   
 [AddCommonConfig](../ide/addcommonconfig.md)