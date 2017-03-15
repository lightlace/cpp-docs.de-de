---
title: "/FU (Name der expliziten #using-Datei)"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.ForcedUsingFiles"
  - "/FU"
  - "VC.Project.VCNMakeTool.ForcedUsingAssemblies"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FU (Compileroption) [C++]"
  - "FU (Compileroption) [C++]"
  - "-FU (Compileroption) [C++]"
ms.assetid: 698f8603-457f-435a-baff-5ac9243d6ca1
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# /FU (Name der expliziten #using-Datei)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Compileroption, die als Alternative zum Übergeben eines Dateinamens an [\#using\-Direktive](../../preprocessor/hash-using-directive-cpp.md) im Quellcode verwenden können.  
  
## Syntax  
  
```  
/FU file  
```  
  
## Argumente  
 `file`  
 die Metadatendatei, auf die in diesem Kompilierungsvorgang verwiesen wird.  
  
## Hinweise  
 Das \/FU\- Schalternehmen nur ein Dateiname.  Um mehrere Dateien anzugeben, verwenden Sie \/FU mit jedem.  
  
 Wenn Sie [!INCLUDE[cppcli](../../build/reference/includes/cppcli_md.md)] verwenden und Metadaten verweisen, um die [Friend\-Assemblys](../../dotnet/friend-assemblies-cpp.md)\-Funktion zu verwenden, können Sie **\/FU** nicht verwenden.  Sie müssen die Metadaten im Code verweisen, indem Sie `#using` zusammen mit dem `[as friend]`\-Attribut verwenden.  Friend\-Assemblys werden nicht in [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] \([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]\) unterstützt.  
  
 Informationen darüber, wie eine Assembly oder ein Modul während der Common Language Runtime \(CLR\), finden Sie unter [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md).  Informationen darüber, wie Sie in [!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)], finden Sie unter [Erstellen von Apps und Bibliotheken](../Topic/Building%20apps%20and%20libraries%20\(C++-CX\).md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Wählen Sie den Ordner **C\/C\+\+** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Erweitert** aus.  
  
4.  Ändern Sie die Eigenschaft **Includes erzwingen \(\#using\)**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedUsingFiles*>.  
  
## Siehe auch  
 [\/F\-Optionen \(Ausgabedateioptionen\)](../../build/reference/output-file-f-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)