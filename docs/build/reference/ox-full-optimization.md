---
title: "/Ox (Komplette Optimierung)"
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
  - "VC.Project.VCCLCompilerTool.ToolOptimization"
  - "/ox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Ox (Compileroption) [C++]"
  - "Schneller Code"
  - "Vollständige Optimierung"
  - "Ox (Compileroption) [C++]"
  - "-Ox (Compileroption) [C++]"
ms.assetid: 3ad7c30b-c615-428c-b1d0-2e024f81c760
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# /Ox (Komplette Optimierung)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Compileroption **\/Ox** erzeugt Code, bei dem eine möglichst hohe Ausführungsgeschwindigkeit bei ggf. größerem Speicherbedarf für den Code bevorzugt wird.  
  
## Syntax  
  
```  
/Ox  
```  
  
## Hinweise  
 Die Compileroption **\/Ox** entspricht einer Angabe der folgenden Optionen:  
  
-   [\/Ob \(Inlinefunktionserweiterung\)](../../build/reference/ob-inline-function-expansion.md), wobei der Optionsparameter 2 \(**\/Ob2**\) ist.  
  
-   [\/Og \(Globale Optimierungen\)](../../build/reference/og-global-optimizations.md)  
  
-   [\/Oi \(Systeminterne Funktionen erstellen\)](../../build/reference/oi-generate-intrinsic-functions.md)  
  
-   [\/Ot \(Schnellen Code bevorzugen\)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)  
  
-   [\/Oy \(Framezeiger unterdrücken\)](../../build/reference/oy-frame-pointer-omission.md)  
  
 **\/Ox** schließt sich gegenseitig aus mit:  
  
-   [\/O1 \(Größe minimieren\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)  
  
-   [\/O2 \(Geschwindigkeit maximieren\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)  
  
-   [\/Od \(Deaktivieren \(Debuggen\)\)](../../build/reference/od-disable-debug.md)  
  
 Die Compileroption **\/Ox** aktiviert außerdem die Optimierung benannter Rückgabewerte, durch die der Kopierkonstruktor und \-destruktor eines stapelbasierten Rückgabewerts eliminiert werden.  Weitere Informationen finden Sie unter [\/O1, \/O2 \(Größe minimieren, Geschwindigkeit maximieren\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md).  
  
 Sie können die Compileroption **\/Ox** weglassen, wenn Sie **\/Oxs** angeben, da diese Option die Compileroptionen **\/Ox** und [\/Os \(Kleinen Code bevorzugen\)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) kombiniert.  Bei der Kombination beider Optionen wird eine kleinere Codegröße bevorzugt.  
  
 Allgemein können Sie [\/O2 \(Geschwindigkeit maximieren\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) anstelle von **\/Ox** und [\/O1 \(Größe minimieren\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) anstelle von **\/Oxs** angeben.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Optimierung**.  
  
4.  Ändern Sie die Eigenschaft **Optimierung**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization*>.  
  
## Siehe auch  
 [\/O\-Optionen \(Code optimieren\)](../../build/reference/o-options-optimize-code.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)