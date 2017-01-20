---
title: "/Fo (Name der Objektdatei)"
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
  - "/Fo"
  - "VC.Project.VCCLCompilerTool.ObjectFile"
  - "VC.Project.VCCLWCECompilerTool.ObjectFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Fo (Compileroption) [C++]"
  - "Fo (Compileroption) [C++]"
  - "-Fo (Compileroption) [C++]"
  - "Objektdateien, Benennen"
ms.assetid: 0e6d593e-4e7f-4990-9e6e-92e1dcbcf6e6
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# /Fo (Name der Objektdatei)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt einen Namen oder ein Verzeichnis für die Objektdatei \(OBJ\-Datei\) an, der bzw. das anstelle des Standardwerts verwendet wird.  
  
## Syntax  
  
```  
/Fopathname  
```  
  
## Hinweise  
 Ohne die Option verwendet die Objektdatei den Basisnamen der Quelldatei und die Erweiterung **.obj**.  Name und Erweiterung können frei gewählt werden, aber es wird empfohlen, die Erweiterung **.obj** zu verwenden.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Ausgabedateien**.  
  
4.  Ändern Sie die Eigenschaft **Objektdateiname**.  In der Entwicklungsumgebung muss die Objektdatei die Erweiterung .obj haben.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ObjectFile*>.  
  
## Beispiel  
 Mit der folgenden Befehlszeile wird eine Objektdatei mit dem Namen **THIS.obj** in dem vorhandenen Verzeichnis **\\OBJECT** auf Laufwerk **B** erstellt.  
  
```  
CL /FoB:\OBJECT\ THIS.C  
```  
  
## Siehe auch  
 [\/F\-Optionen \(Ausgabedateioptionen\)](../../build/reference/output-file-f-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)