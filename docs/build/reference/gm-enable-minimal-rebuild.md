---
title: "/Gm (Minimale Neuerstellung aktivieren) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.MinimalRebuild"
  - "/Gm"
  - "/FD"
  - "VC.Project.VCCLWCECompilerTool.MinimalRebuild"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gm (Compileroption) [C++]"
  - "Aktivieren der minimalen Neuerstellung (Compileroption) [C++]"
  - "Gm (Compileroption) [C++]"
  - "-Gm (Compileroption) [C++]"
  - "Minimale Neuerstellung"
ms.assetid: d8869ce0-d2ea-40eb-8dae-6d2cdb61dd59
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /Gm (Minimale Neuerstellung aktivieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Aktiviert die minimale Neuerstellung, die bestimmt, ob C\+\+\-Quelldateien, die geänderte C\+\+\-Klassendefinitionen enthalten \(gespeichert in Headerdateien \(.h\)\) neu kompiliert werden müssen.  
  
## Syntax  
  
```  
/Gm  
```  
  
## Hinweise  
 Der Compiler speichert Abhängigkeitsinformationen zwischen Quelldateien und Klassendefinitionen während der ersten Kompilierung in der .idb\-Datei des Projekts.  \(Abhängigkeitsinformationen teilen mit, welche Quelldatei von welcher Klassendefinition abhängt und in welcher .h\-Datei sich die Definition befindet.\) Nachfolgende Kompilierungen verwenden die in der .idb\-Datei gespeicherten Informationen, um zu bestimmen, ob eine Quelldatei kompiliert werden muss, selbst wenn sie eine geänderte .h\-Datei enthält.  
  
> [!NOTE]
>  Die minimale Neuerstellung basiert auf Klassendefinitionen, die sich zwischen Includedateien nicht ändern.  Klassendefinitionen müssen für ein Projekt global sein \(es sollte nur eine Definition für eine bestimmte Klasse vorhanden sein\), da die Abhängigkeitsinformationen in der .idb\-Datei für das gesamte Projekt erstellt werden.  Wenn Sie mehr als eine Definition für eine Klasse in Ihrem Projekt haben, deaktivieren Sie die minimale Neuerstellung.  
  
 Da der Incremental Linker die in .obj\-Dateien enthaltenen Windows\-Metadaten unter Verwendung der Option [\/ZW \(Windows\-Runtime\-Kompilierung\)](../../build/reference/zw-windows-runtime-compilation.md) nicht unterstützt, ist die Option **\/Gm** inkompatibel mit **\/ZW**.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Codegenerierung**.  
  
4.  Ändern Sie die Eigenschaft **Minimale Neuerstellung aktivieren**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.MinimalRebuild*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)