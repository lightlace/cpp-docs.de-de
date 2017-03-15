---
title: "/FS (Erzwingen synchroner PDB-Schreibvorg&#228;nge) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/FS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "-FS (Compileroption) [C++]"
  - "/FS (Compileroption) [C++]"
ms.assetid: b2caaffe-f6e1-4963-b068-648f06b105e0
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /FS (Erzwingen synchroner PDB-Schreibvorg&#228;nge)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erzwingt, dass Schreibvorgänge in die Programmdatenbank \(PDB\) – erstellt durch [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) oder [\/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) – von MSPDBSRV.EXE serialisiert werden.  
  
## Syntax  
  
```  
/FS  
```  
  
## Hinweise  
 Wenn **\/Zi** oder **\/ZI** angegeben wird, verhindert der Compiler standardmäßig, dass Typinformationen und symbolische Debuginformationen in PDB\-Dateien geschrieben werden.  Dadurch kann der Compiler bei einer großen Anzahl von Typen die Typinformationen erheblich schneller generieren.  Wenn ein anderer Prozess, beispielsweise ein Antivirenprogramm, die PDB Datei vorübergehend sperrt, können Schreibvorgänge des Compiler möglicherweise nicht ausgeführt werden, sodass ein schwerer Fehler auftritt.  Dieses Problem kann auch auftreten, wenn mehrere Kopien von cl.exe auf dieselbe PDB Datei zugreifen. Das kann der Fall sein, wenn die Projektmappe unabhängige Projekte enthält, welche die gleichen Zwischenverzeichnisse oder Ausgabeverzeichnisse verwenden, während parallele Builds aktiviert sind.  Die **\/FS**\-Compileroption verhindert, dass der Compiler die PDB\-Datei sperrt, und erzwingt die Umleitung von Schreibvorgängen über MSPDBSRV.EXE, das den Zugriff serialisiert.  Dadurch werden aber nicht alle Fehler verhindert, die auftreten können, wenn mehrere Instanzen von cl.exe gleichzeitig auf die PDB\-Datei zugreifen, und zudem dauern Builds erheblich länger.  Es empfiehlt sich, die Projektmappe so zu ändern, dass unabhängige Projekte in getrennte Zwischen\- und Ausgabeorte schreiben, oder eines der Projekte von den anderen abhängig zu machen, um serialisierte Projekt\-Builds zu erzwingen.  
  
 Die [\/MP](../../build/reference/mp-build-with-multiple-processes.md)\-Option aktiviert standardmäßig **\/FS**.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie den Ordner **C\/C\+\+** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Befehlszeile** aus.  
  
4.  Ändern Sie die Eigenschaft **Zusätzliche Optionen** so, dass `/FS` eingeschlossen wird, und wählen Sie dann **OK**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)