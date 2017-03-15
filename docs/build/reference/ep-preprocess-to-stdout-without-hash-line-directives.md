---
title: "/EP (Vorverarbeitung an &quot;stdout&quot; ohne #line-Direktiven)"
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
  - "/ep"
  - "VC.Project.VCCLCompilerTool.GeneratePreprocessedFileNoLines"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/EP (Compileroption) [C++]"
  - "Kopieren der Präprozessorausgabe nach stdout"
  - "EP (Compileroption) [C++]"
  - "-EP (Compileroption) [C++]"
  - "Präprozessorausgabe, Kopieren nach stdout"
ms.assetid: 6ec411ae-e33d-4ef5-956e-0054635eabea
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# /EP (Vorverarbeitung an &quot;stdout&quot; ohne #line-Direktiven)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verarbeitet C\- und C\+\+\-Quelldateien vor und übermittelt die vorverarbeiteten Dateien an das Standardausgabegerät.  
  
## Syntax  
  
```  
/EP  
```  
  
## Hinweise  
 In dem Prozess werden alle Präprozessordirektiven und Makroerweiterungen ausgeführt sowie Kommentare entfernt.  Wenn Sie Kommentare in der vorverarbeiteten Ausgabe beibehalten möchten, verwenden Sie die Option [\/C \(Kommentare bei der Vorverarbeitung beibehalten\)](../../build/reference/c-preserve-comments-during-preprocessing.md) in Verbindung mit **\/EP**.  
  
 Mit der **\/EP**\-Option wird die Kompilierung unterdrückt.  Sie müssen die vorverarbeitete Datei erneut zum Kompilieren übergeben.  **\/EP** unterdrückt auch die Ausgabedateien der Optionen **\/FA**, **\/Fa** und **\/Fm**.  Weitere Informationen finden Sie unter [\/FA, \/Fa \(Listendatei\)](../../build/reference/fa-fa-listing-file.md) und [\/Fm \(Name der Zuordnungsdatei\)](../../build/reference/fm-name-mapfile.md).  
  
 Fehlermeldungen in späteren Verarbeitungsstufen beziehen sich auf die Zeilennummern der vorverarbeiteten Datei, nicht auf die Zeilen in der ursprünglichen Quelldatei.  Wenn sich Zeilennummern auf die ursprüngliche Quelldatei beziehen sollen, verwenden Sie stattdessen [\/E \(Vorverarbeitung an "stdout"\)](../../build/reference/e-preprocess-to-stdout.md).  Die Option **\/E** fügt der Ausgabe zu diesem Zweck `#line`\-Direktiven hinzu.  
  
 Um die vorverarbeitete Ausgabe mit `#line`\-Direktiven in eine Datei zu übergeben, verwenden Sie stattdessen die Option [\/P \(Vorverarbeitung in eine Datei\)](../../build/reference/p-preprocess-to-a-file.md).  
  
 Um die vorverarbeitete Ausgabe mit `#line`\-Direktiven an stdout zu übergeben, verwenden Sie **\/P** und **\/EP** zusammen.  
  
 Vorkompilierte Header können nicht mit der **\/EP**\-Option verwendet werden.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Präprozessor**.  
  
4.  Ändern Sie die Eigenschaft **Präprozessorlauf**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile*>.  
  
## Beispiel  
 Mit der folgenden Befehlszeile werden eine Vorverarbeitung von `ADD.C` durchgeführt, die Kommentare übernommen und das Ergebnis auf dem Standardausgabegerät angezeigt:  
  
```  
CL /EP /C ADD.C  
```  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)