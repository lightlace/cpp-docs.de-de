---
title: -Yu (vorkompilierte Headerdatei verwenden) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /yu
dev_langs:
- C++
helpviewer_keywords:
- Yu compiler option [C++]
- /Yu compiler option [C++]
- -Yu compiler option [C++]
- PCH files, use existing
- .pch files, use existing
- precompiled header files, use existing
ms.assetid: 24f1bd0e-b624-4296-a17e-d4b53e374e1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d115017e843e7f03455e1eef2b384b3475a1b798
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="yu-use-precompiled-header-file"></a>/Yu (Vorkompilierte Headerdatei verwenden)
Weist den Compiler an, eine vorhandene Datei der vorkompilierten Headerdatei (PCH) in der aktuellen Kompilierung verwenden.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Yu[filename]  
```  
  
## <a name="arguments"></a>Argumente  
 *filename*  
 Der Name des Header-Datei, die in der Quelldatei über enthalten ist ein **#include** Präprozessordirektive angegeben.  
  
## <a name="remarks"></a>Hinweise  
 Der Name der Include-Datei muss sowohl für die **"/ Yc"** Option, der vorkompilierte Header und alle erstellt, nachfolgenden **"/ Yu"** Option angeben der Verwendung des vorkompilierten Headers.  
  
 Für **"/ Yc"**, `filename` gibt die Stelle, an welche Vorkompilierung beendet; der Compiler wird jedoch der gesamte Code vorkompiliert `filename` und benennt den resultierenden vorkompilierten Header, die mit der Basisname der Include-Datei und die Erweiterung PCH.  
  
 Die PCH-Datei muss erstellt worden mit **"/ Yc"**.  
  
 Der Compiler behandelt den gesamten Code vor der .h-Datei als vorkompilierte auftreten. Wird übersprungen hinter der **#include** .h-Datei zugeordnete Richtlinie verwendet den Code in die PCH-Datei, und klicken Sie dann kompiliert alle Code nach `filename`.  
  
 In der Befehlszeile darf kein Leerzeichen zwischen **"/ Yu"** und `filename`.  
  
 Geben Sie bei der **"/ Yu"** Option ohne einen Dateinamen Ihrer Quellprogramm darf eine [#pragma Hdrstop](../../preprocessor/hdrstop.md) Pragma, das den Dateinamen des vorkompilierten Headers, der PCH-Datei angibt. In diesem Fall verwendet der Compiler die vorkompilierte Headerdatei (PCH-Datei) von  [ /fp (Name. PCH-Datei)](../../build/reference/fp-name-dot-pch-file.md). Der Compiler auf den Speicherort der diesem Pragma überspringt, wird den kompilierten Zustand aus der vorkompilierten Headerdatei angegeben werden, indem Sie das Pragma wiederhergestellt und kompiliert dann nur Code, der dem Pragma folgt. Wenn **#pragma Hdrstop** gibt keinen Namen einer Datei, der Compiler sucht nach einer Datei mit einem Namen, die von der Basisname der Quelldatei mit einer .pch-Erweiterung abgeleitet. Sie können auch die **/fp** Option aus, um eine andere PCH-Datei angeben.  
  
 Bei Angabe der **"/ Yu"** ohne einen Dateinamen aus, und geben Sie keine **Hdrstop** Pragma, wird eine Fehlermeldung generiert und die Kompilierung schlägt fehl.  
  
 Wenn die **"/ Yc"** `filename` und **"/ Yu"** `filename` Optionen auf derselben Befehlszeile auftreten und beide verweisen auf den gleichen Dateinamen **"/ Yc"** `filename` akzeptiert Vorrang bei der Vorkompilierung des gesamten Codes bis einschließlich der benannten Datei. Diese Funktion vereinfacht das Schreiben von Makefiles.  
  
 Da PCH-Dateien Informationen über die Umgebung des Computers sowie Arbeitsspeicher Adressinformationen über das Programm enthalten, sollten Sie nur eine Pch-Datei auf dem Computer verwenden, in dem es erstellt wurde.  
  
 Weitere Informationen zu vorkompilierten Headern finden Sie unter:  
  
-   [/Y (Vorkompilierte Header)](../../build/reference/y-precompiled-headers.md)  
  
-   [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md)  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Geben Sie [/Yc (Datei der vorkompilierten Header erstellen)](../../build/reference/yc-create-precompiled-header-file.md) für eine CPP-Datei in Ihrem Projekt.  
  
2.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
3.  Klicken Sie auf den Ordner **C/C++** .  
  
4.  Klicken Sie auf die **vorkompilierte Header** Eigenschaftenseite.  
  
5.  Ändern der **PCH durch Datei erstellen/verwenden** Eigenschaft oder die **vorkompilierten Header erstellen/verwenden** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Weitere Informationen finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>.  
  
## <a name="examples"></a>Beispiele  
 Wenn der folgende Code:  
  
```  
#include <afxwin.h>   // Include header for class library  
#include "resource.h" // Include resource definitions  
#include "myapp.h"    // Include information specific to this app  
...  
```  
  
 wird über die Befehlszeile kompiliert `CL /YuMYAPP.H PROG.CPP`, verarbeitet der Compiler nicht die drei Anweisungen, aber verwendet vorkompilierter Code aus MYAPP.pch, dadurch Zeitersparnis beteiligten vorverarbeitung alle drei Dateien (und alle Dateien, die sie möglicherweise enthalten) enthalten.  
  
 Sie können die  [ /fp (Name. PCH-Datei)](../../build/reference/fp-name-dot-pch-file.md) -Option mit der **"/ Yu"** Option aus, um den Namen der PCH-Datei angeben, wenn der Name entweder Datei Name-Arguments, unterscheidet **"/ Yc"** oder der Basisname der Quelldatei, wie in der befolgen:  
  
```  
CL /YuMYAPP.H /FpMYPCH.pch PROG.CPP  
```  
  
 Dieser Befehl gibt eine vorkompilierte Headerdatei mit dem Namen MYPCH.pch an. Der Compiler verwendet den Inhalt, den vorkompilierten Status aller Headerdateien bis zur und einschließlich MYAPP.h wiederherzustellen. Klicken Sie dann kompiliert der Compiler den Code, der auftritt, nachdem die MYAPP.h **enthalten** Anweisung.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)