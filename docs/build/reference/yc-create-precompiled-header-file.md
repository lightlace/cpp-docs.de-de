---
title: -Yc (vorkompilierte Headerdatei erstellen) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.UsePrecompiledHeader
- /yc
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderThrough
- VC.Project.VCCLWCECompilerTool.UsePrecompiledHeader
- VC.Project.VCCLCompilerTool.PrecompiledHeaderThrough
dev_langs:
- C++
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- .pch files, creating
- -Yc compiler option [C++]
- /Yc compiler option [C++]
- Yc compiler option [C++]
ms.assetid: 47c2e555-b4f5-46e6-906e-ab5cf21f0678
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 865b5e0fa7039a0b60f524c2f13a367569757d92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="yc-create-precompiled-header-file"></a>/Yc (vorkompilierten Headerdatei erstellen)
Weist den Compiler an, eine vorkompilierte Headerdatei (.pch) zu erstellen, die den Zustand der Kompilierung zu einem bestimmten Zeitpunkt darstellt.  
  
## <a name="syntax"></a>Syntax  
  
> __"/ Yc"__
> __"/ Yc"__*Dateiname*  
  
  
## <a name="arguments"></a>Argumente  
*filename*  
 Gibt eine Headerdatei (. h). Wenn dieses Argument verwendet wird, kompiliert der Compiler den gesamten Code bis zur und einschließlich der .h-Datei.  
  
## <a name="remarks"></a>Hinweise  
 Wenn **"/ Yc"** wird ohne Argument angegeben, der Compiler kompiliert den gesamten Code bis zum Ende der Quelldatei Basis oder zum Zeitpunkt der Basisdatei, in denen ein [Hdrstop](../../preprocessor/hdrstop.md) -Direktive tritt auf. Die resultierende PCH-Datei hat den gleichen Basisnamen als die Basis-Quelldatei, es sei denn, Sie geben eine andere Datei mit den **Hdrstop** Pragmas oder der **/fp** Option.  
  
 Vorkompilierte Code in einer Datei gespeichert ist, mit einem Namen erstellen, die aus der Basisname der Datei angegeben, mit der **"/ Yc"** Option und einer .pch-Erweiterung. Sie können auch die  [ /fp (Name. PCH-Datei)](../../build/reference/fp-name-dot-pch-file.md) Option, um einen Namen für die vorkompilierte Headerdatei anzugeben.  
  
 Bei Verwendung von __"/ Yc"__*Filename*, kompiliert der Compiler den gesamten Code bis zur und einschließlich der angegebenen Datei zur späteren Verwendung mit der [/Yu (vorkompilierte Headerdatei verwenden)](../../build/reference/yu-use-precompiled-header-file.md) Option.  
  
 Wenn die Optionen __"/ Yc"__*Filename* und __"/ Yu"__*Filename* auf derselben Befehlszeile auftreten, und verweisen oder vermuten lassen, wird der gleiche Dateiname __"/ Yc"__*Filename* hat Vorrang vor. Diese Funktion vereinfacht das Schreiben von Makefiles.  
  
 Weitere Informationen zu vorkompilierten Headern finden Sie unter:  
  
-   [/ Y (Vorkompilierte Header)](../../build/reference/y-precompiled-headers.md)  
  
-   [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md)  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Wählen Sie eine CPP-Datei. Die CPP-Datei muss #include .h-Datei, die vorkompilierte Headerinformationen enthält. Des Projekts **"/ Yc"** Einstellung kann auf Dateiebene überschrieben werden.  
  
2.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
3.  Öffnen der **Konfigurationseigenschaften**, **C/C++-**, **vorkompilierte Header** Eigenschaftenseite.  
  
4.  Ändern der **vorkompilierter Header** Eigenschaft.  
  
5.  Ändern Sie zum Festlegen der Dateiname der **vorkompilierten Headerdatei** Eigenschaft.
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Weitere Informationen finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>.  
  
## <a name="example"></a>Beispiel  
 Betrachten Sie folgenden Code:  
  
```cpp  
// prog.cpp
// compile with: cl /c /Ycmyapp.h prog.cpp
#include <afxwin.h>   // Include header for class library  
#include "resource.h" // Include resource definitions  
#include "myapp.h"    // Include information specific to this app  
// ...  
```  
  
Wenn dieser Code kompiliert wird, mit dem Befehl `CL /YcMYAPP.H PROG.CPP`, speichert der Compiler alle die vorverarbeitung AFXWIN.h, "RESOURCE.h", und in eine vorkompilierte Headerdatei MYAPP.h aufgerufen MYAPP.pch.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md) [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md)