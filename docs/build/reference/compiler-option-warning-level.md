---
title: / w, / W0, / W1, / W2, / w3, / W4, / W1, / W2, / w3, / W4, / Wall, / WD, / we, / wo, / WV, / WX (Warnstufe)
ms.date: 01/31/2018
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
ms.openlocfilehash: 997a73541ab95a393bda4ebf5412c11f025b03a3
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "57820688"
---
# <a name="w-w0-w1-w2-w3-w4-w1-w2-w3-w4-wall-wd-we-wo-wv-wx-warning-level"></a>/ w, / W0, / W1, / W2, / w3, / W4, / W1, / W2, / w3, / W4, / Wall, / WD, / we, / wo, / WV, / WX (Warnstufe)

Gibt an, wie der Compiler Warnungen für eine bestimmte Kompilierung generiert.

## <a name="syntax"></a>Syntax

> **/ w**
>  **/W0**
>  **/W1**
>  **/W2**
>  **/w3** 
>  **/W4**
>  **/wall**
>  **/WV**\[**:**_Version _] **/WX**
>  **/W1**_Warnung_
>  **/W2** _ Warnung_
>  **/w3**_Warnung_
>  **/W4**_Warnung_ 
>  **/WD**_Warnung_
>  **/we**_Warnung_ 
>  **/wo**_Warnung_

## <a name="remarks"></a>Hinweise

Die Warnungsoptionen Geben Sie die Compiler-Warnungen für die Anzeige und das Verhalten bei einer Warnung für die gesamte Kompilierung.

Die Warnungsoptionen für die und die zugehörigen Argumente werden in der folgenden Tabelle beschrieben:

|Option|Beschreibung|
------------|-----------------|
|**/w**|Unterdrückt alle compilerwarnungen.|
|**/W0**<br /><br /> **/W1**<br /><br /> **/W2**<br /><br /> **/W3**<br /><br /> **/W4**|Gibt die Ebene der Warnungen an, die vom Compiler generiert werden. Die gültige Warnung Ebenen liegen zwischen 0 und 4:<br />**/ W0** alle Warnungen unterdrückt. Dies entspricht dem **/w**.<br />**/ W1** zeigt Warnungen der Stufe 1 (Schweregrad). **/ W1** ist die Standardeinstellung in den Befehlszeilencompiler.<br />**/ W2** werden auf Ebene 1 und Warnungen der Stufe 2 (wichtige).<br />**/ W3** zeigt auf Ebene 1, Ebene 2 und Ebene 3 (Produktionsqualität) Warnungen. **/ W3** ist die Standardeinstellung in der IDE.<br />**/ W4** zeigt auf Ebene 1, Ebene 2 und Ebene 3 Warnungen, und alle Ebene 4 (informative) Warnungen, die nicht standardmäßig deaktiviert sind. Es wird empfohlen, dass Sie diese Option verwenden, um Lint-ähnlicher Warnungen bereitzustellen. Für ein neues Projekt möglicherweise am besten geeignet **/W4** in allen Kompilierungen; Dadurch wird die geringstmögliche Anzahl schwer zu findender Codefehler sichergestellt.|
|**/Wall**|Zeigt alle Warnungen angezeigt, indem **/W4** und alle anderen Warnungen, die **/W4** enthält keine – z. B. Warnungen, die standardmäßig deaktiviert sind. Weitere Informationen finden Sie unter [Compiler Warnings, sind standardmäßig](../../preprocessor/compiler-warnings-that-are-off-by-default.md).|
|**/ WV**\[**:**_Version_]|Zeigt nur die Warnungen, die in der Version des Compilers eingeführt wurden *Version* und früheren Versionen. Sie können diese Option verwenden, um neue Warnungen im Code zu unterdrücken, bei der Migration auf eine neuere Version des Compilers, und vorhandene Build-Prozess zu verwalten, während Sie sie beheben. Der optionale Parameter *Version* hat das Format *Nn*[. *mm*[. *Bbbbb*]], in denen *Nn* ist die Hauptversionsnummer *mm* ist die optionale Nebenversionsnummer und *Bbbbb* ist die optionale Buildnummer der Compiler. Verwenden Sie z. B. */Wv:17* , eingeführt in Visual Studio 2012 (d. h. jede Version des Compilers, die eine Hauptversionsnummer von 17) oder früher Warnungen angezeigt, aber Unterdrücken von Warnungen in Visual Studio 2013 (wichtigsten Version eingeführt wurden 18) und höher. In der Standardeinstellung **/WV** verwendet, die die aktuelle Versionsnummer für Compiler und keine Warnungen unterdrückt werden. Informationen darüber, welche Warnungen, durch die Version des Compilers unterdrückt werden, finden Sie unter [Compilerwarnungen nach Compilerversion](../../error-messages/compiler-warnings/compiler-warnings-by-compiler-version.md).|
|**/WX**|Behandelt alle Compilerwarnungen als Fehler. Für ein neues Projekt möglicherweise am besten geeignet **/WX** in allen Kompilierungen; Auflösen aller Warnungen wird die geringstmögliche Anzahl schwer zu findender Codefehler sichergestellt.<br /><br /> Der Linker verfügt auch über eine **/WX** Option. Weitere Informationen finden Sie unter [/WX (Linkerwarnungen als Fehler behandeln)](wx-treat-linker-warnings-as-errors.md).|
|**/w1**_nnnn_<br /><br /> **/w2**_nnnn_<br /><br /> **/w3**_nnnn_<br /><br /> **/w4**_nnnn_|Legt die Warnstufe fest, für die Warnungsnummer gemäß _Nnnn_. Dadurch können Sie ändern das Verhalten des Compilers für diese Warnung, wenn eine bestimmte Warnung-Ebene festgelegt ist. Sie können diese Optionen in Kombination mit anderen Warnungsoptionen verwenden, um eine eigene Codierung Standards für Warnungen, anstatt die von Visual Studio bereitgestellten Standardressourcen zu erzwingen.<br /><br /> Z. B. **/w34326** bewirkt, dass C4326 als eine Warnung der Stufe 3 anstelle von Ebene 1 generiert werden soll. Wenn Sie Kompilieren mit der **/w34326** Option und die **/W2** Option Warnung C4326 wird nicht generiert.|
|**/wd**_nnnn_|Unterdrückt die compilerwarnung, die angegeben wird _Nnnn_.<br /><br /> Z. B. **die Option/wd4326** unterdrückt die Warnung C4326.|
|**/we**_nnnn_|Behandelt die compilerwarnung, die angegebenen _Nnnn_ als Fehler.<br /><br /> Z. B. **/we4326** bewirkt, dass die Nummer der codeanalysewarnung C4326 vom Compiler als Fehler behandelt werden soll.|
|**/wo**_nnnn_|Die compilerwarnung, d. h. angegebenen Berichte _Nnnn_ nur einmal.<br /><br /> Z. B. **/wo4326 bewirkt z.** Ursachen Warnung C4326 nur einmal gemeldet werden, beim ersten er wird vom Compiler gefunden.|

Wenn Sie die Optionen für die Warnung, verwenden Wenn Sie einen vorkompilierten Header erstellen die ["/ Yc"](yc-create-precompiled-header-file.md) option jede Verwendung des vorkompilierten Headers mit der ["/ Yu"](yu-use-precompiled-header-file.md) Option bewirkt, dass die gleichen Warnungsoptionen in Kraft treten erneut aus. Sie können die Warnungsoptionen den Wert in der vorkompilierten Headerdatei, mit einem anderen Warnung die Option in der Befehlszeile überschreiben.

Sie können eine [#pragma-Warnung](../../preprocessor/warning.md) Direktive, um die Warnstufe, steuern, die in bestimmten Quelldateien zur Kompilierungszeit gemeldet.

Warnung-Pragma-Anweisungen im Quellcode sind nicht betroffen von dem **/w** Option.

Die [erstellen Fehlerdokumentation](../../error-messages/compiler-errors-1/c-cpp-build-errors.md) beschreibt die Warnungen und Warnstufen und gibt an, warum bestimmte Anweisungen nicht kompilieren können, wie gewünscht.

### <a name="to-set-the-compiler-options-in-the-visual-studio-development-environment"></a>Zum Festlegen von Compileroptionen in der Visual Studio-Entwicklungsumgebung

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Festlegen der **/W0**, **/W1**, **/W2**, **/w3**, **/W4**, **/Wall**m **/WV**, **/WX** oder **/WX-** Option die **Konfigurationseigenschaften** > **C / C++** > **allgemeine** Eigenschaftenseite.

   - Festlegen der **/W0**, **/W1**, **/W2**, **/w3**, **/W4**, oder **/Wall** Ändern von Optionen, die **Warnstufe** Eigenschaft.

   - Festlegen der **/WX** oder **/WX-** Ändern von Optionen, die **Warnungen als Fehler behandeln** Eigenschaft.

   - Die Version für Festlegen der **/WV** aus, geben Sie die Versionsnummer des Compilers in der **Warnungsversion** Eigenschaft.

1. Festlegen der **/WD** oder **/we** Option die **Konfigurationseigenschaften** > **C/C++-**  >   **Erweiterte** Eigenschaftenseite.

   - Festlegen der **/WD** auswählen, wählen die **bestimmte Warnungen deaktivieren** Eigenschaft Dropdown-Steuerelement, und wählen Sie dann **bearbeiten**. Im Eingabefeld in der **bestimmte Warnungen deaktivieren** Dialogfeld Geben Sie die Anzahl der Warnung. Wenn mehr als eine Warnung eingeben möchten, trennen Sie die Werte durch ein Semikolon (**;**). Geben Sie beispielsweise um sowohl C4001 und C4010 deaktivieren, **4001; 4010**. Wählen Sie **OK** die Änderungen zu speichern und zurück zu den **Eigenschaftenseiten** Dialogfeld.

   - Festlegen der **/we** -Option verwenden, wählen Sie die **bestimmte Warnungen als Fehler behandeln** Eigenschaft Dropdown-Steuerelement, und wählen Sie dann **bearbeiten**. Im Eingabefeld in der **bestimmte Warnungen als Fehler behandeln** Dialogfeld Geben Sie die Anzahl der Warnung. Wenn mehr als eine Warnung eingeben möchten, trennen Sie die Werte durch ein Semikolon (**;**). Geben Sie beispielsweise um sowohl C4001 und C4010 als Fehler behandelt, **4001; 4010**. Wählen Sie **OK** die Änderungen zu speichern und zurück zu den **Eigenschaftenseiten** Dialogfeld.

1. Festlegen der **/wo** auswählen, wählen die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** auf der Seite. Geben Sie die Compileroption in der **zusätzliche Optionen** Feld.

1. Klicken Sie auf **OK**, um die Änderungen zu speichern.

### <a name="to-set-the-compiler-option-programmatically"></a>So legen Sie die Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarningLevel%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarnAsError%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableSpecificWarnings%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)
