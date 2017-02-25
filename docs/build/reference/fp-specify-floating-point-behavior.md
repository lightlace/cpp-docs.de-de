---
title: "/fp (Festlegen des Gleitkommaverhaltens) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.floatingPointModel"
  - "VC.Project.VCCLWCECompilerTool.FloatingPointExceptions"
  - "/fp"
  - "VC.Project.VCCLWCECompilerTool.floatingPointModel"
  - "VC.Project.VCCLCompilerTool.FloatingPointExceptions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Fp (Compileroption) [C++]"
  - "-Fp (Compileroption) [C++]"
ms.assetid: 10469d6b-e68b-4268-8075-d073f4f5d57e
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# /fp (Festlegen des Gleitkommaverhaltens)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt das Gleitkommaverhalten in einer Quellcodedatei an.  
  
## Syntax  
  
```  
/fp:[precise | except[-] | fast | strict ]  
```  
  
## Flags  
 **precise**  
 Der Standardwert.  
  
 Verbessert die Konsistenz von Gleitkommatests auf Gleichheit und Ungleichheit durch Deaktivierung von Optimierungen, die die Genauigkeit von Gleitkommaberechnungen beeinflussen können. \(Für die strikte ANSI\-Konformität ist eine bestimmte Genauigkeit erforderlich.\) Standardmäßig verwendet der Compiler im Code von x86\-Architekturen die 80\-Bit\-Register des Coprozessors, um Zwischenergebnisse von Gleitkommaberechnungen zu speichern.  Damit wird die Geschwindigkeit des Programms erhöht und die Größe verringert.  Da allerdings die Berechnung mit Gleitkomma\-Datentypen durchgeführt wird, die im Speicher mit weniger als 80 Bit dargestellt werden, kann die Verwendung der zusätzlichen Bits für die Genauigkeit \(80 Bit minus der Anzahl von Bits in einem kleineren Gleitkommatyp\) in längeren Berechnungen jedoch zu inkonsistenten Ergebnissen führen.  
  
 Mit **\/fp:precise** auf x86\-Prozessoren führt der Compiler bei Variablen vom Typ `float` für Zuweisungen und Typumwandlungen eine Rundung auf die entsprechende Genauigkeit durch, und das ebenso, wenn Parameter an eine Funktion übergeben werden.  Durch diese Rundung wird gewährleistet, dass die Daten keinen höheren Stellenwert als die Kapazität ihres Typs beibehalten.  Ein mit **\/fp:precise** kompiliertes Programm kann langsamer und größer sein als eines, das ohne **\/fp:precise** kompiliert wurde.  Mit **\/fp:precise** werden systeminterne Funktionen deaktiviert und stattdessen die standardisierten Laufzeitbibliotheksroutinen verwendet.  Weitere Informationen finden Sie unter [\/Oi \(Systeminterne Funktionen erstellen\)](../../build/reference/oi-generate-intrinsic-functions.md).  
  
 Mit **\/fp:precise** wird das folgende Gleitkommaverhalten aktiviert:  
  
-   Kontraktionen, das bedeutet das Ersetzen mehrerer Operationen durch Verwendung einer zusammengesetzten Operation mit einer einzigen Rundung am Ende.  
  
-   Unzulässig sind Ausdruckoptimierungen, die für spezielle Werte \(NaN, \+unendlich, –unendlich, \+ 0, – 0\) ungültig sind.  Die Optimierungen x\-x \=\> 0, x\*0 \=\> 0, x\-0 \=\> x, x\+0 \=\> x und 0\-x \=\> \-x sind aus verschiedenen Gründen ungültig. \(Siehe IEEE 754 und C99\-Standard.\)  
  
-   Der Compiler verarbeitet Vergleichsoperationen bezüglich NaN ordnungsgemäß.  Beispielsweise ergibt x \!\= x den Wert **true**, wenn `x` gleich NaN ist und geordnete Vergleiche mit NaN eine Ausnahme auslösen.  
  
-   Die Auswertung des Ausdrucks folgt C99 FLT\_EVAL\_METHOD\=2 mit folgender Ausnahme: Beim Programmieren für x86\-Prozessoren wird die Genauigkeit "long double" angewendet, da die FPU auf eine Genauigkeit von 53 Bit festgelegt ist.  
  
-   Die Multiplikation mit exakt 1,0 wird wird so umgewandelt, dass nur der andere Faktor verwendet wird.  x\*y\*1.0 wird umgewandelt in x\*y.  Entsprechend wird x\*1.0\*y in x\*y umgewandelt.  
  
-   Die Division durch exakt 1,0 wird so umgewandelt, dass nur der Dividend verwendet wird.  x\*y\/1.0 wird umgewandelt in x\*y.  Entsprechend wird x\/1.0\*y in x\*y umgewandelt.  
  
 Durch Verwendung von **\/fp:precise** mit [fenv\_access](../../preprocessor/fenv-access.md) ON werden einige Optimierungen deaktiviert, beispielsweise Auswertungen von Gleitkommaausdrücken zur Kompilierungszeit.  Wenn Sie beispielsweise das Rundungsverhalten mit [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) ändern und der Compiler eine Gleitkommaberechnung durchführt, wird das von Ihnen angegebene Rundungsverhalten erst angewendet, wenn `fenv_access` auf ON festgelegt ist.  
  
 Die Compileroption **\/Op** wird durch **\/fp:precise** ersetzt.  
  
 **fast**  
 Erstellt durch Lockerung der Regeln zum Optimieren von Gleitkommaoperationen meistens den schnellsten Code.  Dadurch kann der Compiler die Geschwindigkeit von Gleitkommacode optimieren, was allerdings zulasten seiner Genauigkeit und Richtigkeit geht.  Wenn **\/fp:fast** angegeben wird, kann der Compiler möglicherweise Zuweisungsanweisungen, Typenumwandlungen oder Funktionsaufrufe nicht korrekt und Zwischenausdrücke gar nicht runden.  Der Compiler ordnet möglicherweise Operationen neu an oder führt ungeachtet der Auswirkung auf Ergebnisse mit endlicher Genauigkeit algebraische Transformationen aus, z. B. durch assoziative und distributive Regeln.  Der Compiler kann die Genauigkeit von Operationen und Operanden in die einfache Genauigkeit ändern, anstatt die C\+\+\-Typerweiterungsregeln zu befolgen.  Optimierungen für gleitkommaspezifische Kontraktionen sind immer aktiviert \([fp\_contract](../../preprocessor/fp-contract.md) ist ON\).  Gleitkommaausnahmen und der Zugriff auf die FPU\-Umgebung sind deaktiviert \(**\/fp:except\-** wird impliziert und [fenv\_access](../../preprocessor/fenv-access.md) ist OFF\).  
  
 **\/fp:fast** kann nicht mit **\/fp:strict** oder **\/fp:precise** verwendet werden.  Die letzte in der Befehlszeile angegebene Option wird verwendet.  Die Festlegung von **\/fp:fast** und **\/fp:except** generiert einen Compilerfehler.  
  
 Die Angabe von [\/Za, \/Ze \(Spracherweiterungen deaktivieren\)](../../build/reference/za-ze-disable-language-extensions.md) \(ANSI\-Kompatibilität\) und **\/fp:fast** kann ein unerwartetes Verhalten verursachen.  Zum Beispiel werden Gleitkommaoperationen mit einfacher Genauigkeit möglicherweise nicht auf einfache Genauigkeit gerundet.  
  
 **except\[\-\]**  
 Verlässliches Modell für Gleitkommaausnahmen.  Ausnahmen werden sofort ausgelöst, wenn sie auftreten.  Diese Option ist standardmäßig deaktiviert.  Durch Hinzufügen eines Minuszeichens zur Option wird diese explizit deaktiviert.  
  
 **strict**  
 Das strengste Gleitkommamodell.  **\/fp:strict** führt dazu, dass [fp\_contract](../../preprocessor/fp-contract.md) auf OFF und [fenv\_access](../../preprocessor/fenv-access.md) auf ON festgelegt wird.  **\/fp:except** ist aktiviert und kann durch die explizite Festlegung von **\/fp:except\-** deaktiviert werden.  Wird **\/fp:strict** zusammen mit **\/fp:except\-** verwendet, wird eine strikte Gleitkommasemantik erzwungen, jedoch ohne Beachtung von Ausnahmeereignissen.  
  
## Hinweise  
 Mehrere **\/fp**\-Optionen können in der gleichen Kompilierung angegeben werden.  
  
 Informationen zum Steuern des Gleitkommaverhaltens für eine Funktion werden im Zusammenhang mit dem [](../../preprocessor/float-control.md "float_control")\-Pragma erläutert.  Dies überschreibt die Einstellung des **\/fp**\-Compilers.  Als gutes Entwicklungsverfahren wird empfohlen, das lokale Gleitkommaverhalten zu speichern und wiederherzustellen:  
  
```css  
#pragma float_control(precise, on, push)  
// Code that uses /fp:precise mode  
#pragma float_control(pop)  
```  
  
 Die meisten Gleitkommaoptimierungen für die Pragmas **\/fp:strict**, **\/fp:except** \(sowie zugehörige Pragmas\) und `fp_contract` sind abhängig vom Computer.  **\/fp:strict** und **\/fp:except** sind mit **\/clr** nicht kompatibel.  
  
 **\/fp:precise** sollte den meisten Gleitkommaanforderungen einer Anwendung genügen.  Gegebenenfalls können Sie **\/fp:except** und **\/fp:strict** verwenden, was jedoch zu einer Verringerung der Leistung führen kann.  Liegt die Priorität auf der Leistung, sollten Sie **\/fp:fast** verwenden.  
  
 **\/fp:strict**, **\/fp:fast** und **\/fp:precise** sind Modi zur Festlegung der Genauigkeit \(Korrektheit\).  Es kann jeweils nur ein Modus aktiv sein.  Sind sowohl **\/fp:strict** als auch **\/fp:precise** angegeben, wird vom Compiler der Modus verwendet, der zuletzt verarbeitet wurde.  Es ist nicht möglich, sowohl **\/fp:strict** als auch **\/fp:fast** anzugeben.  
  
 Weitere Informationen finden Sie unter [Microsoft Visual C\+\+ Floating\-Point Optimization](http://msdn.microsoft.com/library/aa289157.aspx).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Erweitern Sie den Knoten **C\/C\+\+**.  
  
4.  Wählen Sie die Eigenschaftenseite **Codegenerierung** aus.  
  
5.  Ändern Sie die Eigenschaft **Gleitkommamodell**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.floatingPointModel*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Microsoft Visual C\+\+\-Gleitkommaoptimierung](http://msdn.microsoft.com/library/aa289157.aspx)