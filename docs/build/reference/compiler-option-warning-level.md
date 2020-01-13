---
title: /w,/W0,/W1,/W2,/w3,/W4,/W1,/W2,/w3,/W4,/Wall,/WD,/We,/wo,/WV,/WX (Warnstufe)
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
ms.openlocfilehash: 7d2fd21c476ef4346aa86e682047ea644183b2f3
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2019
ms.locfileid: "74683058"
---
# <a name="w-w0-w1-w2-w3-w4-w1-w2-w3-w4-wall-wd-we-wo-wv-wx-warning-level"></a>/w,/W0,/W1,/W2,/w3,/W4,/W1,/W2,/w3,/W4,/Wall,/WD,/We,/wo,/WV,/WX (Warnstufe)

Gibt an, wie der Compiler Warnungen für eine bestimmte Kompilierung generiert.

## <a name="syntax"></a>Syntax

> **/w**\
> **/W0**\
> **/W1**\
> **/W2**\
> **/W3**\
> **/W4**\
> **/Wall**\
> **/WV**\[ **:** _Version_] \
> **/WX**\
> **/W1**_Warnung_\
> **/W2**_Warnung_\
> **/w3**_Warnung_\
> **/W4**_Warnung_\
> **/WD**_Warnung_\
> **/We**_Warnung_\
> **/wo**_warning_

## <a name="remarks"></a>Hinweise

Die Warnungs Optionen geben an, welche Compilerwarnungen angezeigt werden sollen, und das Warnungs Verhalten der gesamten Kompilierung.

Die Warnungs Optionen und die zugehörigen Argumente werden in der folgenden Tabelle beschrieben:

|Option|Beschreibung|
------------|-----------------|
|**/w**|Unterdrückt alle Compilerwarnungen.|
|**/W0**<br /><br /> **/W1**<br /><br /> **/W2**<br /><br /> **/W3**<br /><br /> **/W4**|Gibt die Ebene der Warnungen an, die vom Compiler generiert werden sollen. Gültige Warn Stufen liegen zwischen 0 und 4:<br />**/W0** unterdrückt alle Warnungen. Dies entspricht **/w**.<br />**/W1** zeigt Warnungen der Stufe 1 (schwerwiegend) an. **/W1** ist die Standardeinstellung im Befehlszeilen Compiler.<br />**/W2** zeigt Warnungen der Stufe 1 und der Ebene 2 (signifikant) an.<br />**/W3** zeigt Warnungen der Stufe 1, Ebene 2 und Ebene 3 (Produktionsqualität) an. **/W3** ist die Standardeinstellung in der IDE.<br />**/W4** zeigt Warnungen auf Ebene 1, Ebene 2 und Ebene 3 sowie alle Warnungen der Stufe 4 (Information) an, die nicht standardmäßig deaktiviert sind. Es wird empfohlen, diese Option zu verwenden, um lint-ähnliche Warnungen bereitzustellen. Bei einem neuen Projekt ist es möglicherweise am besten, **/W4** in allen Kompilierungen zu verwenden. Dadurch wird sichergestellt, dass möglichst wenige schwer zu suchende Code Fehler gefunden werden.|
|**/Wall**|Zeigt alle Warnungen an, die von **/W4** angezeigt werden, und alle anderen Warnungen, die **/W4** nicht enthält – z. b. Warnungen, die standardmäßig deaktiviert sind. Weitere Informationen finden Sie unter [standardmäßig](../../preprocessor/compiler-warnings-that-are-off-by-default.md)deaktivierte Compilerwarnungen.|
|**/WV**\[ **:** _Version_]|Zeigt nur die Warnungen an, die in *der Version der Version und früheren* Versionen von Mit dieser Option können Sie neue Warnungen im Code unterdrücken, wenn Sie zu einer neueren Version des Compilers migrieren und den vorhandenen Buildprozess während der Behebung beibehalten. Die optionale Parameter *Version* hat die Form *NN*[. *mm*[. *bbbbb*]], wobei *NN* die Hauptversionsnummer, *mm* die optionale neben Versionsnummer und *bbbbb* die optionale Buildnummer des Compilers ist. Verwenden Sie z. b. */WV: 17* zum Anzeigen von Warnungen, die in Visual Studio 2012 (d. h. eine beliebige Version des Compilers mit der Hauptversionsnummer 17) oder früher eingeführt wurden, aber die in Visual Studio 2013 (Hauptversion 18) und höher eingeführten Warnungen unterdrücken. Standardmäßig verwendet **/WV** die aktuelle compilerversionsnummer, und es werden keine Warnungen unterdrückt. Informationen dazu, welche Warnungen von der Compilerversion unterdrückt werden, finden Sie unter [Compilerwarnungen by Compiler Version](../../error-messages/compiler-warnings/compiler-warnings-by-compiler-version.md).|
|**/WX**|Behandelt alle Compilerwarnungen als Fehler. Bei einem neuen Projekt ist es möglicherweise am besten, **/WX** in allen Kompilierungen zu verwenden. durch das Auflösen aller Warnungen wird sichergestellt, dass möglichst wenige schwer zu suchende Code Fehler gefunden werden.<br /><br /> Der Linker verfügt auch über eine **/WX** -Option. Weitere Informationen finden Sie unter [/WX (Linkerwarnungen als Fehler behandeln)](wx-treat-linker-warnings-as-errors.md).|
|**/w1**_nnnn_<br /><br /> **/w2**_nnnn_<br /><br /> **/w3**_nnnn_<br /><br /> **/w4**_nnnn_|Legt die Warnstufe für die durch _nnnn_angegebene Warnungs Nummer fest. Auf diese Weise können Sie das Compilerverhalten für diese Warnung ändern, wenn eine bestimmte Warnstufe festgelegt ist. Diese Optionen können in Kombination mit anderen Warn Optionen verwendet werden, um eigene Codierungsstandards für Warnungen zu erzwingen, anstelle der von Visual Studio bereitgestellten Standardwerte.<br /><br /> Beispielsweise bewirkt **/w34326** , dass C4326 als Warnung der Ebene 3 anstelle von Ebene 1 generiert wird. Wenn Sie mit der **/w34326** -Option und der **/W2** -Option kompilieren, wird Warning C4326 nicht generiert.|
|**/wd**_nnnn_|Unterdrückt die Compilerwarnung, die von _nnnn_angegeben wird.<br /><br /> Beispielsweise **/wd4326** unterdrückt die Compilerwarnung C4326.|
|**/We**_nnnn_|Behandelt die Compilerwarnung, die von _nnnn_ als Fehler angegeben wird.<br /><br /> Beispielsweise bewirkt **/we4326** , dass die Warnungs Nummer C4326 vom Compiler als Fehler behandelt wird.|
|**/wo**_nnnn_|Meldet die Compilerwarnung, die von _nnnn_ nur einmal angegeben wird.<br /><br /> Beispielsweise bewirkt **/wo4326** , dass Warning C4326 nur einmal gemeldet wird, wenn der Compiler das erste Mal gefunden hat.|

Wenn Sie eine der Warn Optionen verwenden, wenn Sie mithilfe der [/Yc](yc-create-precompiled-header-file.md) -Option einen vorkompilierten Header erstellen, werden die gleichen Warn Optionen durch jede Verwendung des vorkompilierten Headers mithilfe der [/Yu](yu-use-precompiled-header-file.md) -Option erneut wirksam. Sie können die im vorkompilierten Header festgelegten Warnungs Optionen überschreiben, indem Sie eine andere Warn Option in der Befehlszeile verwenden.

Sie können eine [#pragma warning](../../preprocessor/warning.md) -Direktive verwenden, um die Warnstufe zu steuern, die zur Kompilierzeit in bestimmten Quelldateien gemeldet wird.

Warnung: Pragma-Direktiven im Quellcode sind von der **/w** -Option nicht betroffen.

In der [buildfehlerdokumentation](../../error-messages/compiler-errors-1/c-cpp-build-errors.md) werden die Warnungen und Warn Stufen beschrieben, und es wird angegeben, warum bestimmte Anweisungen möglicherweise nicht wie beabsichtigt kompiliert werden.

### <a name="to-set-the-compiler-options-in-the-visual-studio-development-environment"></a>So legen Sie die Compileroptionen in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Um die Optionen **/W0**, **/W1**, **/W2**, **/w3**, **/W4**, **/Wall,/WV**, **/WX** oder **/WX-** festzulegen, wählen Sie die **Eigenschaften Seite Konfigurations Eigenschaften** > **C/C++**  > **Allgemein** aus.

   - Um die Optionen **/W0**, **/W1**, **/W2**, **/w3**, **/W4**oder **/Wall** festzulegen, ändern Sie die Eigenschaft **Warnstufe** .

   - Um die Optionen **/WX** oder **/WX-** festzulegen, ändern Sie die Eigenschaft **Warnungen als Fehler behandeln** .

   - Um die Version für die **/WV** -Option festzulegen, geben Sie die compilerversionsnummer in der Eigenschaft **Warning Version** ein.

1. Um die Optionen **/WD** oder **/We** festzulegen, wählen Sie die **Eigenschaften Seite Konfigurations Eigenschaften** > **CC++ /**  > **erweitert** aus.

   - Um die **/WD** -Option festzulegen, wählen Sie das Dropdown-Steuerelement **bestimmte Warnungen deaktivieren** aus, und wählen Sie dann **Bearbeiten**aus. Geben Sie im Dialogfeld bearbeiten im Dialogfeld **bestimmte Warnungen deaktivieren** die Warnungs Nummer ein. Um mehr als eine Warnung einzugeben, trennen Sie die Werte durch ein Semikolon ( **;** ). Um beispielsweise sowohl C4001 als auch C4010 zu deaktivieren, geben Sie **4001; 4010**ein. Wählen Sie **OK** aus, um die Änderungen zu speichern und zum Dialogfeld **Eigenschaften Seiten** zurückzukehren.

   - Um die **/We** -Option festzulegen, wählen Sie das Dropdown-Steuerelement **bestimmte Warnungen als Fehler behandeln** aus, und wählen Sie dann **Bearbeiten**aus. Geben Sie im Dialogfeld "Bearbeiten" im Dialogfeld " **bestimmte Warnungen als Fehler behandeln** " die Warnungs Nummer ein. Um mehr als eine Warnung einzugeben, trennen Sie die Werte durch ein Semikolon ( **;** ). Wenn Sie z. b. sowohl C4001 als auch C4010 als Fehler behandeln möchten, geben Sie **4001; 4010**ein. Wählen Sie **OK** aus, um die Änderungen zu speichern und zum Dialogfeld **Eigenschaften Seiten** zurückzukehren.

1. Um die **/wo** -Option festzulegen, wählen Sie die **Eigenschaften Seite Konfigurations Eigenschaften** > **C/ > -C++**  **Befehlszeile** aus. Geben Sie die Compileroption im Feld **zusätzliche Optionen** ein.

1. Klicken Sie auf **OK**, um die Änderungen zu speichern.

### <a name="to-set-the-compiler-option-programmatically"></a>So legen Sie die Compileroption Programm gesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarningLevel%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarnAsError%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableSpecificWarnings%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)\
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
