---
title: /analyze (Codeanalyse)
ms.date: 10/01/2019
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
ms.openlocfilehash: d647045d76dc32544f8146424b220547890b0943
ms.sourcegitcommit: 4517932a67bbf2db16cfb122d3bef57a43696242
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2019
ms.locfileid: "71816332"
---
# <a name="analyze-code-analysis"></a>/analyze (Codeanalyse)

Aktiviert Codeanalyse- und Steueroptionen.

## <a name="syntax"></a>Syntax

```cmd
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only][:ruleset]
```

## <a name="arguments"></a>Argumente

/analyze aktiviert die Analyse im Standardmodus. Die Analyse Ausgabe wird wie andere Fehlermeldungen an das **Ausgabe** Fenster weitergeleitet. Verwenden Sie **/analyze-** , um die Analyse explizit zu deaktivieren.

/ANALYZE: WX-angeben von **/analyze: WX-** bedeutet, dass Code Analyse Warnungen nicht als Fehler behandelt werden, wenn Sie die Kompilierung mit **/WX**ausführen. Weitere Informationen finden Sie unter [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX (Warnstufe)](compiler-option-warning-level.md).

/ANALYZE: Log `filename` ausführliche Analyseergebnisse werden als XML in die Datei geschrieben, die von `filename` angegeben wird.

/ANALYZE: Quiet schaltet die Analyse der Analyse im **Ausgabe** Fenster aus.

/ANALYZE: STACKSIZE `number` der mit dieser Option verwendete `number`-Parameter gibt die Größe (in Bytes) des Stapel Rahmens an, für den die Warnung [C6262](/visualstudio/code-quality/c6262) generiert wird. Der Leerraum vor `number` ist optional. Wenn dieser Parameter nicht angegeben wird, beträgt die Größe des Stapelrahmens standardmäßig 16 KB.

/ANALYZE: max_paths `number` der `number`-Parameter, der mit dieser Option verwendet wird, gibt die maximale Anzahl der zu analysierenden Codepfade an. Wenn dieser Parameter nicht angegeben wird, beträgt die Anzahl standardmäßig 256. Bei höheren Werten ist die Überprüfung gründlicher, die Analyse dauert aber möglicherweise auch länger.

/ANALYZE: nur in der Regel generiert der Compiler Code und führt nach der Ausführung der Analyse eine weitere Syntax Überprüfung durch. Mit der Option **/analyze: Only** wird dieser Code Generierungs Durchlauf deaktiviert. Dadurch wird die Analyse beschleunigt, aber Kompilierungsfehler und Warnungen, die möglicherweise von der Code Generierungs Übergabe des Compilers entdeckt wurden, werden nicht ausgegeben. Wenn das Programm Codegenerierungsfehler enthält, sind die Analyseergebnisse möglicherweise unzuverlässig; daher wird empfohlen, diese Option nur zu verwenden, wenn der Code die Syntaxüberprüfung bereits bestanden hat.

/ANALYZE: RuleSet `<file_path>.ruleset` ermöglicht Ihnen die Angabe der zu analysierenden Regelsätze, einschließlich benutzerdefinierter Regelsätze, die Sie selbst erstellen können. Wenn dieser Switch festgelegt ist, ist die Regel-Engine effizienter, da Sie vor der Ausführung nicht-Member des angegebenen Regelsatzes ausschließt. Wenn der Schalter nicht festgelegt ist, überprüft die Engine alle Regeln.

Die RuleSets, die mit Visual Studio ausgeliefert werden, finden Sie unter **%VSInstallDir%\Team Tools\Static Analysis tools\rule Sets.**

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

/ANALYZE: das Plug-in aktiviert das angegebene PREfast-Plug-in im Rahmen der Ausführung von Code Analysen.
Localespc. dll ist das Plug-in, das Parallelitäts bezogene Code Analyse Überprüfungen im Bereich der C261XX-Warnungen implementiert. Beispiel: [C26100](/visualstudio/code-quality/c26100), [C26101](/visualstudio/code-quality/c26101),..., [C26167](/visualstudio/code-quality/c26167).

Verwenden Sie zum Ausführen von "localespc. dll" Diese Compileroption: **/analyze: Plugin localespc. dll**

Um cppcorecheck. dll auszuführen, führen Sie zuerst den folgenden Befehl über eine Developer-Eingabeaufforderung aus:

```cmd
set Esp.Extensions=CppCoreCheck.dll
```

Verwenden Sie dann diese Compileroption: **/analyze: Plugin espxengine. dll**.

## <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Code Analyse für c/C++ Overview](/visualstudio/code-quality/code-analysis-for-c-cpp-overview) und [Code Analyse für c/C++ Warnungen](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Erweitern Sie den Knoten **Konfigurationseigenschaften**.

1. Erweitern Sie den Knoten **Code Analyse** .

1. Wählen Sie die Eigenschaftenseite **Allgemein** aus.

1. Ändern Sie eine oder mehrere der **Code Analyse** Eigenschaften.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>.

## <a name="see-also"></a>Siehe auch

- [MSVC-Compileroptionen](compiler-options.md)
- [Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
