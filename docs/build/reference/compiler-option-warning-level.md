---
title: -w,-W0,-W1, -W2,-W3, -W4,-w1,-w2,-w3,-w4,-Wand, -wd,-wir -wo, -Wv, - WX (Warnstufe) | Microsoft Docs
ms.custom: ''
ms.date: 01/31/2018
ms.technology:
- cpp-tools
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 60fc8072a95787f9e6f50e7e5c50408ef66e3261
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379249"
---
# <a name="w-w0-w1-w2-w3-w4-w1-w2-w3-w4-wall-wd-we-wo-wv-wx-warning-level"></a>/ w, / W0, /W1, /W2, /W3, / W4, /w1, /w2, /w3, / W4, / Wall, / WD, / we, /, wo WV, / WX (Warnstufe)

Gibt an, wie der Compiler Warnungen für eine bestimmte Kompilierung generiert.

## <a name="syntax"></a>Syntax

> **/w**  
> **/W0**  
> **/W1**  
> **/W2**  
> **/W3**  
> **/W4**  
> **/Wall**  
> **WV**\[**:**_Version_]  
> **/WX**  
> **/W1**_Warnung_  
> **/w2**_warning_  
> **/w3**_warning_  
> **/w4**_warning_  
> **/wd**_warning_  
> **/ we**_Warnung_  
> **/wo**_warning_  

## <a name="remarks"></a>Hinweise

Die Warnungsoptionen angeben, welche compilerwarnungen angezeigt und das Verhalten bei einer Warnung für die gesamte Kompilierung.

Die Warnungsoptionen und die zugehörigen Argumente werden in der folgenden Tabelle beschrieben:

|Option|Beschreibung|
------------|-----------------|
|**/w**|Unterdrückt alle compilerwarnungen.|
|**/W0**<br /><br /> **/W1**<br /><br /> **/W2**<br /><br /> **/W3**<br /><br /> **/W4**|Gibt die Ebene der Warnungen an, die vom Compiler generiert werden. Gültige Warnung Schweregrade liegen zwischen 0 und 4:<br />**/ W0** unterdrückt alle Warnungen. Dies entspricht dem **/w**.<br />**/ W1** Ebene 1 (Schweregrad) Warnungen angezeigt. **/ W1** ist die Standardeinstellung in der Befehlszeile-Compiler.<br />**/ W2** zeigt Ebene 1 und Ebene 2 (signifikante) Warnungen.<br />**/ W3** zeigt Ebene 1, Ebene 2 und 3 (produktionsqualitäts-)-Warnung mit Schweregrad. **/ W3** ist die Standardeinstellung in der IDE.<br />**/ W4** zeigt Ebene 1, Ebene 2 und 3 Warnung mit Schweregrad und alle Ebene 4 (informative) Warnungen, die nicht standardmäßig deaktiviert. Es wird empfohlen, dass Sie diese Option verwenden, um fusselfreien-ähnliche Warnungen bereitzustellen. Für ein neues Projekt möglicherweise am besten geeignet, **/W4** in allen Kompilierungen; Dadurch wird die wenigsten Codefehler für mögliche schwer zu findende sichergestellt.|
|**/Wall**|Zeigt alle Warnungen angezeigt, indem **/W4** und alle anderen Warnungen, **/W4** enthält keine – z. B. Warnungen, die standardmäßig deaktiviert sind. Weitere Informationen finden Sie unter [Compiler Warnungen, werden standardmäßig](../../preprocessor/compiler-warnings-that-are-off-by-default.md).|
|**WV**\[**:**_Version_]|Zeigt nur die Warnungen in Compilerversion eingeführte *Version* und früher. Sie können diese Option verwenden, um neue Warnungen im Code zu unterdrücken, bei der Migration auf eine neuere Version des Compilers und vorhandenen Build-Prozess zu behalten, während Sie das Problem beheben. Der optionale Parameter *Version* hat das Format *Nn*[. *mm*[. *Bbbbb*]], in dem *Nn* ist die Hauptversionsnummer *mm* ist die optionale Nebenversionsnummer und *Bbbbb* ist die optionale Buildnummer der Compiler. Verwenden Sie z. B. */Wv:17* eingeführte in Visual Studio 2012 (d. h. alle Versionen des Compilers, die eine höhere Versionsnummer 17) oder früher Warnungen angezeigt, aber Unterdrücken von Warnungen, die in Visual Studio 2013 (Hauptversion eingeführt 18) und höher. Standardmäßig **WV** verwendet, die die aktuelle Versionsnummer des Compilers und keine Warnungen werden unterdrückt. Informationen darüber, welche Warnungen, indem Compilerversion unterdrückt werden finden Sie unter [Compilerwarnungen von Compilerversion](../../error-messages/compiler-warnings/compiler-warnings-by-compiler-version.md).|
|**/WX**|Behandelt alle Compilerwarnungen als Fehler. Für ein neues Projekt möglicherweise am besten geeignet, **/WX** in allen Kompilierungen; beheben alle Warnungen wird sichergestellt, dass die wenigsten Codefehler für mögliche schwer zu findende.<br /><br /> Der Linker hat auch ein **/WX** Option. Weitere Informationen finden Sie unter [/WX (Linkerwarnungen als Fehler behandeln)](../../build/reference/wx-treat-linker-warnings-as-errors.md).|
|**/W1**_Nnnn_<br /><br /> **/W2**_Nnnn_<br /><br /> **/w3**_Nnnn_<br /><br /> **/ W4**_Nnnn_|Legt die Warnstufe fest, für die Warnungsnummer gemäß _Nnnn_. Dadurch können Sie das Compilerverhalten für diese Warnung zu ändern, wenn eine bestimmte Warnung Ebene festgelegt ist. Sie können diese Optionen in Kombination mit anderen Warnungsoptionen verwenden, um eine eigene Codierung Standards für Warnungen, anstatt der Standardeinstellung von Visual Studio angebotenen zu erzwingen.<br /><br /> Beispielsweise **/w34326** bewirkt, dass C4326 als eine Warnung der Stufe 3 anstelle der Ebene 1 generiert werden soll. Wenn Sie bei der Kompilierung mit beiden Methoden die **/w34326** Option und die **/W2** Option Warnung C4326 wird nicht generiert.|
|**/ WD**_Nnnn_|Unterdrückt die compilerwarnung, die durch angegebenen _Nnnn_.<br /><br /> Beispielsweise **die Option/wd4326** unterdrückt die Warnung C4326.|
|**/ we**_Nnnn_|Behandelt die compilerwarnung, die durch angegebenen _Nnnn_ als Fehler.<br /><br /> Beispielsweise **/we4326** bewirkt, dass die Warnungsnummer C4326 vom Compiler als Fehler behandelt werden soll.|
|**/ wo**_Nnnn_|Der Compiler also Warnung angegebenen Berichte _Nnnn_ nur einmal.<br /><br /> Beispielsweise **/wo4326 bewirkt z.** Ursachen Warnung C4326 nur einmal gemeldet werden, beim ersten er festgestellt wird vom Compiler.|

Wenn Sie die Optionen für die Warnung, verwenden Wenn Sie einen vorkompilierten Header Erstellen der ["/ Yc"](../../build/reference/yc-create-precompiled-header-file.md) jede Verwendung des vorkompilierten Headers mithilfe der option der ["/ Yu"](../../build/reference/yu-use-precompiled-header-file.md) Option bewirkt, dass dieselben Warnung-Optionen wirksam werden. erneut aus. Sie können die Warnungsoptionen den Wert in der vorkompilierte Header mit einem anderen Warnung-Option in der Befehlszeile überschreiben.

Sie können eine [#pragma Warning](../../preprocessor/warning.md) Richtlinie zum Steuern der Ebene der Warnung, d. h., die zum Zeitpunkt der Kompilierung in bestimmten Quelldateien gemeldet.

Pragma-Direktiven Warnung im Quellcode wurden, wirken sich die **/w** Option.

Die [erstellen Fehlerdokumentation](../../error-messages/compiler-errors-1/c-cpp-build-errors.md) beschreibt die Warnungen sowie die Warnstufen und gibt an, warum bestimmte Anweisungen nicht wie beabsichtigt kompilieren können.

### <a name="to-set-the-compiler-options-in-the-visual-studio-development-environment"></a>Die Compileroptionen in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Festlegen der **/W0**, **/W1**, **/W2**, **/W3**, **/W4**, **/Wall**m **WV**, **/WX** oder **/WX-** Optionen der **Konfigurationseigenschaften** > **C / C++** > **allgemeine** Eigenschaftenseite.

   - Festlegen der **/W0**, **/W1**, **/W2**, **/W3**, **/W4**, oder **/Wall** Ändern von Optionen, die **Warnstufe** Eigenschaft.

   - Festlegen der **/WX** oder **/WX-** Ändern von Optionen, die **Warnungen als Fehler behandeln** Eigenschaft.

   - Festlegen die Version für die **WV** aus, geben Sie die Versionsnummer des Compilers in der **Warnung Version** Eigenschaft.

1. Festlegen der **/WD** oder **/we** Optionen der **Konfigurationseigenschaften** > **C/C++-**  >   **Erweiterte** Eigenschaftenseite.

   - Festlegen der **/WD** aus, Aktivieren der **bestimmte Warnungen deaktivieren** Eigenschaft Dropdown-Steuerelement, und wählen Sie dann **bearbeiten**. Im Eingabefeld in der **bestimmte Warnungen deaktivieren** Dialogfeld, geben Sie die Anzahl der Warnung. Wenn mehr als eine einzige Warnung eingeben möchten, trennen Sie die Werte durch ein Semikolon (**;**). Geben Sie beispielsweise zum Deaktivieren der C4001 und C4010 generiert **4001; 4010**. Wählen Sie **OK** die Änderungen zu speichern und an die **Eigenschaftenseiten** Dialogfeld.

   - Festlegen der **/we** aktivieren, wählen Sie die **bestimmte Warnungen als Fehler behandeln** Eigenschaft Dropdown-Steuerelement, und wählen Sie dann **bearbeiten**. Im Eingabefeld in der **bestimmte Warnungen als Fehler behandeln** Dialogfeld, geben Sie die Anzahl der Warnung. Wenn mehr als eine einzige Warnung eingeben möchten, trennen Sie die Werte durch ein Semikolon (**;**). Geben Sie beispielsweise zum C4001 und C4010 generiert als Fehler zu behandeln, **4001; 4010**. Wählen Sie **OK** die Änderungen zu speichern und an die **Eigenschaftenseiten** Dialogfeld.

1. Festlegen der **/wo** aus, Aktivieren der **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite "". Geben Sie die Compileroption "in der **Zusatzoptionen** Feld.

1. Wählen Sie **OK** zum Speichern der Änderungen.

### <a name="to-set-the-compiler-option-programmatically"></a>So legen Sie die Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarningLevel%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarnAsError%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableSpecificWarnings%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)  
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)  
