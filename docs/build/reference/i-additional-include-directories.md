---
title: "/I (Zus&#228;tzliche Includeverzeichnisse) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.AdditionalIncludeDirectories"
  - "VC.Project.VCCLCompilerTool.AdditionalIncludeDirectories"
  - "/I"
  - "VC.Project.VCNMakeTool.IncludeSearchPath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/I (Compileroption) [C++]"
  - "Zusätzliche Includeverzeichnisse (Compileroption)"
  - "I (Compileroption) [C++]"
  - "-I (Compileroption) [C++]"
  - "Includeverzeichnisse, Compileroption [C++]"
  - "Einrichten von Include-Verzeichnissen"
ms.assetid: 3e9add2a-5ed8-4d15-ad79-5b411e313a49
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /I (Zus&#228;tzliche Includeverzeichnisse)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fügt ein Verzeichnis zur Verzeichnisliste hinzu, in der nach Includedateien gesucht wird.  
  
## Syntax  
  
```  
/I[ ]directory  
```  
  
## Argumente  
 `directory`  
 das Verzeichnis, das zur Verzeichnisliste hinzugefügt werden soll, in der nach Includedateien gesucht wird.  
  
## Hinweise  
 Um mehrere Verzeichnisse hinzuzufügen, verwenden Sie diese Option mehrmals.  Verzeichnisse werden nur solange durchsucht, bis die angegebene Includedatei gefunden worden ist.  
  
 Sie können diese Option mit der Option "Include\-Standardpfad ignorieren" \([\/X \(Standardincludepfade ignorieren\)](../../build/reference/x-ignore-standard-include-paths.md)\) verwenden.  
  
 Der Compiler durchsucht die Verzeichnisse in folgender Reihenfolge:  
  
1.  Verzeichnisse, die die Quelldatei enthalten.  
  
2.  Verzeichnisse, die mit der Option **\/I** angegeben werden, und zwar in der Reihenfolge, in der der CL\-Befehl sie antrifft.  
  
3.  Verzeichnisse, die in der Umgebungsvariablen **INCLUDE** angegeben sind.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Allgemein**.  
  
4.  Bearbeiten Sie die Eigenschaft **Zusätzliche Includeverzeichnisse**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories*>.  
  
## Beispiel  
 Mit dem folgenden Befehl wird die von **MAIN.c** angeforderte Includedatei in folgender Reihenfolge gesucht: zuerst in dem Verzeichnis, in dem sich **MAIN.c** befindet, dann im Verzeichnis **\\INCLUDE**, anschließend im Verzeichnis **\\MY\\INCLUDE** und zuletzt in den Verzeichnissen, die der Umgebungsvariablen **INCLUDE** zugeordnet sind.  
  
```  
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C  
```  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)