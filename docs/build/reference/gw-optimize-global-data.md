---
title: "/Gw (Optimieren globaler Daten) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Gw"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gw (Compileroption) [C++]"
  - "-Gw (Compileroption) [C++]"
ms.assetid: 6f90f4e9-5eb8-4c47-886e-631278a5a4a9
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /Gw (Optimieren globaler Daten)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fasst globale Daten zur Optimierung in COMDAT\-Abschnitten zusammen.  
  
## Syntax  
  
```  
/Gw[-]  
```  
  
## Hinweise  
 Die **\/Gw**\-Option bewirkt, dass der Compiler globale Daten in einzelnen COMDAT\-Abschnitten verpackt.  Standardmäßig ist **\/Gw** deaktiviert und muss explizit aktiviert werden.  Zur expliziten Deaktivierung verwenden Sie **\/Gw\-**.  Wenn sowohl **\/Gw** als auch [\/GL](../../build/reference/gl-whole-program-optimization.md) aktiviert ist, verwendet der Linker die programmübergreifende Optimierung, um COMDAT\-Abschnitte über mehrere Objektdateien hinweg zu vergleichen, wobei nicht referenzierte globale Daten ausgeschlossen oder identische schreibgeschützte globale Daten zusammengeführt werden.  Dies kann die Größe der resultierenden binären ausführbaren Datei deutlich reduzieren.  
  
 Wenn Sie getrennt kompilieren und binden, können Sie die Linkeroption [\/OPT:REF](../../build/reference/opt-optimizations.md) verwenden, um aus der ausführbaren Datei die nicht referenzierten globalen Daten in Objektdateien auszuschließen, die mit der **\/Gw**\-Option kompiliert wurden.  
  
 Sie können auch die Linkeroptionen [\/OPT:ICF](../../build/reference/opt-optimizations.md) und [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md) verwenden, um in der ausführbaren Datei alle identischen globalen schreibgeschützten Daten zusammenzuführen, die aus Objektdateien stammen, die mit der **\/Gw**\-Option kompiliert wurden.  
  
 Weitere Informationen finden Sie unter [Introducing ‘\/Gw’ Compiler Switch](http://blogs.msdn.com/b/vcblog/archive/2013/09/11/introducing-gw-compiler-switch.aspx) im Visual C\+\+\-Team\-Blog.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie den Ordner **C\/C\+\+** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Befehlszeile** aus.  
  
4.  Ändern Sie die Eigenschaft **Zusätzliche Optionen**, damit sie **\/Gw** einschließt, und wählen Sie dann **OK** aus.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)