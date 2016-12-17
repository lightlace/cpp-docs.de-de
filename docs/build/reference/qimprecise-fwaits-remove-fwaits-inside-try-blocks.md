---
title: "/Qimprecise_fwaits (Entfernen von fwaits in Try-Bl&#246;cken)"
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
  - "/Qimprecise_fwaits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Qimprecise_fwaits-Compileroption (C++)"
  - "-Qimprecise_fwaits-Compileroption (C++)"
ms.assetid: b1501f21-7e08-4fea-95e8-176ec03a635b
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# /Qimprecise_fwaits (Entfernen von fwaits in Try-Bl&#246;cken)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Entfernt die `fwait`\-Befehle in `try`\-Blöcken, wenn Sie die [\/fp:except](../../build/reference/fp-specify-floating-point-behavior.md)\-Compileroption verwenden.  
  
## Syntax  
  
```  
/Qimprecise_fwaits  
```  
  
## Hinweise  
 Diese Option hat keine Auswirkungen, wenn **\/fp:except** nicht auch angegeben wird.  Wenn Sie die **\/fp:except**\-Option angeben, fügt der Compiler einen `fwait`\-Befehl um jede Codezeile in einem `try`\-Block ein.  Auf diese Weise kann der Compiler die spezifische Codezeile identifizieren, die eine Ausnahme erzeugt.  **\/Qimprecise\_fwaits** entfernt interne `fwait`\-Anweisungen und lässt nur die Waits um den `try`\-Block stehen.  Damit wird die Leistung verbessert, aber der Compiler kann nur angeben, welcher `try`\-Block eine Ausnahme verursacht. Die Zeile kann nicht angegeben werden.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [\/Q\-Optionen \(Operationen auf niedriger Ebene\)](../../build/reference/q-options-low-level-operations.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)