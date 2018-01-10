---
title: -OPT (Optimierungen) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.OptimizeReferences
- /opt
- VC.Project.VCLinkerTool.OptimizeForWindows98
- VC.Project.VCLinkerTool.EnableCOMDATFolding
- VC.Project.VCLinkerTool.OptimizeFolding
- VC.Project.VCLinkerTool.FoldingIterations
- VC.Project.VCLinkerTool.OptimizeFoldingIterations
dev_langs: C++
helpviewer_keywords:
- LINK tool [C++], controlling optimizations
- -OPT linker option
- linker [C++], optimizations
- OPT linker option
- optimization, linker
- /OPT linker option
ms.assetid: 8f229863-5f53-48a8-9478-243a647093ac
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 86427dbf1ac6c3404daa36d2e02786aa80ed6453
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="opt-optimizations"></a>/OPT (Optimierungen)
Steuert die Optimierungen, die während eines Builds von LINK ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
/OPT:{REF | NOREF}  
/OPT:{ICF[=iterations] | NOICF}  
/OPT:{LBR | NOLBR}  
```  
  
## <a name="arguments"></a>Argumente  
 **REF** &#124; **NOREF**  
 **/ OPT: REF** löscht Funktionen und Daten, die nie verwiesen werden; **NOREF** bleiben Funktionen und Daten, die nie verwiesen wird.  
  
 Wenn /OFT:REF aktiviert ist, entfernt LINK unreferenzierte gepackte Funktionen und Daten. Ein Objekt enthält Paketfunktionen und Daten (COMDATs), wenn die Kompilierung mit der [/Gy](../../build/reference/gy-enable-function-level-linking.md) Option. Diese Optimierung ist als transitive COMDAT-Eliminierung bekannt. Standardmäßig **/OPT: REF** in nichtdebugversionen aktiviert ist. Um diesen Standardwert überschreiben und Unreferenzierte COMDATs im Programm beizubehalten, geben Sie **NOREF**. Sie können die [/INCLUDE](../../build/reference/include-force-symbol-references.md) Option aus, um das Entfernen eines bestimmten Symbols zu überschreiben.  
  
 Wenn **/OPT: REF** ist entweder explizit oder standardmäßig eingeschränkter Form aktiviert **/OPT: ICF** ist aktiviert, sodass lediglich identische Funktionen gefaltet. Wenn Sie möchten **/OPT: REF** , aber nicht **/OPT: ICF**, geben Sie **/OPT: REF, NOICF** oder **/OPT:NOICF**.  
  
 Wenn [/DEBUG](../../build/reference/debug-generate-debug-info.md) angegeben wird, der Standardwert für **/OPT** ist **NOREF**, und alle Funktionen werden im Image beibehalten. Um diesen Standardwert überschreiben und einen Debugbuild zu optimieren, geben Sie **/OPT: REF**. Da **/OPT: REF** impliziert **/OPT: ICF**, es wird empfohlen, dass Sie auch angeben, **/OPT:NOICF** identische Funktionen in Debugversionen beibehalten. Dadurch wird es einfacher, in Funktionen, die andernfalls gefaltet würden, Stapelüberwachungen zu lesen und Haltepunkte festzulegen. Die **/OPT: REF** -Option wird inkrementelles Verknüpfen deaktiviert.  
  
 Müssen Sie explizit kennzeichnen `const` Daten als COMDAT; verwenden Sie [__declspec(selectany)](../../cpp/selectany.md).  
  
 Angeben von **/OPT: ICF** ermöglicht keine der **/OPT: REF** Option.  
  
 **WINDOWS-FIREWALL [=** `iterations` **] &#124; NOICF**   
 Verwendung **/OPT: ICF [=**`iterations`**]** auf identische COMDAT-Faltung durchzuführen. Redundante COMDATs können aus der Linkerausgabe entfernt werden. Der optionale `iterations`-Parameter gibt die Häufigkeit für das Durchlaufen der Symbole für Duplikate an. Die Anzahl von Iterationen beträgt standardmäßig 2. Zusätzliche Iterationen können mehr Duplikate auffinden, die bei der Faltung in vorherigen Iterationen unentdeckt blieben.  
  
 Der Linker verhält sich anders bei **/OPT: REF** angegeben wird – und **ICF** ist wirksam standardmäßig – als mit der beim **/OPT: REF, ICF** explizit angegeben wird. Die Form des **ICF** , aktiviert **/OPT: REF** allein nicht schreibgeschützten Daten gefaltet – Dies schließt .rdata, .pdata und .xdata. Dies führt zu einer geringeren Funktionsfaltung, wenn Images für [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] erstellt werden, denn die Funktionen in diesen Modulen weisen eine größere Abhängigkeit von schreibgeschützten Daten, wie beispielsweise .pdata und .xdata, auf. Für ein vollständiges **ICF** -faltungsverhalten, explizit angeben **/OPT: ICF**.  
  
 Um Funktionen in COMDATs einzufügen, verwenden Sie die **/Gy** Compileroption; platzieren `const` Daten, deklarieren Sie ihn `__declspec(selectany)`. Informationen dazu, wie Sie Daten zur Faltung finden Sie unter [Selectany](../../cpp/selectany.md).  
  
 Standardmäßig **ICF** befindet sich auf If **REF** befindet sich auf. Um diesen Standard zu überschreiben, wenn **REF** wird angegeben, verwenden Sie **NOICF**. Wenn **/OPT: REF** nicht angegeben in einem Debugbuild müssen Sie explizit angeben **/OPT: ICF** COMDAT-Faltung aktivieren. Aber da **/OPT: ICF** identische Daten oder Funktionen zusammenführen kann, kann es sich um die die in der stapelüberwachung angezeigten Funktionsnamen ändern. Ferner verhindert die Option möglicherweise, dass Haltepunkte in bestimmten Funktionen festgelegt oder Daten im Debugger überprüft werden können, und Sie können auf unerwartete Funktionen stoßen, wenn Sie den Code Schritt für Schritt durchlaufen. Daher nicht empfehlenswert die Verwendung von **/OPT: ICF** im Debugmodus erstellt, es sei denn, die Vorteile von kompaktem Code die genannten Nachteile überwiegen.  
  
> [!NOTE]
>  Da **/OPT: ICF** kann dazu führen, dass die gleiche Adresse unterschiedlichen Funktionen oder schreibgeschützten Datenmembern zugewiesen werden (`const` -Variablen kompiliert mit **/Gy**), können sie ein Programm, das hängt unterbrechen eindeutige Adressen für Funktionen oder schreibgeschützte Datenmember. Weitere Informationen finden Sie unter [/Gy (Funktionslevel-Linking aktivieren)](../../build/reference/gy-enable-function-level-linking.md).  
  
 **LBR** &#124; **NOLBR**  
 Die **/OPT:LBR** und **/OPT:NOLBR** Optionen gelten nur für ARM-Binärdateien. Bestimmte Branchanweisungen von ARM-Prozessoren haben einen begrenzten Bereich. Wenn der Linker einen Sprung zu einer außerhalb des Gültigkeitsbereichs liegenden Adresse erkennt, ersetzt er die Zieladresse der Branchanweisung durch die Adresse einer „Codeinsel“, die eine Branchanweisung enthält, die auf das eigentliche Ziel abzielt. Sie können **/OPT:LBR** optimiert die Erkennung von langen verzweigungsanweisungen und die Platzierung von zwischencodeinseln gesamtcodegröße zu minimieren. **/OPT:NOLBR** weist den Linker an, wie sie, ohne Optimierung erkannt werden codeinseln für lange verzweigungsanweisungen zu generieren.  
  
 Wird standardmäßig die **/OPT:LBR** Option wird festgelegt, wenn keine inkrementelle Verlinkung aktiviert ist. Wenn Sie einen nicht inkrementellen Link, aber keine langen branchoptimierungen möchten, geben Sie **/OPT:NOLBR**. Die **/OPT:LBR** -Option wird inkrementelles Verknüpfen deaktiviert.  
  
## <a name="remarks"></a>Hinweise  
 Optimierungen verkleinern im Allgemeinen die Imagegröße und beschleunigen die Programmausführung, allerdings auf Kosten einer längeren Verknüpfungsdauer.  
  
 Sie können die [/VERBOSE](../../build/reference/verbose-print-progress-messages.md) Option aus, um die Funktionen, die entfernt werden, finden Sie unter **/OPT: REF** und Funktionen, die von gefalteten **/OPT: ICF**.  
  
### <a name="to-set-the-opticf-or-optref-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie die OPT:ICF- oder OPT:REF-Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie im linken Bereich **Konfigurationseigenschaften**, **Linker**, **Optimierung**.  
  
3.  Ändern Sie eine der folgenden Eigenschaften:  
  
    -   **COMDAT-Faltung aktivieren**  
  
    -   **Verweise**  
  
### <a name="to-set-the-optlbr-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie die OPT:LBR-Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **Linker** Ordner.  
  
3.  Wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
4.  Geben Sie die Option im **Zusatzoptionen**:  
  
     `/opt:lbr`  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe die Eigenschaften <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableCOMDATFolding%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OptimizeReferences%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)