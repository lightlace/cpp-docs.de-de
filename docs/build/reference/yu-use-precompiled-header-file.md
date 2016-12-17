---
title: "/Yu (Vorkompilierte Headerdatei verwenden)"
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
  - "/yu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pch-Dateien, Verwenden von vorhandenen"
  - "/Yu (Compileroption) [C++]"
  - "PCH-Dateien, Verwenden von vorhandenen"
  - "Vorkompilierte Headerdateien, Verwenden von vorhandenen"
  - "Yu (Compileroption) [C++]"
  - "-Yu (Compileroption) [C++]"
ms.assetid: 24f1bd0e-b624-4296-a17e-d4b53e374e1f
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# /Yu (Vorkompilierte Headerdatei verwenden)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Weist den Compiler an, eine vorhandene vorkompilierte Headerdatei \(.pch\) in der aktuellen Kompilierung zu verwenden.  
  
## Syntax  
  
```  
/Yu[filename]  
```  
  
## Argumente  
 *filename*  
 Der Name einer Headerdatei, die mit der **\#include**\-Präprozessordirektive in die Quelldatei eingebunden wird.  
  
## Hinweise  
 Der Name der Includedatei muss bei der **\/Yc**\-Option, die den vorkompilierten Header erstellt, und jeder nachfolgenden **\/Yu**\-Option, die die Verwendung des vorkompilierten Headers angibt, derselbe sein.  
  
 Bei **\/Yc** gibt `filename` den Punkt an, an dem die Vorkompilierung anhält. Der Compiler kompiliert den gesamten Code bis einschließlich `filename` und benennt den resultierenden vorkompilierten Header mit dem Basisnamen der Includedatei und der Erweiterung .pch.  
  
 Die PCH\-Datei muss mit **\/Yc** erstellt worden sein.  
  
 Der Compiler behandelt den gesamten Code vor der H\-Datei als vorkompiliert.  Er überspringt diesen bis hinter die die der H\-Datei zugeordneten **\#include**\-Direktive, verwendet den in der PCH\-Datei enthaltenen Code und kompiliert dann den gesamten Code hinter `filename`.  
  
 In der Befehlszeile sind keine Leerzeichen zwischen **\/Yu** und `filename` zulässig.  
  
 Wenn Sie die Option **\/Yu** ohne einen Dateinamen angeben, muss das Quellprogramm ein [\#pragma hdrstop](../../preprocessor/hdrstop.md)\-Pragma enthalten, das den Dateinamen der vorkompilierten Headerdatei \(PCH\-Datei\) angibt.  In diesem Fall verwendet der Compiler die durch [\/Fp \(Name der PCH\-Datei\)](../../build/reference/fp-name-dot-pch-file.md) angegebene vorkompilierte Headerdatei \(PCH\-Datei\).  Der Compiler überspringt den Code bis zu diesem Pragma, stellt den kompilierten Zustand von der vorkompilierten Headerdatei, die im Pragma angegeben ist, wieder her und kompiliert dann nur den Code, der dem Pragma folgt.  Wenn **\#pragma hdrstop** keinen Dateinamen angibt, sucht der Compiler nach einer Datei mit einem vom Basisnamen der Quelldatei abgeleiteten Namen und der Erweiterung .pch.  Sie können auch die Option **\/Fp** verwenden, um eine andere PCH\-Datei anzugeben.  
  
 Wenn Sie die Option **\/Yu** ohne einen Dateinamen verwenden und kein **hdrstop**\-Pragma angeben, wird eine Fehlermeldung generiert und die Kompilierung schlägt fehl.  
  
 Wenn die Optionen **\/Yc**`filename` und  **\/Yu**`filename` in derselben Befehlszeile vorkommen und beide auf denselben Dateinamen verweisen, hat **\/Yc**`filename` Vorrang bei der Vorkompilierung des gesamten Codes bis einschließlich der benannten Datei.  Diese Funktion vereinfacht das Schreiben von Makefiles.  
  
 Da PCH\-Dateien ebenso Informationen über die Computerumgebung wie Speicheradresseninformationen über das Programm enthalten, sollten Sie eine PCH\-Datei nur auf dem Computer verwenden, auf dem sie erstellt wurde.  
  
 Weitere Informationen zu vorkompilierten Headern finden Sie unter:  
  
-   [\/Y \(Vorkompilierte Header\)](../../build/reference/y-precompiled-headers.md)  
  
-   [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md)  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Geben Sie [\/Yc \(Datei der vorkompilierten Header erstellen\)](../../build/reference/yc-create-precompiled-header-file.md) für eine CPP\-Datei im Projekt an.  
  
2.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
3.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
4.  Klicken Sie auf die Eigenschaftenseite **Vorkompilierte Header**.  
  
5.  Ändern Sie die Eigenschaft **PCH durch Datei erstellen** oder **Erstellen\/Verwenden eines vorkompilierten Headers**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Weitere Informationen finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough*> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader*>.  
  
## Beispiele  
 Wenn der folgende Code:  
  
```  
#include <afxwin.h>   // Include header for class library  
#include "resource.h" // Include resource definitions  
#include "myapp.h"    // Include information specific to this app  
...  
```  
  
 mit der Befehlszeile `CL /YuMYAPP.H PROG.CPP` kompiliert wird, verarbeitet der Compiler die drei Include\-Anweisungen nicht, sondern verwendet vorkompilierten Code aus MYAPP.pch. Dadurch wird die Zeit eingespart, die zum Vorverarbeiten aller drei Dateien \(und etwaiger eingebundener Dateien\) nötig wäre.  
  
 Sie können die [\/Fp \(Name der PCH\-Datei\)](../../build/reference/fp-name-dot-pch-file.md)\-Option mit der **\/Yu**\-Option verwenden, um den Namen der PCH\-Datei anzugeben, wenn sich dieser vom Dateinamenargument für **\/Yc** oder dem Basisnamen der Quelldatei unterscheidet, wie im folgenden Beispiel:  
  
```  
CL /YuMYAPP.H /FpMYPCH.pch PROG.CPP  
```  
  
 Dieser Befehl legt eine vorkompilierte Headerdatei mit der Bezeichnung MYPCH.pch fest.  Der Compiler verwendet die Inhalte dieser Datei, um den vorkompilierten Status aller Headerdateien bis zu einschließlich MYAPP.h wiederherzustellen.  Der Compiler kompiliert dann den Code, der auf die **include**\-Anweisung für MYAPP.h folgt.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)