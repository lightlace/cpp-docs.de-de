---
title: /analyze (Codeanalyse)
ms.date: 10/15/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.EnablePREfast
- /analyze
- VC.Project.VCCLCompilerTool.PREfastAdditionalOptions
- VC.Project.VCCLCompilerTool.PREfastAdditionalPlugins
helpviewer_keywords:
- /analyze compiler option [C++]
- -analyze compiler option [C++]
- analyze compiler option [C++]
ms.assetid: 81da536a-e030-4bd4-be18-383927597d08
ms.openlocfilehash: f537fdea2703805c7ab1c57ba0d4429f6b683ae4
ms.sourcegitcommit: 9aab425662a66825772f091112986952f341f7c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72444887"
---
# <a name="analyze-code-analysis"></a>/analyze (Codeanalyse)

Aktiviert Codeanalyse- und Steueroptionen.

## <a name="syntax"></a>Syntax

> **/analyze**[-] [ **: WX-** ] [ **: Protokoll** *Dateiname*] [ **: Quiet**] [ **: STACKSIZE** *Number*] [ **: max_paths** *Number*] [ **: Only**] [ **: RuleSet** *RuleSet*] [ **:p Lugin**  *Plug-in-dll*]

## <a name="arguments"></a>Argumente

**/analyze**\
Aktiviert die Analyse im Standardmodus. Die Analyse Ausgabe wird wie andere Fehlermeldungen an das **Ausgabe** Fenster weitergeleitet. Verwenden Sie **/analyze-** , um die Analyse explizit zu deaktivieren.

**/analyze: WX-** \
Code Analyse Warnungen werden bei der Kompilierung mit **/WX**nicht als Fehler behandelt. Weitere Informationen finden Sie unter [/WX (Warnstufe)](compiler-option-warning-level.md).

**/analyze: Protokoll** *Dateiname*\
Ausführliche Analyseergebnisse werden als XML in die Datei geschrieben, die durch *filename*angegeben wird.

**/analyze: Quiet**\
Deaktiviert die Analyzer-Ausgabe im **Ausgabe** Fenster.

**/analyze: STACKSIZE** - *Nummer*\
Der mit dieser Option verwendete *Number* -Parameter gibt die Größe (in Bytes) des Stapel Rahmens an, für den die Warnung [C6262](/visualstudio/code-quality/c6262) generiert wird. Der Leerraum vor der *Zahl* ist optional. Wenn dieser Parameter nicht angegeben wird, beträgt die Stapel Rahmengröße standardmäßig 16 KB.

**/analyze: max_paths** *Number*\
Der mit dieser Option verwendete *Number* -Parameter gibt die maximale Anzahl von Codepfade an, die analysiert werden sollen. Wenn dieser Parameter nicht angegeben wird, ist die Zahl standardmäßig 256. Größere Werte führen zu einer gründlicheren Überprüfung, aber die Analyse kann länger dauern.

**/analyze: nur**\
In der Regel generiert der Compiler Code und führt nach der Ausführung der Analyse eine erweiterte Syntaxprüfung durch. Mit der Option **/analyze: Only** wird dieser Code Generierungs Durchlauf deaktiviert. Die Analyse erfolgt schneller, aber Kompilierungsfehler und Warnungen, die die Code Generierungs Übergabe des Compilers möglicherweise findet, werden nicht ausgegeben. Wenn das Programm keine Fehler bei der Codegenerierung hat, sind die Analyseergebnisse möglicherweise unzuverlässig. Es wird empfohlen, diese Option nur zu verwenden, wenn der Code die Syntax Überprüfung der Codegenerierung bereits ohne Fehler durchläuft.

**/analyze: RuleSet** *FILE_PATH. RuleSet*\
Ermöglicht Ihnen die Angabe der zu analysierenden Regelsätze, einschließlich benutzerdefinierter Regelsätze, die Sie selbst erstellen können. Wenn dieser Switch festgelegt ist, ist die Regel-Engine effizienter, da Sie vor der Ausführung nicht-Member des angegebenen Regelsatzes ausschließt. Andernfalls prüft die Engine alle Regeln.

Die RuleSets, die mit Visual Studio ausgeliefert werden, finden Sie unter *%VSInstallDir%\Team Tools\Static Analysis tools\rule Sets.*

Der folgende Beispiel benutzerdefinierte Regelsatz weist das Regel Modul an, nach C6001 und C26494 zu suchen. Sie können diese Datei beliebig lange platzieren, wenn Sie über eine `.ruleset`-Erweiterung verfügt, und Sie geben den vollständigen Pfad im Argument an.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description=" " ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

**/analyze: Plug** *-in-Plug-in-dll*\
Aktiviert das angegebene PREfast-Plug-in als Teil der Code Analyse Ausführungen.

::: moniker range="<=vs-2017"

Localespc. dll ist das Plug-in, das Parallelitäts bezogene Code Analyse Überprüfungen im Bereich der C261XX-Warnungen implementiert. Beispiel: [C26100](/visualstudio/code-quality/c26100), [C26101](/visualstudio/code-quality/c26101),..., [C26167](/visualstudio/code-quality/c26167).

Verwenden Sie zum Ausführen von "localespc. dll" Diese Compileroption: **/analyze: Plugin localespc. dll**

::: moniker-end
::: moniker range=">=vs-2019"

Die Datei "-Parallelität" implementiert neben läufigkeits bezogene Code Analyse Überprüfungen im Bereich von C261XX-Warnungen. Beispiel: [C26100](/visualstudio/code-quality/c26100), [C26101](/visualstudio/code-quality/c26101),..., [C26167](/visualstudio/code-quality/c26167).

Zum Ausführen von "" "" "" "" "" "" ".

```cmd
set Esp.Extensions=ConcurrencyCheck.dll
```

Verwenden Sie dann diese Compileroption: **/analyze: Plugin espxengine. dll**.

::: moniker-end

Um cppcorecheck. dll auszuführen, führen Sie zuerst den folgenden Befehl über eine Developer-Eingabeaufforderung aus:

```cmd
set Esp.Extensions=CppCoreCheck.dll
```

Verwenden Sie dann diese Compileroption: **/analyze: Plugin espxengine. dll**.

## <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Code Analyse für c/C++ Overview](/visualstudio/code-quality/code-analysis-for-c-cpp-overview) und [Code Analyse für c/C++ Warnungen](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Wählen Sie die **Eigenschaften Seite Konfigurations Eigenschaften** > **Code Analyse** > **Allgemein** aus.

1. Ändern Sie eine oder mehrere der **Code Analyse** Eigenschaften.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)\
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
