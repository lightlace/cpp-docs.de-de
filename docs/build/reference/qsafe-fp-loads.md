---
title: "/Qsafe_fp_loads | Microsoft Docs"
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
ms.assetid: 2b2ce52d-ba57-4bd3-a739-47a7f8bfaba9
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /Qsafe_fp_loads
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erfordert ganzzahlige Verschiebungsanweisungen für Gleitkommawerte und deaktiviert bestimmte Gleitkomma\-Ladeoptimierungen.  
  
## Syntax  
  
```  
/Qsafe_fp_loads  
```  
  
## Hinweise  
 **\/Qsafe\_fp\_loads** ist nur in Compilern für x86 verfügbar, nicht in Compilern für x64 oder ARM.  
  
 **\/Qsafe\_fp\_loads** zwingt den Compiler, ganzzahlige Verschiebungsanweisungen anstelle der Gleitkomma\-Verschiebungsanweisungen verwenden, um Daten zwischen Arbeitsspeicher und MMX\-Registern zu verschieben.  Diese Option deaktiviert auch Registerladeoptimierung für Gleitkommawerte, die in mehreren Kontrollpfaden geladen werden können, wenn der Wert \(beispielsweise NaN\) beim Laden eine Ausnahme verursacht.  
  
 Diese Option wird durch [\/fp:except](../../build/reference/fp-specify-floating-point-behavior.md) überschrieben.  **\/Qsafe\_fp\_loads** gibt eine Teilmenge des Compilerverhaltens an, das von **\/fp:except** angegeben wird.  
  
 **\/Qsafe\_fp\_loads** ist mit [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) und [\/fp:fast](../../build/reference/fp-specify-floating-point-behavior.md) nicht kompatibel.  Weitere Informationen über Gleitkomma\-Compileroptionen finden Sie unter [\/fp \(Festlegen des Gleitkommaverhaltens\)](../../build/reference/fp-specify-floating-point-behavior.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Wählen Sie den Ordner **C\/C\+\+** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Befehlszeile** aus.  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [\/Q\-Optionen \(Operationen auf niedriger Ebene\)](../../build/reference/q-options-low-level-operations.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)