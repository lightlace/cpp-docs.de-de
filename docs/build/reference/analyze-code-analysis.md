---
title: -analyze (Codeanalyse) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ba76ddd10866e414d9817f628c7a1aec019964de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="analyze-code-analysis"></a>/analyze (Codeanalyse)
Aktiviert Codeanalyse- und Steueroptionen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only]  
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
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Codeanalyse für C/C++-Übersicht](/visualstudio/code-quality/code-analysis-for-c-cpp-overview) und [Codeanalyse für C/C++-Warnungen](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten.  
  
3.  Erweitern Sie die **Codeanalyse** Knoten.  
  
4.  Wählen Sie die Eigenschaftenseite **Allgemein** aus.  
  
5.  Ändern Sie eine oder mehrere der **Codeanalyse** Eigenschaften.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)