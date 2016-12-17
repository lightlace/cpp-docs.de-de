---
title: "/Qfast_transcendentals (Erzwingen von schnellen Transzendenten)"
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
  - "/Qfast_transcendentals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Qfast_transcendentals"
  - "Erzwingen von schnellen Transzendenten"
ms.assetid: 4de24bd1-38e6-49d4-9a05-04c9937d24ac
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# /Qfast_transcendentals (Erzwingen von schnellen Transzendenten)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Generiert Inlinecode für transzendente Funktionen.  
  
## Syntax  
  
```  
/Qfast_transcendentals  
```  
  
## Hinweise  
 Diese Compileroption erzwingt die Konvertierung von transzendenten Funktionen in Inlinecode, um die Ausführungsgeschwindigkeit zu erhöhen.  Diese Option hat nur Auswirkungen, wenn sie zusammen mit **\/fp:except** oder **\/fp:precise** verwendet wird.  Die Generierung von Inlinecode für transzendente Funktionen ist unter **\/fp:fast** bereits das Standardverhalten.  
  
 Diese Option ist mit **\/fp:strict** nicht kompatibel.  Weitere Informationen über Gleitkomma\-Compileroptionen finden Sie unter [\/fp \(Festlegen des Gleitkommaverhaltens\)](../../build/reference/fp-specify-floating-point-behavior.md).  
  
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