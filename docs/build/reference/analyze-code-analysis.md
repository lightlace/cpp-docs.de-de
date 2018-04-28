---
title: -analyze (Codeanalyse) | Microsoft Docs
ms.custom: ''
ms.date: 04/26/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.EnablePREfast
- /analyze
- VC.Project.VCCLCompilerTool.PREfastAdditionalOptions
- VC.Project.VCCLCompilerTool.PREfastAdditionalPlugins
dev_langs:
- C++
helpviewer_keywords:
- /analyze compiler option [C++]
- -analyze compiler option [C++]
- analyze compiler option [C++]
ms.assetid: 81da536a-e030-4bd4-be18-383927597d08
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f706c3ff32635384766ac2c028cc0e5096118b8
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="analyze-code-analysis"></a>/analyze (Codeanalyse)

Aktiviert Codeanalyse- und Steueroptionen.

## <a name="syntax"></a>Syntax

```cmd
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only][:ruleset]
```

## <a name="arguments"></a>Argumente

 /analyze  
 Aktiviert die Analyse im Standardmodus. Analyseausgabe der **Ausgabe** wie andere Fehlermeldungen im Fenster. Verwendung **/ analyze-** Analyse explizit zu deaktivieren.

 /analyze:WX-  
 Angeben von **/ analyze: WX -** bedeutet, die codeanalysewarnungen nicht als Fehler behandelt werden, wenn Sie bei der Kompilierung **/WX**. Weitere Informationen finden Sie unter [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX (Warnstufe)](../../build/reference/compiler-option-warning-level.md).

 /analyze:log `filename`  
 Ausführliche Analysergebnisse werden als XML in die von `filename` angegebene Datei geschrieben.

 /analyze:quiet  
 Aktiviert die Analyseausgabe der **Ausgabe** Fenster.

 /analyze:stacksize `number`  
 Die `number` mit dieser Option verwendete Parameter gibt die Größe in Bytes, des Stapelrahmens für den die Warnung [C6262](/visualstudio/code-quality/c6262) wird generiert. Wenn dieser Parameter nicht angegeben wird, beträgt die Größe des Stapelrahmens standardmäßig 16 KB.

 /analyze:max_paths `number`  
 Der mit dieser Option verwendete Parameter `number` gibt die maximale Anzahl der zu analysierenden Codepfade an. Wenn dieser Parameter nicht angegeben wird, beträgt die Anzahl standardmäßig 256. Bei höheren Werten ist die Überprüfung gründlicher, die Analyse dauert aber möglicherweise auch länger.

 /analyze:only  
 In der Regel generiert der Compiler Code und führt nach der Ausführung der Analyse eine erweiterte Syntaxprüfung durch. Die **/ analyze: nur** Option deaktiviert diesen; dies Analyse beschleunigt aber Kompilierungsfehler und Warnungen, die durch die Übergabe des Code-Generierung des Compilers ermittelt wurden möglicherweise nicht ausgegeben. Wenn das Programm Codegenerierungsfehler enthält, sind die Analyseergebnisse möglicherweise unzuverlässig; daher wird empfohlen, diese Option nur zu verwenden, wenn der Code die Syntaxüberprüfung bereits bestanden hat.

 / analyze: Ruleset `<file_path>.ruleset`  
Ermöglicht es Ihnen, um anzugeben, welche Regel legt fest, um zu analysieren, einschließlich von benutzerdefinierten Regelsätzen, dass Sie selbst erstellen können. Wenn diese Option festgelegt ist, ist das Regelmodul effizienter, da er nicht Mitglieder der angegebenen Regel legen Sie vor der Ausführung schließt. Wenn der Schalter nicht festgelegt ist, überprüft das Modul alle Regeln.

Die Rulesets, die im Lieferumfang von Visual Studio finden Sie im **%VSINSTALLDIR%\Team Tools\Static Analysis Tools\Rule Sätze.**

Das folgende Beispiel benutzerdefinierten Regelsatz weist das Regelmodul für C6001 und C26494 überprüfen. Sie können diese Datei platzieren, an einer beliebigen Stelle solange es hat eine `.ruleset` -Erweiterung, und Sie den vollständigen Pfad im Argument bereitzustellen.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description=" " ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

/ analyze:-Plug-in  
Die angegebene PREfast-Plug-Ins ermöglicht, als Teil der Codeanalyse ausgeführt wird. LocalEspC.dll ist, dass das Plug-in, die Parallelität bezogene Codeanalyse in den Bereich der C261XX Warnungen überprüft. Beispielsweise [C26100](/visualstudio/code-quality/c26100), [C26101](/visualstudio/code-quality/c26101),..., [C26167](/visualstudio/code-quality/c26167).

Um LocalEspC.dll auszuführen, verwenden Sie diese Compileroption: **/ analyze: Plug-in LocalEspC.dll**

Um CppCoreCheck.dll auszuführen, führen Sie zunächst diesen Befehl über eine Developer-Eingabeaufforderung:

```cmd
set Esp.Extensions=CppCoreCheck.dll
```

Verwenden Sie diese Compileroption: **/ analyze: Plug-in EspXEngine.dll**.

## <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Codeanalyse für C/C++-Übersicht](/visualstudio/code-quality/code-analysis-for-c-cpp-overview) und [Codeanalyse für C/C++-Warnungen](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Erweitern Sie die **Konfigurationseigenschaften** Knoten.

1. Erweitern Sie die **Codeanalyse** Knoten.

1. Wählen Sie die Eigenschaftenseite **Allgemein** aus.

1. Ändern Sie eine oder mehrere der **Codeanalyse** Eigenschaften.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>.

## <a name="see-also"></a>Siehe auch

- [Compileroptionen](../../build/reference/compiler-options.md)
- [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)