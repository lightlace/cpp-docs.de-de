---
title: "/Oi (Systeminterne Funktionen erstellen)"
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
  - "VC.Project.VCCLCompilerTool.EnableIntrinsicFunctions"
  - "/oi"
  - "VC.Project.VCCLWCECompilerTool.EnableIntrinsicFunctions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Oi (Compileroption) [C++]"
  - "Systeminterne Funktionen generieren (Compileroption) [C++]"
  - "Systeminterne Funktionen, Generieren"
  - "Oi (Compileroption) [C++]"
  - "-Oi (Compileroption) [C++]"
ms.assetid: fa4a3bf6-0ed8-481b-91c0-add7636132b4
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# /Oi (Systeminterne Funktionen erstellen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Option ersetzt einige Funktionsaufrufe durch systeminterne oder sonstige spezielle Formen der Funktion, die dazu beitragen, dass die Arbeitsgeschwindigkeit der Anwendung erhöht wird.  
  
## Syntax  
  
```  
/Oi[-]  
```  
  
## Hinweise  
 Programme, die systeminterne Funktionen verwenden, sind von verkürzter Laufzeit geprägt, weil der Verwaltungsaufwand von Funktionsaufrufen entfällt, aber sie können wegen des zusätzlich erstellten Codes größer sein.  
  
 Weitere Informationen darüber, welche Funktionen über systeminterne Formen verfügen, finden Sie unter [intrinsic](../../preprocessor/intrinsic.md).  
  
 **\/Oi** ist lediglich eine Anforderung an den Compiler, bestimmte Funktionsaufrufe mit systeminternen Funktionen zu ersetzen. Die Funktion wird möglicherweise vom Compiler aufgerufen \(und nicht durch eine systeminterne ersetzt\), wenn dadurch eine bessere Leistung erzielt wird.  
  
 **x86\-spezifisch**  
  
 Da die systeminternen Gleitkommafunktionen die Eingabewerte nicht gründlich prüfen, arbeiten sie in beschränkten Eingabebereichen und haben eine andere Ausnahmebehandlung und andere Grenzwertbedingungen als die gleichnamigen Bibliotheksroutinen.  Die Verwendung der echten systeminternen Formen impliziert den Verlust der Ausnahmebehandlung nach IEEE sowie den Verlust der `_matherr` und `errno`\-Funktionen. Letztere implizieren den Verlust der ANSI\-Konformität.  Die systeminternen Funktionen können jedoch Programme mit intensiven Gleitkommaberechnungen erheblich beschleunigen, und für viele Programme hat die Konformität wenig praktische Bedeutung.  
  
 Mithilfe der [Za](../../build/reference/za-ze-disable-language-extensions.md)\-Compileroption können Sie die Erzeugung echter systeminterner Gleitkommaoptionen überschreiben.  In diesem Fall werden die Funktionen als Bibliotheksfunktionen erzeugt, die die Argumente direkt an den Gleitkommachip übergeben, statt sie in den Programmstapel abzulegen.  
  
 **END x86\-spezifisch**  
  
 Sie können außerdem [intrinsic](../../preprocessor/intrinsic.md) dazu verwenden, systeminterne Funktionen zu erstellen, oder [Funktion](../../preprocessor/function-c-cpp.md), um einen Funktionsaufruf explizit zu erzwingen.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Optimierung**.  
  
4.  Ändern Sie die Eigenschaft **Systeminterne Funktionen aktivieren**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableIntrinsicFunctions*>.  
  
## Siehe auch  
 [\/O\-Optionen \(Code optimieren\)](../../build/reference/o-options-optimize-code.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Intrinsische Compilerfunktionen](../../intrinsics/compiler-intrinsics.md)