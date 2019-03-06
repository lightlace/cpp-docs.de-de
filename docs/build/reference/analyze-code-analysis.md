---
title: /analyze (Codeanalyse)
ms.date: 04/26/2018
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
ms.openlocfilehash: 057fabe9612f84af07649d7a4f7bbf6d83e01f6c
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57426211"
---
# <a name="analyze-code-analysis"></a>/analyze (Codeanalyse)

Aktiviert Codeanalyse- und Steueroptionen.

## <a name="syntax"></a>Syntax

```cmd
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only][:ruleset]
```

## <a name="arguments"></a>Argumente

/ analyze-wird auf der Analyse im Standardmodus. Analyseausgabe erfolgt auf die **Ausgabe** Fenster wie andere Fehlermeldungen. Verwendung **/ analyze-** Analyse explizit zu deaktivieren.

/ analyze: WX-Angabe **/ analyze: WX-** bedeutet, die codeanalysewarnungen nicht als Fehler behandelt werden, wenn Sie bei der Kompilierung **/WX**. Weitere Informationen finden Sie unter [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX (Warnstufe)](../../build/reference/compiler-option-warning-level.md).

/ analyze: Log `filename` ausführliche analysergebnisse werden als XML geschrieben, um die Datei, die angegeben wird `filename`.

/ analyze: quiet aktiviert die Analyseausgabe der **Ausgabe** Fenster.

/ analyze: Stacksize `number` der `number` mit dieser Option verwendete Parameter gibt die Größe in Bytes des Stapelrahmens für den die Warnung [C6262](/visualstudio/code-quality/c6262) wird generiert. Wenn dieser Parameter nicht angegeben wird, beträgt die Größe des Stapelrahmens standardmäßig 16 KB.

/ analyze: Max_paths `number` der `number` mit dieser Option verwendete Parameter gibt die maximale Anzahl der Codepfade analysiert werden. Wenn dieser Parameter nicht angegeben wird, beträgt die Anzahl standardmäßig 256. Bei höheren Werten ist die Überprüfung gründlicher, die Analyse dauert aber möglicherweise auch länger.

/ analyze: nur in der Regel der Compiler Code generiert und eine erweiterte syntaxprüfung durch ist, nachdem sie den Analyzer ausgeführt wird. Die **/ analyze: nur** Option werden diese Durchlauf der codegenerierung deaktiviert; dies Analyse beschleunigt, aber Kompilierungsfehler und Warnungen, die von den Durchlauf der codegenerierung des Compilers möglicherweise entdeckt worden wären, werden nicht ausgegeben. Wenn das Programm Codegenerierungsfehler enthält, sind die Analyseergebnisse möglicherweise unzuverlässig; daher wird empfohlen, diese Option nur zu verwenden, wenn der Code die Syntaxüberprüfung bereits bestanden hat.

/ analyze: Ruleset `<file_path>.ruleset` ermöglicht es Ihnen, die angeben, welche von Regelsätzen zum Analysieren, einschließlich von benutzerdefinierten Regelsätzen, die Sie selbst erstellen können. Wenn diese Option festgelegt ist, ist die Regel-Engine effizienter, da es sich um nicht-Mitglieder der angegebenen Regel legen Sie vor der Ausführung schließt. Wenn der Schalter nicht festgelegt ist, überprüft die Engine alle Regeln.

Die Rulesets aus dem Lieferumfang von Visual Studio finden Sie im **%VSINSTALLDIR%\Team Tools\Static Analysis Tools\Rule legt.**

Der folgende Beispiel benutzerdefinierten Regelsatz weist die Regel-Engine für C6001 und C26494 überprüfen. Sie können diese Datei platzieren, an einer beliebigen Stelle solange hat einem `.ruleset` -Erweiterung, und Sie geben den vollständigen Pfad im Argument.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description=" " ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

/ analyze:-Plug-in der angegebenen PREfast-Plug-in ermöglicht, als Teil der Codeanalyse ausgeführt wird.
LocalEspC.dll ist, dass das Plug-in, das gleichzeitige Codeanalyse implementiert in den Bereich der C261XX Warnungen überprüft. Z. B. [C26100](/visualstudio/code-quality/c26100), [C26101](/visualstudio/code-quality/c26101),..., [C26167](/visualstudio/code-quality/c26167).

Um LocalEspC.dll auszuführen, verwenden Sie diese Compileroption: **/ analyze: Plugin LocalEspC.dll**

Um CppCoreCheck.dll auszuführen, müssen Sie zunächst führen Sie mit diesem Befehl an einer Developer-Eingabeaufforderung aus:

```cmd
set Esp.Extensions=CppCoreCheck.dll
```

Klicken Sie dann verwenden Sie diese Compileroption: **/ analyze: Plugin EspXEngine.dll**.

## <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Codeanalyse für C/C++-Übersicht](/visualstudio/code-quality/code-analysis-for-c-cpp-overview) und [Codeanalyse für C/C++-Warnungen](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Erweitern Sie den Knoten **Konfigurationseigenschaften**.

1. Erweitern Sie die **Codeanalyse** Knoten.

1. Wählen Sie die Eigenschaftenseite **Allgemein** aus.

1. Ändern Sie eine oder mehrere der **Codeanalyse** Eigenschaften.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>.

## <a name="see-also"></a>Siehe auch

- [Compileroptionen](../../build/reference/compiler-options.md)
- [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
