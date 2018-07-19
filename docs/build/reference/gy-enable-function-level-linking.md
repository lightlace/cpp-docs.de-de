---
title: -Gy (Funktionslevel-Linking aktivieren) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFunctionLevelLinking
- /gy
- VC.Project.VCCLWCECompilerTool.EnableFunctionLevelLinking
dev_langs:
- C++
helpviewer_keywords:
- enable function-level linking compiler option [C++]
- COMDAT function
- Gy compiler option [C++]
- -Gy compiler option [C++]
- /Gy compiler option [C++]
- packaged functions
ms.assetid: 0d3cf14c-ed7d-4ad3-b4b6-104e56f61046
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36e939a12cf23a9d9e476b676a5b068889414497
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376298"
---
# <a name="gy-enable-function-level-linking"></a>/Gy (Funktionslevel-Linking aktivieren)
Ermöglicht dem Compiler, einzelne Funktionen in Form von kompilierten Funktionen (COMDATs) zu kompilieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Gy[-]  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Linker erfordert, dass Funktionen separat als COMDATs ausgeschlossen oder sortieren einzelne Funktionen in einer DLL oder .exe-Datei verpackt werden.  
  
 Sie können die Linkeroption [/OPT (Optimierungen)](../../build/reference/opt-optimizations.md) Unreferenzierte gepackte Funktionen .exe-Datei ausgeschlossen werden.  
  
 Sie können die Linkeroption [/Order (Put-Funktionen in der Reihenfolge)](../../build/reference/order-put-functions-in-order.md) Paketfunktionen in einer bestimmten Reihenfolge in der .exe-Datei eingeschlossen.  
  
 Inlinefunktionen werden immer verpackt, wenn sie als Aufrufe instanziiert werden (Dies tritt ein, z. B. wenn inlining ist deaktiviert oder eine Funktionsadresse). Darüber hinaus werden C++-Memberfunktionen, die in der Klassendeklaration definiert automatisch gepackt; andere Funktionen sind nicht, und diese Option ist erforderlich, um sie als Paketfunktionen zu kompilieren.  
  
> [!NOTE]
>  Die [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) -Option zum Bearbeiten und fortfahren, setzt automatisch das **/Gy** Option.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die **Codegenerierung** Eigenschaftenseite.  
  
4.  Ändern der **Funktionslevel Linking aktivieren** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)