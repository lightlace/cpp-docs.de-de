---
title: "/arch (ARM) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 4f1406ff-f174-487c-a126-8ab06cf447c1
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# /arch (ARM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt die Architektur für die Codegenerierung auf ARM an.  Siehe auch [\/arch \(x86\)](../../build/reference/arch-x86.md) und [\/arch \(x64\)](../../build/reference/arch-x64.md).  
  
## Syntax  
  
```  
/arch:[ARMv7VE|VFPv4]  
```  
  
## Argumente  
 **\/arch:ARMv7VE**  
 Ermöglicht die Verwendung von Anweisungen für ARMv7VE\-Virtualisierungserweiterungen.  
  
 **\/arch:VFPv4**  
 Ermöglicht die Verwendung von ARM\-VFPv4\-Anweisungen.  Wenn diese Option nicht angegeben wird, ist VFPv3 die Standardeinstellung.  
  
## Hinweise  
 Das `_M_ARM_FP` \-Makro gibt an, welche **\/arch**\-Compileroption ggf. verwendet wurde.  Weitere Informationen finden Sie unter [Vordefinierte Makros](../../preprocessor/predefined-macros.md).  
  
 Wenn Sie Kompilierungsvorgänge mit [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) ausführen, hat **\/arch** keine Auswirkungen auf die Codegenerierung für verwaltete Funktionen.  **\/arch** wirkt sich nur auf die Codegenerierung für systemeigene Funktionen aus.  
  
### Zum Festlegen der \/arch:ARMv7VE oder \/arch:VFPv4\-Compileroption in Visual Studio  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** für das Projekt.  Weitere Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Wählen Sie den Ordner **C\/C\+\+** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Befehlszeile** aus.  
  
4.  Fügen Sie im Feld **Zusätzliche Optionen** `/arch:ARMv7VE` oder `/arch:VFPv4` hinzu.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet*>.  
  
## Siehe auch  
 [\/arch \(Minimale CPU\-Architektur\)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)