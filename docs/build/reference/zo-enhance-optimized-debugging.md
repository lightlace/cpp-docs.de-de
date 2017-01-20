---
title: "/Zo (erweitertes optimiertes Debugging)"
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
  - "-Zo"
  - "/Zo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zo Compileroption [C++]"
  - "Zo Compileroption [C++]"
  - "-Zo Compileroption [C++]"
ms.assetid: eea8d89a-7fe0-4fe1-86b2-7689bbebbd7f
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# /Zo (erweitertes optimiertes Debugging)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Generieren Sie erweiterte Debuginformationen für optimierten Code in Nicht\-Debugbuilds.  
  
## Syntax  
  
```cpp  
/Zo[-]  
```  
  
## Hinweise  
 Der **\/Zo**\-Compilerschalter generiert erweiterte Debuginformationen für optimierten Code.  Bei der Optimierung können Register für lokale Variablen verwendet, Code neu angeordnet, Schleifen vektorisiert und Inline\-Funktionsaufrufe verwendet werden.  Diese Optimierungen können die Beziehung zwischen dem Quellcode und dem kompilierten Objektcode verbergen.  Der **\/Zo**\-Schalter weist den Compiler an, zusätzliche Debuginformationen für lokale Variablen und Inlinefunktionen zu generieren.  Verwenden Sie diese Informationen, um Variablen in den Fenstern **Auto**, **Lokal** und **Überwachen** anzuzeigen, wenn Sie den optimierten Code in Visual Studio\-Debugger schrittweise durchlaufen.  Darüber hinaus können Stapelüberwachungen Inlinefunktionen im WinDBG\-Debugger anzeigen.  Für Debug\-Builds mit deaktivierter Optimierung \([\/Od](../../build/reference/od-disable-debug.md)\) müssen die zusätzlichen Debuginformationen nicht generiert werden, wenn **\/Zo** angegeben ist.  Verwenden Sie den **\/Zo**\-Schalter, um die Releasekonfigurationen mit aktivierter Optimierung zu debuggen.  Weitere Informationen zu Optimierungsschaltern finden Sie unter [\/O\-Optionen \(Code optimieren\)](../../build/reference/o-options-optimize-code.md).  Die **\/Zo**\-Option ist standardmäßig in Visual Studio 2015 aktiviert, wenn Sie Debuginformationen mit **\/Zi** oder **\/Z7** angeben.  Geben Sie **\/Zo\-** an, um diese Compileroption explizit zu deaktivieren.  
  
 Der **\/Zo**\-Schalter ist in Visual Studio 2013 Update 3 verfügbar und ersetzt den zuvor nicht dokumentierten **\/d2Zi\+**\-Schalter.  
  
### So legen Sie die \/Zo\-Compileroption in Visual Studio fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** für das Projekt.  Weitere Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Wählen Sie den Ordner **Konfigurationseigenschaften**, **C\/C\+\+** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Befehlszeile** aus.  
  
4.  Ändern Sie die Eigenschaft **Zusätzliche Optionen** so, dass `/Zo` eingeschlossen wird, und wählen Sie dann **OK**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [\/O\-Optionen \(Code optimieren\)](../../build/reference/o-options-optimize-code.md)   
 [\/Z7, \/Zi, \/ZI \(Debuginformationsformat\)](../../build/reference/z7-zi-zi-debug-information-format.md)   
 ["Bearbeiten und Fortfahren"](../Topic/Edit%20and%20Continue.md)