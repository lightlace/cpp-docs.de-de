---
title: "/FR, /Fr (SBR-Datei erstellen)"
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
  - "VC.Project.VCCLWCECompilerTool.BrowseInformation"
  - "VC.Project.VCCLCompilerTool.BrowseInformation"
  - "/fr"
  - "VC.Project.VCCLCompilerTool.BrowseInformationFile"
  - "VC.Project.VCCLWCECompilerTool.BrowseInformationFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FR (Compileroption) [C++]"
  - "FR (Compileroption) [C++]"
  - "-FR (Compileroption) [C++]"
  - "Symbolische Browserinformationen"
ms.assetid: 3fd8f88b-3924-4feb-9393-287036a28896
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "corob"
manager: "ghogen"
---
# /FR, /Fr (SBR-Datei erstellen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt SBR\-Dateien.  
  
## Syntax  
  
```  
/FR[pathname[\filename]]  
/Fr[pathname[\filename]]  
```  
  
## Hinweise  
 Beim Erstellungsvorgang erstellt das Microsoft Browse Information Maintenance\-Hilfsprogramm \(BSCMAKE\) anhand dieser Dateien eine BSC\-Datei, die zur Darstellung von Browseinformationen verwendet wird.  
  
 Mit **\/FR** wird eine SBR\-Datei mit vollständigen symbolischen Informationen erstellt.  
  
 Mit **\/Fr** wird eine SBR\-Datei ohne Informationen über lokale Variablen erstellt.  
  
 Wenn Sie keinen Wert für `filename` angeben, erhält die SBR\-Datei denselben Basisnamen wie die Quelldatei.  
  
 **\/Fr** ist veraltet. Verwenden Sie stattdessen **\/FR**. Weitere Informationen hierzu finden Sie unter „Veraltete und entfernte Compileroptionen“ in [Compileroptionen nach Kategorien sortiert](../../build/reference/compiler-options-listed-by-category.md).  
  
> [!NOTE]
>  Ändern Sie nicht die Erweiterung SBR. BSCMAKE erfordert, dass die Zwischendateien diese Erweiterung haben.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Wählen Sie im Navigationsbereich die Eigenschaftenseite **C\/C\+\+**, **Browseinformationsdatei** aus.  
  
3.  Ändern Sie die Eigenschaft **Browseinformationsdatei** oder **Durchsuchen der Informationen aktivieren**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Weitere Informationen finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformation*> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformationFile*>.  
  
## Siehe auch  
 [\/F\-Optionen \(Ausgabedateioptionen\)](../../build/reference/output-file-f-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)