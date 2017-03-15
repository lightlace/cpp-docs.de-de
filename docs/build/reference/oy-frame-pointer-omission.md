---
title: "/Oy (Framezeiger unterdr&#252;cken) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.OmitFramePointers"
  - "/oy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Oy (Compileroption) [C++]"
  - "Rahmenzeigerauslassung (Compileroption) [C++]"
  - "Framezeiger unterdrücken"
  - "Oy (Compileroption) [C++]"
  - "-Oy (Compileroption) [C++]"
  - "Stapelrahmenzeiger (Compileroption) [C++]"
  - "Unterdrücken der Framezeigererstellung"
ms.assetid: c451da86-5297-4c5a-92bc-561d41379853
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# /Oy (Framezeiger unterdr&#252;cken)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unterdrückt die Erstellung von Framezeigern im Anrufstapel.  
  
## Syntax  
  
```  
/Oy[-]  
```  
  
## Hinweise  
 Durch diese Option werden Funktionsaufrufe beschleunigt, da keine Framezeiger eingerichtet und entfernt werden müssen.  Außerdem wird ein weiteres Register \(EBP bei Intel 386\- oder neueren Prozessoren\) zum Speichern häufig verwendeter Variablen und untergeordneter Ausdrücke freigegeben.  
  
 **\/Oy** aktiviert und **\/Oy\-** deaktiviert die Unterdrückung des Framezeigers. **\/Oy** ist nur in x86\-Compilern verfügbar.  
  
 Wenn der Code eine EBP\-basierte Adressierung erfordert, können Sie die Option **\/Oy–** im Anschluss an die Option **\/Ox** angeben oder [optimize](../../preprocessor/optimize.md) zusammen mit den Argumenten **y** und **off** verwenden, um die EBP\-basierte Adressierung zu optimieren.  Der Compiler erkennt in den meisten Situationen, wenn eine EBP\-basierte Adressierung erforderlich ist \(beispielsweise in der `_alloca`\-und der `setjmp`\-Funktion sowie bei strukturierter Ausnahmebehandlung\).  
  
 Die Optionen [\/Ox \(Komplette Optimierung\)](../../build/reference/ox-full-optimization.md) und [\/O1, \/O2 \(Größe minimieren, Geschwindigkeit maximieren\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) implizieren **\/Oy**.  Durch Angabe von **\/Oy–** im Anschluss an eine der Optionen **\/Ox**, **\/O1** oder **\/O2** wird **\/Oy** deaktiviert, sei es explizit oder implizit.  
  
 Die Compileroption **\/Oy** erschwert die Verwendung des Debuggers, da der Compiler hierdurch Framezeigerinformationen unterdrückt.  Wenn Sie die Compileroption "debug" \([\/Z7, \/Zi, \/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)\) festlegen, sollten Sie die Option **\/Oy\-** in Anschluss an alle anderen Optimierungsoptionen angeben.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Optimierung**.  
  
4.  Ändern Sie die Eigenschaft **Framezeiger unterdrücken**.  Durch diese Eigenschaft wird nur die Option **\/Oy** hinzugefügt oder entfernt.  Wenn Sie die Option **\/Oy\-** hinzufügen möchten, klicken Sie auf **Befehlszeile**, und ändern Sie die Option **Zusätzliche Optionen**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers*>.  
  
## Siehe auch  
 [\/O\-Optionen \(Code optimieren\)](../../build/reference/o-options-optimize-code.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)