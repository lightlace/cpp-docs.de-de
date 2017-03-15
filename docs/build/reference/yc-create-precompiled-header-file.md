---
title: "/Yc (Datei der vorkompilierten Header erstellen) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.UsePrecompiledHeader"
  - "/yc"
  - "VC.Project.VCCLWCECompilerTool.PrecompiledHeaderThrough"
  - "VC.Project.VCCLWCECompilerTool.UsePrecompiledHeader"
  - "VC.Project.VCCLCompilerTool.PrecompiledHeaderThrough"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pch-Dateien, Erstellen"
  - "/Yc (Compileroption) [C++]"
  - "PCH-Dateien, Erstellen"
  - "Vorkompilierte Headerdateien, Erstellen"
  - "Yc (Compileroption) [C++]"
  - "-Yc (Compileroption) [C++]"
ms.assetid: 47c2e555-b4f5-46e6-906e-ab5cf21f0678
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /Yc (Datei der vorkompilierten Header erstellen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Weist den Compiler an, eine vorkompilierte Headerdatei \(.pch\) zu erstellen, die den Zustand der Kompilierung zu einem bestimmten Zeitpunkt darstellt.  
  
## Syntax  
  
```  
/Yc[filename]  
```  
  
## Argumente  
 `filename`  
 Gibt eine Headerdatei \(H\-Datei\) an  Wenn dieses Argument verwendet wird, kompiliert der Compiler den gesamten Code bis einschließlich der H\-Datei.  
  
## Hinweise  
 Wenn **\/Yc** ohne Argument angegeben wird, kompiliert der Compiler den gesamten Code bis zum Ende der Basisquelldatei oder bis zu einer Stelle in der Quelldatei, an der [hdrstop](../../preprocessor/hdrstop.md) auftritt.  Die erzeugte PCH\-Datei hat denselben Basisnamen wie die Basisquelldatei, es sei denn, Sie geben mithilfe des **hdrstop**\-Pragmas oder der **\/Fp**\-Option einen anderen Dateinamen an.  
  
 Der vorkompilierte Code wird in einer Datei gespeichert, deren Namen aus dem Basisnamen der durch die **\/Yc**\-Option angegebenen Datei und der Erweiterung .pch gebildet wird.  Sie können auch die [\/Fp \(Name der PCH\-Datei\)](../../build/reference/fp-name-dot-pch-file.md)\-Option zur Angabe eines Namens für die vorkompilierte Headerdatei verwenden.  
  
 Wenn Sie **\/Yc**`filename` verwenden, kompiliert der Compiler den gesamten Code bis einschließlich der zur nachfolgenden Verwendung mit der **\/Yu**\-Option angegebenen Datei.  
  
 Wenn die **\/Yc**`filename`\-Option und die [\/Yu \(Vorkompilierte Headerdatei verwenden\)](../../build/reference/yu-use-precompiled-header-file.md)`filename`\-Option in derselben Befehlszeile auftreten und auf denselben Dateinamen verweisen oder diesen implizieren, hat **\/Yc**`filename` Vorrang.  Diese Funktion vereinfacht das Schreiben von Makefiles.  
  
 Weitere Informationen zu vorkompilierten Headern finden Sie unter:  
  
-   [\/Y \(Vorkompilierte Header\)](../../build/reference/y-precompiled-headers.md)  
  
-   [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md)  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Wählen Sie eine CPP\-Datei aus.  Die H\-Datei, die die vorkompilierten Headerinformationen enthält, muss in der CPP\-Datei mit \#include eingeschlossen werden.  Die **\/Yc**\-Einstellung des Projekts kann auf Dateiebene überschrieben werden.  
  
2.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
3.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
4.  Klicken Sie auf die Eigenschaftenseite **Vorkompilierte Header**.  
  
5.  Ändern Sie die Eigenschaft **PCH durch Datei erstellen** oder **Erstellen\/Verwenden eines vorkompilierten Headers**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Weitere Informationen finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough*> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader*>.  
  
## Beispiel  
 Betrachten Sie folgenden Code:  
  
```  
#include <afxwin.h>   // Include header for class library  
#include "resource.h" // Include resource definitions  
#include "myapp.h"    // Include information specific to this app  
...  
```  
  
 Wenn der Code mit dem `CL /YcMYAPP.H PROG.CPP`\-Befehl kompiliert wird, wird vom Compiler die gesamte Vorverarbeitung für AFXWIN.h, RESOURCE.h und MYAPP.h in einer vorkompilierten Headerdatei mit dem Namen MYAPP.pch gespeichert.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)