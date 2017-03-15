---
title: "/P (Vorverarbeitung in eine Datei) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.GeneratePreprocessedFile"
  - "/p"
  - "VC.Project.VCCLWCECompilerTool.GeneratePreprocessedFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/P (Compileroption) [C++]"
  - "Ausgabedateien, Präprozessor"
  - "P (Compileroption) [C++]"
  - "-P (Compileroption) [C++]"
  - "Vorverarbeiten von Ausgabedateien"
ms.assetid: 123ee54f-8219-4a6f-9876-4227023d83fc
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /P (Vorverarbeitung in eine Datei)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verarbeitet C\- und C\+\+\-Quelldateien vor und schreibt die vorverarbeitete Ausgabe in eine Datei.  
  
## Syntax  
  
```  
/P  
```  
  
## Hinweise  
 Die Datei hat denselben Basisnamen wie die Quelldatei und trägt die Erweiterung ".i".  In dem Prozess werden alle Präprozessordirektiven und Makroerweiterungen ausgeführt sowie Kommentare entfernt.  Um Kommentare in der vorverarbeiteten Ausgabe zu erhalten, verwenden Sie die Option [\/C \(Kommentare bei der Vorverarbeitung beibehalten\)](../../build/reference/c-preserve-comments-during-preprocessing.md) zusammen mit **\/P**.  
  
 **\/P** fügt der Ausgabe `#line`\-Direktiven am Anfang und Ende jeder eingeschlossenen Datei sowie vor und hinter den Zeilen hinzu, die von den Präprozessordirektiven zur bedingten Kompilierung entfernt wurden.  Diese Direktiven ändern die Zeilennummerierung der vorverarbeiteten Datei.  Deshalb beziehen sich Fehlermeldungen in späteren Verarbeitungsstufen auf die Zeilennummern der ursprünglichen Quelldatei, nicht auf die Zeilen in der vorverarbeiteten Datei.  Verwenden Sie die Optionen [\/EP \(Vorverarbeitung an "stdout" ohne \#line\-Direktiven\)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) und **\/P**, um die Erstellung von `#line`\-Direktiven zu unterdrücken.  
  
 Mit der **\/P**\-Option wird die Kompilierung unterdrückt.  Auch bei Verwendung von [\/Fo \(Name der Objektdatei\)](../../build/reference/fo-object-file-name.md) wird keine OBJ\-Datei erzeugt.  Sie müssen die vorverarbeitete Datei erneut zum Kompilieren übergeben.  **\/P** unterdrückt auch die Ausgabedateien der Optionen **\/FA**, **\/Fa** und **\/Fm**.  Weitere Informationen finden Sie unter [\/FA, \/Fa \(Listendatei\)](../../build/reference/fa-fa-listing-file.md) und [\/Fm \(Name der Zuordnungsdatei\)](../../build/reference/fm-name-mapfile.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Präprozessor**.  
  
4.  Ändern Sie die Eigenschaft **Präprozessorlauf**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile*>.  
  
## Beispiel  
 Mit der folgenden Befehlszeile werden eine Vorverarbeitung von `ADD.C` durchgeführt, die Kommentare übernommen, `#line`\-Direktiven hinzugefügt und das Ergebnis in die Datei `ADD.I` geschrieben:  
  
```  
CL /P /C ADD.C  
```  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [\/Fi \(Ausgabedateiname vorverarbeiten\)](../../build/reference/fi-preprocess-output-file-name.md)