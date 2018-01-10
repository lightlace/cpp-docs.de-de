---
title: -w,-W0,-W1, -W2,-W3, -W4,-w1,-w2,-w3,-w4,-Wand, -wd,-wir -wo, -Wv, - WX (Warnstufe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.DisableSpecificWarnings
- VC.Project.VCCLCompilerTool.WarningLevel
- VC.Project.VCCLWCECompilerTool.DisableSpecificWarnings
- VC.Project.VCCLCompilerTool.WarnAsError
- VC.Project.VCCLWCECompilerTool.WarnAsError
- /wx
- VC.Project.VCCLWCECompilerTool.WarningLevel
- /wall
- VC.Project.VCCLCompilerTool.TreatSpecificWarningsAsErrors
- /Wv
- /w0
- /w1
- /w2
- /w3
- /w4
- /wd
- /we
- /wo
dev_langs: C++
helpviewer_keywords:
- /W1 compiler option [C++]
- w compiler option [C++]
- -wo compiler option [C++]
- Warning Level compiler option
- W1 compiler option [C++]
- -we compiler option [C++]
- /WX compiler option [C++]
- -wd compiler option [C++]
- WX compiler option [C++]
- wo compiler option [C++]
- Wall compiler option [C++]
- /w compiler option
- W2 compiler option [C++]
- -W2 compiler option [C++]
- wd compiler option [C++]
- /we compiler option [C++]
- we compiler option [C++]
- -W1 compiler option [C++]
- -W4 compiler option [C++]
- -Wall compiler option [C++]
- /Wall compiler option [C++]
- -W0 compiler option [C++]
- W0 compiler option [C++]
- -WX compiler option [C++]
- /wo compiler option [C++]
- W4 compiler option [C++]
- W3 compiler option [C++]
- /wd compiler option [C++]
- warnings, as errors compiler option
- /W3 compiler option [C++]
- /W0 compiler option [C++]
- /W4 compiler option [C++]
- -W3 compiler option [C++]
- -w compiler option [C++]
- /W2 compiler option [C++]
- /Wv compiler option [C++]
ms.assetid: d6bc7bf5-c754-4879-909c-8e3a67e2629f
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4f38328f94fd68b3b5402d08ddb6d2bd97e3de76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="w-w0-w1-w2-w3-w4-w1-w2-w3-w4-wall-wd-we-wo-wv-wx-warning-level"></a>/ w, / W0, /W1, /W2, /W3, / W4, /w1, /w2, /w3, / W4, / Wall, / WD, / we, /, wo WV, / WX (Warnstufe)
Gibt an, wie der Compiler Warnungen für eine bestimmte Kompilierung generiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
/w  
/W0  
/W1  
/W2  
/W3  
/W4  
/Wall  
/Wv[<version>]  
/WX  
/w1<warning>   
/w2<warning>   
/w3<warning>   
/w4<warning>   
/wd<warning>   
/we<warning>   
/wo<warning>  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Warnungsoptionen angeben, welche compilerwarnungen angezeigt und das Verhalten bei einer Warnung für die gesamte Kompilierung.  
  
 Die Warnungsoptionen und die zugehörigen Argumente werden in der folgenden Tabelle beschrieben:  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**/ w**|Unterdrückt alle compilerwarnungen.|  
|**/W0**<br /><br /> **/W1**<br /><br /> **/W2**<br /><br /> **/W3**<br /><br /> **/W4**|Gibt die Ebene der Warnungen an, die vom Compiler generiert werden. Gültige Warnung Schweregrade liegen zwischen 0 und 4:<br /><br /> -   **/ W0** unterdrückt alle Warnungen.<br />-   **/ W1** Ebene 1 (Schweregrad) Warnungen angezeigt. **/ W1** ist die Standardeinstellung.<br />-   **/ W2** zeigt Ebene 1 und Ebene 2 (signifikante) Warnungen.<br />-   **/ W3** zeigt Ebene 1, Ebene 2 und 3 (produktionsqualitäts-)-Warnung mit Schweregrad.<br />-   **/ W4** zeigt Ebene 1, Ebene 2 und 3 Warnung mit Schweregrad und alle Ebene 4 (informative) Warnungen, die nicht standardmäßig deaktiviert. Es wird empfohlen, dass Sie diese Option lediglich zur Bereitstellung von fusselfreien-ähnliche Warnungen verwenden. Allerdings für ein neues Projekt möglicherweise am besten geeignet, **/W4** in allen Kompilierungen; Dadurch wird die wenigsten Codefehler für mögliche schwer zu findende sichergestellt.|  
|**/ Wall**|Zeigt alle Warnungen angezeigt, indem **/W4** und alle anderen Warnungen, **/W4** enthält keine – z. B. Warnungen, die standardmäßig deaktiviert sind. Weitere Informationen finden Sie unter [Compiler Warnungen, werden standardmäßig](../../preprocessor/compiler-warnings-that-are-off-by-default.md).|  
|**WV**`:version`|Unterdrücken von Warnungen als neueren Compilerversionen eingeführten `version`. Sie können diese Option verwenden, um zu bestimmen, ob neue Warnungen in Code, der ohne Warnungen kompiliert wird, wenn eine frühere Version des Compilers verwenden und die neuen Warnungen vom Buildprozess vorübergehend zu unterdrücken, während Sie das Problem beheben. Der optionale Parameter `version` hat das Format `nn`[.`mm` [. `bbbbb`]], in dem `nn` ist die Hauptversionsnummer `mm` ist die optionale Nebenversionsnummer und `bbbbb` ist die optionale Buildnummer des Compilers. Verwenden Sie z. B. `/Wv:17.00.00000` unterdrückt Warnungen, die in Visual C++ 2012 und höher eingeführt. Standardmäßig **WV** verwendet, die die aktuelle Versionsnummer des Compilers und keine Warnungen werden unterdrückt. Informationen darüber, welche Warnungen, indem Compilerversion unterdrückt werden finden Sie unter [Compilerwarnungen von Compilerversion](../..//error-messages/compiler-warnings/compiler-warnings-by-compiler-version.md).|  
|**/ WX**|Behandelt alle Compilerwarnungen als Fehler. Für ein neues Projekt möglicherweise am besten geeignet, **/WX** in allen Kompilierungen; beheben alle Warnungen wird sichergestellt, dass die wenigsten Codefehler für mögliche schwer zu findende.<br /><br /> Der Linker hat auch ein **/WX** Option. Weitere Informationen finden Sie unter [/WX (Linkerwarnungen als Fehler behandeln)](../../build/reference/wx-treat-linker-warnings-as-errors.md).|  
|**/W1**`n`<br /><br /> **/W2**`n`<br /><br /> **/w3**`n`<br /><br /> **/ W4**`n`|Legt die Warnstufe fest, für die Warnungsnummer gemäß `n`. Dadurch können Sie das Compilerverhalten für diese Warnung zu ändern, wenn eine bestimmte Warnung Ebene festgelegt ist. Sie können diese Optionen in Kombination mit anderen Warnungsoptionen verwenden, um eine eigene Codierung Standards für Warnungen, anstatt der Standardeinstellung von Visual Studio angebotenen zu erzwingen.<br /><br /> Beispielsweise `/w34326` bewirkt, dass C4326 als eine Warnung der Stufe 3 anstelle der Ebene 1 generiert werden soll. Wenn Sie bei der Kompilierung mit beiden Methoden die `/w34326` Option und die `/W2` Option Warnung C4326 wird nicht generiert.|  
|**/ WD**`n`|Unterdrückt die compilerwarnung, die durch angegebenen `n`.<br /><br /> Beispielsweise `/wd4326` unterdrückt die Warnung C4326.|  
|**/ we**`n`|Behandelt die compilerwarnung, die durch angegebenen `n` als Fehler.<br /><br /> Beispielsweise `/we4326` bewirkt, dass die Warnungsnummer C4326 vom Compiler als Fehler behandelt werden soll.|  
|**/ wo**`n`|Der Compiler also Warnung angegebenen Berichte `n` nur einmal.<br /><br /> Beispielsweise `/wo4326` Ursachen Warnung C4326 nur einmal gemeldet werden, beim ersten er festgestellt wird vom Compiler.|  
  
 Wenn Sie die Optionen für die Warnung, verwenden Wenn Sie einen vorkompilierten Header Erstellen der ["/ Yc"](../../build/reference/yc-create-precompiled-header-file.md) jede Verwendung des vorkompilierten Headers mithilfe der option der ["/ Yu"](../../build/reference/yu-use-precompiled-header-file.md) Option bewirkt, dass dieselben Warnung-Optionen wirksam werden. erneut aus. Sie können die Warnungsoptionen den Wert in der vorkompilierte Header mit einem anderen Warnung-Option in der Befehlszeile überschreiben.  
  
 Sie können eine [#pragma Warning](../../preprocessor/warning.md) Richtlinie zum Steuern der Ebene der Warnung, d. h., die zum Zeitpunkt der Kompilierung in bestimmten Quelldateien gemeldet.  
  
 Pragma-Direktiven Warnung im Quellcode wurden, wirken sich die **/w** Option.  
  
 Die [erstellen Fehlerdokumentation](../../error-messages/compiler-errors-1/c-cpp-build-errors.md) beschreibt die Warnungen sowie die Warnstufen und gibt an, warum bestimmte Anweisungen nicht wie beabsichtigt kompilieren können.  
  
### <a name="to-set-the-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie die Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie **C/C++-**.  
  
3.  Auf der **allgemeine** Eigenschaft, ändern Sie die **Warnstufe** oder **Warnungen als Fehler behandeln** Eigenschaften.  
  
4.  Auf der **erweitert** Eigenschaft, ändern Sie die **bestimmte Warnungen deaktivieren** Eigenschaft.  
  
5.  Für die restliche auf die **Befehlszeile** Eigenschaft geben Sie die Compileroption "in der **zusätzliche Optionen** Feld.  
  
### <a name="to-set-the-compiler-option-programmatically"></a>So legen Sie die Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarningLevel%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarnAsError%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableSpecificWarnings%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)