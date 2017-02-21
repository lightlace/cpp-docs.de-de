---
title: "/Yl (PCH-Verweis f&#252;r Debugbibliothek einf&#252;gen) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/yi"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Yl (Compileroption) [C++]"
  - "Yl (Compileroption) [C++]"
  - "-Yl (Compileroption) [C++]"
ms.assetid: 8e4a396a-6790-4a9f-8387-df015a3220e7
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# /Yl (PCH-Verweis f&#252;r Debugbibliothek einf&#252;gen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Option wird verwendet, wenn das Erstellen einer Bibliothek mit Debuginformationen fehlschlägt, die vorkompilierte Header verwendet.  
  
## Syntax  
  
```  
/Ylsymbol  
```  
  
```  
/Yl-  
```  
  
## Argumente  
 `symbol`  
 ein beliebiges Symbol, das im Objektmodul gespeichert wird.  
  
 \-  
 Ein Minuszeichen \(\-\) dass explizit die Compileroption **\/Yl** deaktiviert.  
  
## Hinweise  
 Standardmäßig verwendet der Compiler die **\/Yl** \- Option ohne anzugeben \( *symbol*\).  Die Option **\/Yl** aktiviert den Debugger, um vollständige Informationen über Typen abzurufen.  **\/Yl\-** deaktiviert das Standardverhalten.  
  
 Wenn Sie ein Modul mit **\/Yc** und **\/Yl**`symbol` kompilieren, erstellt der Compiler ein Symbol, wie das Folgende: \_\_@@\_PchSym\_@00@...@`symbol`. Es wird im Objektmodul gespeichert. Die Auslassungszeichen \(...\) stehen hierbei für eine vom Linker generierte Zeichenfolge.  Jede mit diesem vorkompilierten Header kompilierte Quelldatei bezieht sich auf das angegebene Symbol. Dies bewirkt, dass das Objektmodul und die dazugehörigen Debuginformationen aus der Bibliothek vom Linker eingebunden werden.  
  
 Die Verwendung dieser Option verursacht möglicherweise LNK1211.  Wenn Sie die Optionen [\/Yc \(Datei der vorkompilierten Header erstellen\)](../../build/reference/yc-create-precompiled-header-file.md) und [\/Z7, \/Zi, \/ZI \(Debuginformationsformat\)](../../build/reference/z7-zi-zi-debug-information-format.md) auswählen, erstellt der Compiler eine vorkompilierte Headerdatei mit Debuginformationen.  Ein Fehler kann auftreten, wenn Sie den vorkompilierten Header in einer Bibliothek speichern, mit der Bibliothek ein Objektmodul erstellen und der Quellcode keinen Verweis auf die in der vorkompilierten Headerdatei definierten Funktionen enthält.  
  
 Geben Sie beim Erstellen einer vorkompilierten Headerdatei, die keine Funktionsdefinitionen enthält, **\/Yl**`symbol` an, um das Problem zu lösen. `symbol` ist der Name eines beliebigen Symbols in der Bibliothek.  Diese Option weist den Compiler an, die Debuginformation in der vorkompilierten Headerdatei zu speichern.  
  
 Weitere Informationen zu vorkompilierten Headern finden Sie unter:  
  
-   [\/Y \(Vorkompilierte Header\)](../../build/reference/y-precompiled-headers.md)  
  
-   [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md)  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)