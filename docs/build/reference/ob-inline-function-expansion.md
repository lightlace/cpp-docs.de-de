---
title: "/Ob (Inlinefunktionserweiterung) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.InlineFunctionExpansion"
  - "VC.Project.VCCLCompilerTool.InlineFunctionExpansion"
  - "/ob"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Ob (Compileroption) [C++]"
  - "/Ob0 (Compileroption) [C++]"
  - "/Ob1 (Compileroption) [C++]"
  - "/Ob2 (Compileroption) [C++]"
  - "Jede geeignete Compileroption [C++]"
  - "disable (Compileroption) [C++]"
  - "Inline-Erweiterung, Compileroption"
  - "Inlinefunktionen, Funktionserweiterung (Compileroption) [C++]"
  - "Ob (Compileroption) [C++]"
  - "-Ob (Compileroption) [C++]"
  - "Ob0 (Compileroption) [C++]"
  - "-Ob0 (Compileroption) [C++]"
  - "Ob1 (Compileroption) [C++]"
  - "-Ob1 (Compileroption) [C++]"
  - "Ob2 (Compileroption) [C++]"
  - "-Ob2 (Compileroption) [C++]"
  - "only __inline (Compileroption) [C++]"
ms.assetid: f134e6df-e939-4980-a01d-47425dbc562a
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# /Ob (Inlinefunktionserweiterung)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Steuert die Inlineerweiterung von Funktionen.  
  
## Syntax  
  
```  
/Ob{0|1|2}  
```  
  
## Argumente  
 **0**  
 Deaktiviert Inline\-Erweiterungen.  Standardmäßig erfolgen Erweiterungen aufgrund von Compilerentscheidungen bei allen Funktionen, was häufig als *automatisches Inlining* bezeichnet wird.  
  
 **1**  
 Die Erweiterung wird nur für Funktionen zugelassen, die als [inline](../../misc/inline-inline-forceinline.md), [\_\_inline](../../misc/inline-inline-forceinline.md), oder [\_\_forceinline](../../misc/inline-inline-forceinline.md) markiert oder in einer C\+\+\-Memberfunktion in einer Klassendeklaration definiert sind.  
  
 **2**  
 Der Standardwert.  Ermöglicht die Erweiterung von Funktionen, die als `inline`, `__inline` oder `__forceinline` gekennzeichnet sind, sowie aller anderen Funktionen, für die sich der Compiler entscheidet.  
  
 **\/Ob2** ist wirksam, wenn [\/O1, \/O2 \(Größe minimieren, Geschwindigkeit maximieren\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) oder [\/Ox \(Komplette Optimierung\)](../../build/reference/ox-full-optimization.md) verwendet wird.  
  
 Diese Option setzt voraus, dass Sie Optimierungen mithilfe von **\/O1**, **\/O2**, **\/Ox** oder **\/Og** aktivieren.  
  
## Hinweise  
 Der Compiler behandelt die Inlineerweiterungsoptionen und \-Schlüsselwörter als Vorschläge.  Es gibt keine Garantie dafür, dass eine bestimmte Funktion inline erweitert wird.  Sie können die Inlineerweiterung deaktivieren, Sie können den Compiler aber nicht dazu zwingen, für eine bestimmte Funktion Inlining auszuführen, auch nicht mithilfe des Schlüsselworts `__forceinline`.  
  
 Sie können die Anweisung `#pragma` [auto\_inline](../../preprocessor/auto-inline.md) verwenden, um Funktionen aus der Gruppe der Kandidaten für die Inlineerweiterung auszuschließen.  Mehr dazu finden Sie auch bei der Anweisung `#pragma` [intrinsic](../../preprocessor/intrinsic.md).  
  
> [!NOTE]
>  Informationen, die bei Testläufen für die Profilerstellung erfasst wurden, überschreiben Optimierungen, die sonst bei Angabe von **\/Ob**, **\/Os** oder **\/Ot** aktiv wären.  Weitere Informationen finden Sie unter [Profilgesteuerte Optimierungen \(PGO\)](../../build/reference/profile-guided-optimizations.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Details finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie **Konfigurationseigenschaften**, **C\/C\+\+**, und wählen Sie **Optimierung** aus.  
  
3.  Ändern der Eigenschaft **Inlinefunktionserweiterung**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.InlineFunctionExpansion*>.  
  
## Siehe auch  
 [\/O\-Optionen \(Code optimieren\)](../../build/reference/o-options-optimize-code.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)