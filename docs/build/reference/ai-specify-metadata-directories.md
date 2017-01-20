---
title: "/AI (Metadatenverzeichnisse festlegen)"
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
  - "VC.Project.VCCLCompilerTool.AdditionalUsingDirectories"
  - "VC.Project.VCNMakeTool.AssemblySearchPath"
  - "/AI"
  - "VC.Project.VCCLWCECompilerTool.AdditionalUsingDirectories"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/AI (Compileroption) [C++]"
  - "AI (Compileroption) [C++]"
  - "-AI (Compileroption) [C++]"
ms.assetid: fb9c1846-504c-4a3b-bb39-c8696de32f6f
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# /AI (Metadatenverzeichnisse festlegen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt ein Verzeichnis an, das der Compiler durchsucht, um Dateiverweise aufzulösen, die an die `#using`\-Direktive übergeben wurden.  
  
## Syntax  
  
```  
/AIdirectory  
```  
  
## Argumente  
 `directory`  
 Das Verzeichnis oder der Pfad, den der Compiler durchsuchen soll.  
  
## Hinweise  
 Es kann nur ein Verzeichnis an einen **\/AI**\-Aufruf übergeben werden.  Geben Sie eine **\/AI**\-Option für jeden Pfad an, den der Compiler durchsuchen soll.  Wenn Sie beispielsweise dem Compilersuchpfad für `#using`\-Direktiven sowohl C:\\Project\\Meta als auch C:\\Common\\Meta hinzufügen möchten, fügen Sie zur Befehlszeile des Compilers `/AI"C:\Project\Meta" /AI"C:\Common\Meta"` hinzu oder fügen Sie die beiden Verzeichnisse zur Eigenschaft **Zusätzliche \#using\-Verweise** in Visual Studio hinzu.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Wählen Sie im Navigationsbereich **Konfigurationseigenschaften**, **C\/C\+\+**, **Allgemein** aus.  
  
3.  Bearbeiten Sie die Eigenschaft **Zusätzliche \#using\-Verweise**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalUsingDirectories*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [\#using\-Direktive](../../preprocessor/hash-using-directive-cpp.md)