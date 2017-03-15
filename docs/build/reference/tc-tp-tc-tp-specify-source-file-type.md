---
title: "/Tc, /Tp, /TC, /TP (Typ der Quelldatei angeben) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.CompileAs"
  - "VC.Project.VCCLCompilerTool.CompileAs"
  - "/Tp"
  - "/tc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Tc (Compileroption) [C++]"
  - "/Tp (Compileroption) [C++]"
  - "Quelldateien, Angeben für den Compiler"
  - "Tc (Compileroption) [C++]"
  - "-Tc (Compileroption) [C++]"
  - "Tp (Compileroption) [C++]"
  - "-Tp (Compileroption) [C++]"
ms.assetid: 7d9d0a65-338b-427c-8b48-fff30e2f9d2b
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /Tc, /Tp, /TC, /TP (Typ der Quelldatei angeben)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit der Option **\/Tc** kann angegeben werden, dass `filename` eine C\-Quelldatei ist, auch wenn sie nicht über die Erweiterung .c verfügt.  Die Option **\/Tp** gibt an, dass `filename` eine C\+\+\-Quelltextdatei ist, selbst wenn sie nicht über eine .cpp\- oder .cxx\-Erweiterung verfügt.  Ein Leerzeichen zwischen der Option und `filename` ist optional.  Jede Option gibt eine Datei an; zur Angabe weiterer Dateien wiederholen Sie die Option.  
  
 **\/TC** und **\/TP** sind globale Varianten von **\/Tc** und **\/Tp**.  Sie weisen den Compiler an, alle in der Befehlszeile genannten Dateien als C\-Quelltextdateien \(**\/TC**\) oder C\+\+\-Quelltextdateien \(**\/TP**\) zu behandeln, unabhängig von deren relativer Position zur Option in der Befehlszeile.  Diese globalen Optionen können für einzelne Dateien mit **\/Tc** oder **\/Tp** überschrieben werden.  
  
## Syntax  
  
```  
/Tcfilename  
/Tpfilename  
/TC  
/TP  
```  
  
## Argumente  
 `filename`  
 eine C\- oder C\+\+\-Quelldatei.  
  
## Hinweise  
 Standardmäßig nimmt der Befehl **CL** an, dass Dateien mit der Erweiterung **.c** C\-Quelltextdateien und Dateien mit den Erweiterungen **.cpp** oder **.cxx** C\+\+\-Quelltextdateien sind.  
  
 Wenn entweder **TC** oder **Tc** \- Option angegeben wird, wird jede der Spezifikation [\/Zc:wchar\_t \(wchar\_t ist der systemeigene Typ\)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) Option ignoriert.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Erweitert**.  
  
4.  Ändern Sie die Eigenschaft **Kompilierungsart**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs*>.  
  
## Beispiele  
 Die nachfolgende **CL**\-Befehlszeile gibt an, dass **MAIN.c**, **TEST.prg** und **COLLATE.prg** C\-Quelltextdateien sind.  **CL** erkennt **PRINT.prg** nicht.  
  
```  
CL MAIN.C /TcTEST.PRG /TcCOLLATE.PRG PRINT.PRG  
```  
  
 Die folgende **CL**\-Befehlszeile legt fest, dass **TEST1.c**, **TEST2.cxx**, **TEST3.huh** und **TEST4.o** als C\+\+\-Dateien kompiliert werden und dass **TEST5.z** als C\-Datei kompiliert wird.  
  
```  
CL TEST1.C TEST2.CXX TEST3.HUH TEST4.O /Tc TEST5.Z /TP  
```  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)