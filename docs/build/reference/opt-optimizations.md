---
title: "/OPT (Optimierungen) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.OptimizeReferences"
  - "/opt"
  - "VC.Project.VCLinkerTool.OptimizeForWindows98"
  - "VC.Project.VCLinkerTool.EnableCOMDATFolding"
  - "VC.Project.VCLinkerTool.OptimizeFolding"
  - "VC.Project.VCLinkerTool.FoldingIterations"
  - "VC.Project.VCLinkerTool.OptimizeFoldingIterations"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/OPT-Linkeroption"
  - "LINK-Tool [C++], Steuern von Optimierungen"
  - "Linker [C++], Optimierungen"
  - "OPT-Linkeroption"
  - "-OPT (Linkeroption)"
  - "Optimierung, Linker"
ms.assetid: 8f229863-5f53-48a8-9478-243a647093ac
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# /OPT (Optimierungen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Steuert die Optimierungen, die während eines Builds von LINK ausgeführt werden.  
  
## Syntax  
  
```  
/OPT:{REF | NOREF}  
/OPT:{ICF[=iterations] | NOICF}  
/OPT:{LBR | NOLBR}  
```  
  
## Argumente  
 **REF** &#124; **NOREF**  
 **\/OPT:REF** löscht Funktionen und Daten, auf die nie verwiesen wird, während mithilfe von **\/OPT:NOREF** solche Funktionen und Daten beibehalten werden.  
  
 Wenn \/OFT:REF aktiviert ist, entfernt LINK unreferenzierte gepackte Funktionen und Daten.  Ein Objekt enthält Paketfunktionen und Daten \(COMDATs\), wenn es mit der Option [\/Gy](../../build/reference/gy-enable-function-level-linking.md) kompiliert worden ist.  Diese Optimierung ist als transitive COMDAT\-Eliminierung bekannt.  Standardmäßig ist **\/OPT:REF** in Nichtdebugversionen aktiviert.  Geben Sie **\/OPT:NOREF** an, um diese Standardeinstellung zu überschreiben und unreferenzierte COMDATs im Programm zu behalten.  Sie können die [\/INCLUDE](../../build/reference/include-force-symbol-references.md)\-Option verwenden, um das Entfernen eines bestimmten Symbols zu überschreiben.  
  
 Wenn **\/OPT:REF** entweder explizit oder standardmäßig aktiviert ist, wird **\/OPT:ICF** in eingeschränkter Form aktiviert, sodass lediglich identische Funktionen gefaltet werden.  Wenn Sie **\/OPT:REF**, nicht jedoch **\/OPT:ICF** festlegen möchten, geben Sie **\/OPT:REF,NOICF** oder **\/OPT:NOICF** an.  
  
 Bei Angabe von [\/DEBUG](../../build/reference/debug-generate-debug-info.md) ist **NOREF** die Standardeinstellung für **\/OPT**, und alle Funktionen werden im Image beibehalten.  Um diese Standardeinstellung zu überschreiben und einen Debugbuild zu optimieren, geben Sie **\/OPT:REF** an.  Da **\/OPT:ICF** durch **\/OPT:REF** impliziert wird, wird empfohlen, auch **\/OPT:NOICF** anzugeben, damit identische Funktionen in Debugversionen beibehalten werden.  Dadurch wird es einfacher, in Funktionen, die andernfalls gefaltet würden, Stapelüberwachungen zu lesen und Haltepunkte festzulegen.  Mit der **\/OPT:REF**\-Option wird inkrementelles Verknüpfen deaktiviert.  
  
 `const`\-Daten müssen mithilfe von [\_\_declspec\(selectany\)](../../cpp/selectany.md) ausdrücklich als COMDAT\-Daten gekennzeichnet werden.  
  
 Durch Angabe von **\/OPT:ICF** wird die **\/OPT:REF**\-Option nicht aktiviert.  
  
 **ICF\[\=**  `iterations` **\] &#124; NOICF**  
 Verwenden Sie **\/OPT:ICF\[\=**`iterations`**\]**, um eine identische COMDAT\-Faltung durchzuführen.  Redundante COMDATs können aus der Linkerausgabe entfernt werden.  Der optionale `iterations`\-Parameter gibt die Häufigkeit für das Durchlaufen der Symbole für Duplikate an.  Die Anzahl von Iterationen beträgt standardmäßig 2.  Zusätzliche Iterationen können mehr Duplikate auffinden, die bei der Faltung in vorherigen Iterationen unentdeckt blieben.  
  
 Der Linker verhält sich anders, wenn **\/OPT:REF** angegeben und somit **ICF** standardmäßig aktiv ist, als wenn **\/OPT:REF,ICF** explizit angegeben wird.  Bei der Variante von **ICF**, die nur mit **\/OPT:REF** aktiviert wird, werden keine schreibgeschützten Daten gefaltet. Das gilt auch für .rdata, .pdata und .xdata.  Dies führt zu einer geringeren Funktionsfaltung, wenn Images für [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] erstellt werden, denn die Funktionen in diesen Modulen weisen eine größere Abhängigkeit von schreibgeschützten Daten, wie beispielsweise .pdata und .xdata, auf.  Für ein vollständiges **ICF**\-Faltungsverhalten geben Sie explizit **\/OPT:ICF** an.  
  
 Verwenden Sie zum Einfügen von Funktionen in COMDATs die Compileroption **\/Gy**; wenn Sie `const`\-Daten einfügen möchten, deklarieren Sie sie als `__declspec(selectany)`.  Informationen über die Angabe von Daten zur Faltung finden Sie unter [selectany](../../cpp/selectany.md).  
  
 **ICF** ist standardmäßig aktiviert, wenn **REF** aktiviert ist.  Wenn Sie diesen Standard überschreiben möchten und **REF** angegeben ist, verwenden Sie **NOICF**.  Sie müssen **\/OPT:REF** explizit angeben, um die COMDAT\-Faltung in einer Debugversion zu aktivieren, wenn **\/OPT:ICF** nicht angegeben ist.  Da allerdings die Option **\/OPT:ICF** identische Daten oder Funktionen zusammenführen kann, kann sie die in der Stapelüberwachung angezeigten Funktionsnamen ändern.  Ferner verhindert die Option möglicherweise, dass Haltepunkte in bestimmten Funktionen festgelegt oder Daten im Debugger überprüft werden können, und Sie können auf unerwartete Funktionen stoßen, wenn Sie den Code Schritt für Schritt durchlaufen.  Daher empfiehlt sich die Verwendung von **\/OPT:ICF** in Debugversionen nur, wenn die Vorteile der Verwendung von kompaktem Code die genannten Nachteile überwiegen.  
  
> [!NOTE]
>  Die Option **\/OPT:ICF** kann bewirken, dass eine Adresse unterschiedlichen Funktionen oder schreibgeschützten Datenmembern zugewiesen wird \(`const`\-Variablen kompiliert mit **\/Gy**\); daher besteht die Gefahr, dass Programme unterbrochen werden, die Funktionen oder schreibgeschützte Datenmember mit eindeutigen Adressen benötigen.  Weitere Informationen finden Sie unter [\/Gy \(Funktionslevel\-Linking aktivieren\)](../../build/reference/gy-enable-function-level-linking.md).  
  
 **LBR** &#124; **NOLBR**  
 Die **\/OPT:LBR**\- und **\/OPT:NOLBR**\-Optionen gelten nur für ARM\-Binärdateien.  Bestimmte Verzweigungsanweisungen von ARM\-Prozessoren haben einen begrenzten Bereich. Wenn der Linker einen Sprung zu einer außerhalb des Gültigkeitsbereichs liegenden Adresse erkennt, ersetzt er die Zieladresse der Verzweigungsanweisung durch die Adresse einer "Codeinsel", die eine Verzweigungsanweisung enthält, die auf das eigentliche Ziel abzielt.  Verwenden Sie **\/OPT:LBR**, um die Erkennung von langen Verzweigungsanweisungen und die Platzierung von Zwischencodeinseln zu optimieren und somit die Gesamtcodegröße zu minimieren.  **\/OPT:NOLBR** weist den Linker an, ohne Optimierung Codeinseln für lange Verzweigungsanweisungen zu generieren, während sie auftreten.  
  
 Standardmäßig ist die **\/OPT:LBR**\-Option festgelegt, wenn keine inkrementelle Verlinkung aktiviert ist.  Wenn Sie einen nicht inkrementellen Link, aber keine langen Verzweigungsoptimierungen möchten, geben Sie **\/OPT:NOLBR** an.  Mit der **\/OPT:LBR**\-Option wird inkrementelles Verknüpfen deaktiviert.  
  
## Hinweise  
 Optimierungen verkleinern im Allgemeinen die Imagegröße und beschleunigen die Programmausführung, allerdings auf Kosten einer längeren Verknüpfungsdauer.  
  
 Verwenden Sie die [\/VERBOSE](../../build/reference/verbose-print-progress-messages.md)\-Option, um die durch **\/OPT:REF** entfernten Funktionen und die durch **\/OPT:ICF** gefalteten Funktionen anzuzeigen.  
  
### So legen Sie die OPT:ICF\- oder OPT:REF\-Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie im linken Bereich die Struktur **Konfigurationseigenschaften**, **Linker**, **Optimierung**.  
  
3.  Ändern Sie eine der folgenden Eigenschaften:  
  
    -   **COMDAT\-Faltung aktivieren**  
  
    -   **Verweise**  
  
### So legen Sie die OPT:LBR\-Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie den Ordner **Linker** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Befehlszeile** aus.  
  
4.  Geben Sie die Option in **Zusätzliche Optionen** ein:  
  
     `/opt:lbr`  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe die Eigenschaften <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableCOMDATFolding*> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OptimizeReferences*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)