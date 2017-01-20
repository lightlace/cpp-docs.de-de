---
title: "Syntax f&#252;r die Compilerbefehlszeile"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe-Compiler, Befehlszeilensyntax"
  - "Syntax, CL-Compilerbefehlszeile"
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Syntax f&#252;r die Compilerbefehlszeile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die CL\-Befehlszeile verwendet folgende Syntax:  
  
```  
CL [option...] file... [option | file]... [lib...] [@command-file] [/link link-opt...]  
```  
  
 Die folgende Tabelle beschreibt die Eingabe für den CL\-Befehl.  
  
|Eintrag|Bedeutung|  
|-------------|---------------|  
|*\-Option*|Eine oder mehrere [CL\-Optionen](../../build/reference/compiler-options.md).  Beachten Sie, dass alle Optionen auf alle angegebenen Quelldateien angewendet werden.  Optionen werden entweder durch einen Schrägstrich \(\/\) oder einen Halbgeviertstrich \(–\) eingeleitet.  Wenn eine Option ein Argument erhält, dann wird in der Beschreibung der Option dokumentiert, ob ein Leerzeichen zwischen Option und Argumenten erlaubt ist.  Bei Optionsnamen muss \(mit Ausnahme der **\/HELP**\-Option\) die Groß\-\/Kleinschreibung beachtet werden.  Weitere Informationen finden Sie im Abschnitt [Reihenfolge von CL\-Optionen](../../build/reference/order-of-cl-options.md).|  
|`file`|Der Name einer oder mehrerer Quelldateien, OBJ\-Dateien oder Bibliotheken.  CL kompiliert die Quelldateien und übergibt die Namen der OBJ\-Dateien und Bibliotheken an den Linker.  Weitere Informationen finden Sie unter [Syntax für Dateinamen bei CL](../../build/reference/cl-filename-syntax.md).|  
|*lib*|Ein oder mehrere Bibliotheksnamen.  CL übergibt die Namen an den Linker.|  
|*command\-file*|Eine Datei, die mehrere Optionen und Dateinamen enthält.  Weitere Informationen finden Sie unter [CL\-Befehlsdateien](../../build/reference/cl-command-files.md).|  
|*link\-opt*|Eine oder mehrere [Linkeroptionen](../../build/reference/linker-options.md).  CL übergibt diese Optionen an den Linker.|  
  
 Sie können eine beliebige Anzahl von Optionen, Datei\- und Bibliotheksnamen angeben, solange die Anzahl der Zeichen in der Befehlszeile nicht 1024 überschreitet \(eine Grenze, die das Betriebssystem vorgibt\).  
  
 Informationen über den Rückgabewert von cl.exe finden Sie unter [Rückgabewert von cl.exe](../../build/reference/return-value-of-cl-exe.md).  
  
> [!NOTE]
>  Es gibt keine Garantie dafür, dass diese Grenze von 1024 Zeichen für die Eingabe in der Befehlszeile in zukünftigen Versionen von Windows unverändert bleibt.  
  
## Siehe auch  
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)