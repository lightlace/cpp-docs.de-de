---
title: "/doc (Verarbeiten von Dokumentationskommentaren) (C/C++)"
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
  - "VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles"
  - "/doc"
  - "VC.Project.VCCLCompilerTool.XMLDocumentationFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/doc (Compileroption) [C++]"
  - "Kommentare, C++-Code"
  - "-doc (Compileroption) [C++]"
  - "XML-Dokumentation, Kommentare in Quelldateien"
ms.assetid: b54f7e2c-f28f-4f46-9ed6-0db09be2cc63
caps.latest.revision: 17
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# /doc (Verarbeiten von Dokumentationskommentaren) (C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Durch diese Option werden vom Compiler Dokumentationskommentare in Quellcodedateien verarbeitet, und für jede Quellcodedatei mit Dokumentationskommentaren wird eine XDC\-Datei erstellt.  
  
## Syntax  
  
```  
/doc[name]  
```  
  
## Argumente  
 `name`  
 Der Name der XDC\-Datei, die vom Compiler erstellt wird.  Nur gültig, wenn bei der Kompilierung eine CPP\-Datei übergeben wird.  
  
## Hinweise  
 Die XDC\-Dateien werden mit xdcmake.exe in eine XML\-Datei umgewandelt.  Weitere Informationen finden Sie unter [XDCMake\-Verweis](../../ide/xdcmake-reference.md).  
  
 Sie können den Quellcodedateien Dokumentationskommentare hinzufügen.  Weitere Informationen finden Sie unter [Empfohlene Tags für Dokumentationskommentare](../../ide/recommended-tags-for-documentation-comments-visual-cpp.md).  
  
 **\/doc** ist nicht mit **\/clr:oldSyntax** kompatibel.  Weitere Informationen finden Sie unter [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Um die erzeugte XML\-Datei in IntelliSense zu verwenden, weisen Sie der XML\-Datei denselben Namen zu wie der Assembly, die unterstützt werden soll, und legen die XML\-Datei in dem Verzeichnis ab, in dem sich auch die Assembly befindet.  Wenn im Visual Studio\-Projekt auf die Assembly verwiesen wird, wird die entsprechende XML\-Datei ebenfalls gefunden.  Weitere Informationen finden Sie unter [Verwenden von IntelliSense](../Topic/Using%20IntelliSense.md) und [Anzeigen von XML\-Codekommentaren](../Topic/Supplying%20XML%20Code%20Comments.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Erweitern Sie den Knoten **C\/C\+\+**.  
  
4.  Wählen Sie die Eigenschaftenseite für die **Ausgabedateien** aus.  
  
5.  Ändern Sie die Eigenschaft **XML\-Dokumentationsdateien generieren**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GenerateXMLDocumentationFiles*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)