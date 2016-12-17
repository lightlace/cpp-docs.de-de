---
title: "/arch (x86)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 9dd5a75d-06e4-4674-aade-33228486078d
caps.latest.revision: 33
caps.handback.revision: "33"
ms.author: "corob"
manager: "ghogen"
---
# /arch (x86)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt die Architektur für die Codegenerierung auf x86 an.  Siehe auch [\/arch \(x64\)](../../build/reference/arch-x64.md) und [\/arch \(ARM\)](../../build/reference/arch-arm.md).  
  
## Syntax  
  
```  
/arch:[IA32|SSE|SSE2|AVX|AVX2]  
```  
  
## Argumente  
 **\/arch:IA32**  
 Gibt keine erweiterten Anweisungen an, und gibt außerdem x87 für Gleitkommaberechnungen an.  
  
 **\/arch:SSE**  
 Aktiviert die Verwendung von SSE\-Anweisungen.  
  
 **\/arch:SSE2**  
 Aktiviert die Verwendung von SSE2\-Anweisungen.  Dies ist die Standardanweisung auf x86\-Plattformen, wenn keine **\/arch**\-Option angegeben wird.  
  
 **\/arch:AVX**  
 Aktiviert die Verwendung von Intel Advanced Vector Extensions\-Anweisungen.  
  
 **\/arch:AVX2**  
 Aktiviert die Verwendung von Intel Advanced Vector Extensions 2\-Anweisungen.  
  
## Hinweise  
 Die SSE\- und SSE2\-Anweisungen werden in verschiedenen Intel\- und AMD\-Prozessoren verwendet.  Die AVX\-Anweisungen gibt es bei Intel Sandy Bridge\- und AMD Bulldozer\-Prozessoren.  AVX2\-Anweisungen werden von Intel Haswell\- und Broadwell\-Prozessoren sowie AMD Excavator\-basierten Prozessoren unterstützt.  
  
 Die Makros `_M_IX86_FP`, `__AVX__` und `__AVX2__` geben an, welche **\/arch**\-Compileroption ggf. verwendet wurde.  Weitere Informationen finden Sie unter [Vordefinierte Makros](../../preprocessor/predefined-macros.md).  Die Option **\/arch:AVX2** und das Makro `__AVX2__` wurden in Visual Studio 2013 Update 2 Version 12.0.34567.1 eingeführt.  
  
 Der Optimierer wählt aus, wann und wie die SSE\- und SSE2\-Anweisungen bei Angabe von **\/arch** verwendet werden.  Er verwendet SSE\- und SSE2\-Anweisungen für einige skalare Gleitkommaberechnungen, und zwar in Fällen, in denen die Verwendung der SSE\/SSE2\-Anweisungen und \-Register Leistungsvorteile gegenüber dem x87\-Gleitkomma\-Registerstapel bietet.  Dies bedeutet, dass im Code für Gleitkommaberechnungen tatsächlich eine Kombination aus x87 und SSE\/SSE2 verwendet werden kann.  Darüber hinaus können mit **\/arch:SSE2** SSE2\-Anweisungen für einige 64\-Bit\-Ganzzahloperationen verwendet werden.  
  
 Neben den SSE\- und SSE2\-Anweisungen verwendet der Compiler weitere Anweisungen, die in den jeweiligen Prozessorrevisionen mit SSE\- und SSE2\-Unterstützung verfügbar sind.  Die CMOV\-Anweisung, die zuerst in der Pentium Pro\-Revision der Intel\-Prozessoren verwendet wurde, ist ein Beispiel hierfür.  
  
 Da der x86\-Compiler Code generiert, der Anweisungen SSE2\-Anweisungen standardmäßig verwendet, müssen Sie **\/arch:IA32** angeben, um die Generierung von SSE\- und SSE2\-Anweisungen für x86\-Prozessoren zu deaktivieren.  
  
 **\/arch** wirkt sich nur auf die Codegenerierung für systemeigene Funktionen aus.  Wenn Sie Kompilierungsvorgänge mit [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) ausführen, hat **\/arch** keine Auswirkungen auf die Codegenerierung für verwaltete Funktionen.  
  
 **\/arch** und [\/QIfist](../../build/reference/qifist-suppress-ftol.md) können nicht für dieselbe Kompiliereinheit verwendet werden.  Insbesondere wenn Sie das FP\-Steuerwort nicht mithilfe von `_controlfp` ändern, legt der Laufzeitstartcode das x87 FPU\-Steuerwort\-Genauigkeitskontrollfeld auf 53 Bits fest.  Daher verwendet jeder Vorgang vom Typ "float" und "double" in einem Ausdruck einen 53\-Bit\-Signifikanden und einen 15\-Bit\-Exponenten.  Alle SSE\-Operationen mit einfacher Genauigkeit verwenden jedoch 24\-Bit\-Signifikanden und einen 8\-Bit\-Exponenten, und SSE2\-Operationen mit doppelter Genauigkeit verwenden 53\-Bit\-Signifikanden und einen 11\-Bit\-Exponenten.  Weitere Informationen finden Sie unter [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md).  Diese Unterschiede können in einer Ausdrucksbaumstruktur auftreten. Dies gilt jedoch nicht, wenn nach jedem untergeordneten Ausdruck eine Benutzerzuordnung stattfindet.  Nehmen wir einmal die folgende Situation:  
  
```c  
  
r = f1 * f2 + d;  // Different results are possible on SSE/SSE2.  
```  
  
 Gegenüber:  
  
```c  
  
t = f1 * f2;   // Do f1 * f2, round to the type of t.  
r = t + d;     // This should produce the same overall result   
               // whether x87 stack is used or SSE/SSE2 is used.  
```  
  
### So legen Sie diese Compileroption für AVX, AVX2, IA32, SSE oder SSE2 in Visual Studio fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** für das Projekt.  Weitere Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Wählen Sie den Ordner **Konfigurationseigenschaften**, **C\/C\+\+** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Codegenerierung** aus.  
  
4.  Ändern Sie die Eigenschaft **Erweitertes Anweisungsset aktivieren**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet*>.  
  
## Siehe auch  
 [\/arch \(Minimale CPU\-Architektur\)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)