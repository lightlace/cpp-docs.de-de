---
title: "/Z7, /Zi, /ZI (Debuginformationsformat)"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.DebugInformationFormat"
  - "/zi"
  - "/z7"
  - "VC.Project.VCCLWCECompilerTool.DebugInformationFormat"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C7-Kompatibel (Compileroption) [C++]"
  - "-Zl (Compileroption) [C++]"
  - "Debuginformationsformat (Compileroption)"
  - "ZI (Compileroption)"
  - "-Zi (Compileroption) [C++]"
  - "/ZI-Compileroption [C++]"
  - "Z7-Compileroption [C++]"
  - "Debuggen [C++], Debuginformationsdateien"
  - "Zi (Compileroption) [C++]"
  - "none (Compileroption) [C++]"
  - "/Zi (Compileroption) [C++]"
  - "Programmdatenbank (Compileroption) [C++]"
  - "Vollständige symbolische Debuginformationen"
  - "/Z7-Compileroption [C++]"
  - "Nur Zeilennummern (Compileroption) [C++]"
  - "cl.exe (Compiler), Debugoptionen"
  - "-Z7-Compileroption [C++]"
ms.assetid: ce9fa7e1-0c9b-47e3-98ea-26d1a16257c8
caps.latest.revision: 21
caps.handback.revision: "18"
ms.author: "corob"
manager: "ghogen"
---
# /Z7, /Zi, /ZI (Debuginformationsformat)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wählen Sie den Typ der Debuginformationen aus, der für Ihr Programm erstellt wird, und ob diese Informationen als Objektdateien \(OBJ\) oder in einer Programmdatenbank \(PDB\) gespeichert werden sollen.  
  
## Syntax  
  
```  
/Z{7|i|I}  
```  
  
## Hinweise  
 Die Optionen werden in der folgenden Tabelle beschrieben.  
  
 Kein  
 Erzeugt keine Debuginformationen, sodass die Kompilierung schneller ist.  
  
 **\/Z7**  
 Generiert eine OBJ\-Datei mit vollständigen symbolischen Debuginformationen zur Verwendung mit dem Debugger.  Zu den symbolischen Debuginformationen gehören die Namen und Typen von Variablen sowie Funktionen und Zeilennummern.  Es wird keine PDB\-Datei generiert.  
  
 Für die Verteiler von Drittanbieterbibliotheken ist es von Vorteil, keine PDB\-Datei zu haben.  Die OBJ\-Dateien für die vorkompilierten Header sind jedoch während der Linkphase und für das Debuggen erforderlich.  Wenn die PCH\-Objektdateien nur Typinformationen \(und keinen Code\) enthalten, müssen Sie außerdem mit [\/Yl \(PCH\-Verweis für Debugbibliothek einfügen\)](../../build/reference/yl-inject-pch-reference-for-debug-library.md) kompilieren.  
  
 **\/Zi**  
 Erstellt eine Programmdatenbank \(PDB\), die Typinformationen und symbolische Debuginformationen für die Verwendung mit dem Debugger enthält.  Zu den symbolischen Debuginformationen gehören die Namen und Typen von Variablen sowie Funktionen und Zeilennummern.  
  
 **\/Zi** hat keinen Einfluss auf Optimierungen.  **\/Zi** impliziert aber **\/debug**. Weitere Informationen finden Sie unter [\/DEBUG \(Debuginfo generieren\)](../../build/reference/debug-generate-debug-info.md).  
  
 Typinformationen werden in der PDB\-Datei, nicht in der OBJ\-Datei abgelegt.  
  
 Sie können [\/Gm \(Minimale Neuerstellung aktivieren\)](../../build/reference/gm-enable-minimal-rebuild.md) mit **\/Zi** verwenden. **\/Gm** ist jedoch nicht verfügbar, wenn Sie mit **\/Z7** kompilieren.  
  
 Beim Kompilieren mit **\/Zi** und **\/clr** wird das <xref:System.Diagnostics.DebuggableAttribute>\-Attribut nicht in den Assemblymetadaten abgelegt. Sie müssen es im Quellcode angeben, um es zu verwenden.  Dieses Attribut kann Auswirkungen auf die Laufzeitleistung der Anwendung haben.  Weitere Informationen zu den Auswirkungen des Debuggable\-Attributs auf die Leistung und möglichen Änderungen der Leistungsauswirkungen finden Sie unter [Erleichtern des Debuggens für ein Abbild](../Topic/Making%20an%20Image%20Easier%20to%20Debug.md).  
  
 **\/ZI**  
 Erstellt, wie oben beschrieben, eine Programmdatenbank in einem Format, das die Funktion "Bearbeiten und Fortfahren" unterstützt.  Wenn Sie mit "Bearbeiten und Fortfahren" debuggen möchten, müssen Sie diese Option verwenden.  Da die meisten Optimierungen nicht mit "Bearbeiten und Fortfahren" kompatibel sind, werden bei Verwendung von **\/ZI** alle `#pragma optimize`\-Anweisungen im Code deaktiviert.  
  
 **\/ZI** bewirkt, dass [\/Gy \(Funktionslevel\-Linking aktivieren\)](../../build/reference/gy-enable-function-level-linking.md) und [\/FC \(Vollständiger Pfad der Quellcodedatei in Diagnostik\)](../../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md) in der Kompilierung verwendet werden.  
  
 **\/ZI** ist nicht mit [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md) kompatibel.  
  
> [!NOTE]
>  **\/ZI** ist nur im Compiler verfügbar, der auf x86 abzielt. Diese Compileroption steht nicht in Compilern zur Verfügung, die auf [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] oder ARM\-Prozessoren abzielen.  
  
 Die Programmdatenbank wird vom Compiler mit "*project*.pdb" benannt.  Wenn Sie eine Datei ohne ein Projekt kompilieren, wird vom Compiler eine Datenbank mit dem Namen "VC*x*0.pdb" erstellt, wobei *x* die verwendete Hauptversion von [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] ist.  Der Compiler bettet den Namen der PDB in jede mit dieser Option erstellte OBJ\-Datei ein und verweist so den Debugger auf den Standort von symbolischen Informationen und Zeilennummern.  Mit dieser Option werden die OBJ\-Dateien kleiner, weil die Debuginformationen nicht in OBJ\-Dateien, sondern in der PDB\-Datei gespeichert werden.  
  
 Wenn Sie eine Bibliothek von Objekten erstellen, die mit dieser Option kompiliert worden sind, muss die zugeordnete PDB\-Datei verfügbar sein, wenn die Bibliothek zu einem Programm gelinkt wird.  Daher müssen Sie auch die PDB weitergeben, wenn Sie die Bibliothek weitergeben.  
  
 Zum Erstellen einer Bibliothek mit Debuginformationen ohne Verwendung von PDB\-Dateien wählen Sie die Option "C 7.0\-kompatibel" \(**\/Z7**\) des Compilers.  Wenn Sie die Optionen "Vorkompilierte Header" verwenden, werden Debuginformationen sowohl für den vorkompilierten Header als auch den restlichen Quellcode in der PDB abgelegt.  Die **\/Yd**\-Option wird ignoriert, wenn die Programmdatenbank\-Option angegeben ist.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Allgemein**.  
  
4.  Ändern Sie die Eigenschaft **Debuginformationsformat**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)