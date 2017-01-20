---
title: "/analyze (Codeanalyse)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.EnablePREfast"
  - "/analyze"
  - "VC.Project.VCCLCompilerTool.PREfastAdditionalOptions"
  - "VC.Project.VCCLCompilerTool.PREfastAdditionalPlugins"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/analyze (Compileroption) [C++]"
  - "analyze (Compileroption) [C++]"
  - "-analyze (Compileroption) [C++]"
ms.assetid: 81da536a-e030-4bd4-be18-383927597d08
caps.latest.revision: 21
caps.handback.revision: "21"
ms.author: "corob"
manager: "ghogen"
---
# /analyze (Codeanalyse)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Aktiviert Codeanalyse\- und Steueroptionen.  
  
## Syntax  
  
```  
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only]  
```  
  
## Argumente  
 \/analyze  
 Aktiviert die Analyse im Standardmodus.  Die Analyseausgabe erfolgt, wie andere Fehlermeldungen auch, im Fenster **Ausgabe**.  Verwenden Sie **\/analyze\-**, um die Analyse explizit zu deaktivieren.  
  
 \/analyze:WX\-  
 Die Angabe von **\/analyze:WX\-** bedeutet, dass Codeanalysewarnungen nicht als Fehler behandelt werden, wenn Sie zum Kompilieren **\/WX** verwenden.  Weitere Informationen finden Sie unter [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won \(Warnstufe\)](../../build/reference/compiler-option-warning-level.md).  
  
 \/analyze:log `filename`  
 Ausführliche Analysergebnisse werden als XML in die von `filename` angegebene Datei geschrieben.  
  
 \/analyze:quiet  
 Deaktiviert die Analyseausgabe im Fenster **Ausgabe**.  
  
 \/analyze:stacksize `number`  
 Der mit dieser Option verwendete Parameter `number` gibt die Größe des Stapelrahmens in Byte an, für den die Warnung [C6262](../Topic/C6262.md) generiert wird.  Wenn dieser Parameter nicht angegeben wird, beträgt die Größe des Stapelrahmens standardmäßig 16 KB.  
  
 \/analyze:max\_paths `number`  
 Der mit dieser Option verwendete Parameter `number` gibt die maximale Anzahl der zu analysierenden Codepfade an.  Wenn dieser Parameter nicht angegeben wird, beträgt die Anzahl standardmäßig 256.  Bei höheren Werten ist die Überprüfung gründlicher, die Analyse dauert aber möglicherweise auch länger.  
  
 \/analyze:only  
 In der Regel generiert der Compiler Code und führt nach der Ausführung der Analyse eine erweiterte Syntaxprüfung durch.  Die Option **\/analyze:only** deaktiviert diesen Codegenerierungsdurchgang; dadurch wird zwar die Analyse beschleunigt, allerdings werden manche Compilerfehler und \-warnungen, die bei der Codegenerierung möglicherweise entdeckt worden wären, nicht ausgegeben.  Wenn das Programm Codegenerierungsfehler enthält, sind die Analyseergebnisse möglicherweise unzuverlässig; daher wird empfohlen, diese Option nur zu verwenden, wenn der Code die Syntaxüberprüfung bereits bestanden hat.  
  
## Hinweise  
 Weitere Informationen finden Sie unter [Übersicht über die Codeanalyse für C\/C\+\+](../Topic/Code%20Analysis%20for%20C-C++%20Overview.md) und [Codeanalyse für C\/C\+\+\-Warnungen](../Topic/Code%20Analysis%20for%20C-C++%20Warnings.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Erweitern Sie den Knoten **Codeanalyse**.  
  
4.  Wählen Sie die Eigenschaftenseite **Allgemein** aus.  
  
5.  Ändern Sie mindestens eine Eigenschaft unter **Codeanalyse**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)