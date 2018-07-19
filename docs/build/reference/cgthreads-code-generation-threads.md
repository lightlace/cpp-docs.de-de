---
title: -Cgthreads (Codegenerierungsthreads) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /cgthreads
dev_langs:
- C++
helpviewer_keywords:
- /cgthreads compiler option (C++)
- -cgthreads compiler option (C++)
- cgthreads compiler option (C++)
- cgthreads
ms.assetid: 64bc768c-6caa-4baf-9dea-7cfa1ffb01c2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 32c88fe00958a0fc767d8a316bfe4edab7b4fb0e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372434"
---
# <a name="cgthreads-code-generation-threads"></a>/cgthreads (Codegenerierungsthreads)
Legt die Anzahl der cl.exe-Threads fest, die für Optimierung und Codegenerierung verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
/cgthreads[1-8]  
```  
  
## <a name="arguments"></a>Argumente  
 number  
 Die maximale Anzahl von Threads zur Verwendung für cl.exe, im Bereich von 1 bis 8.  
  
## <a name="remarks"></a>Hinweise  
 Die **/cgthreads** Option gibt die maximale Anzahl von Threads cl.exe verwendet parallel für die Optimierungs- und codegenerierungsphasen der Kompilierung. Beachten Sie, dass es kann kein Leerzeichen zwischen **/cgthreads** und `number` Argument. Standardmäßig verwendet cl.exe vier Threads, als ob **/cgthreads4** angegeben wurden. Wenn mehr Prozessorkerne verfügbar sind, kann ein höherer `number`-Wert die Builderstellung beschleunigen. Diese Option ist besonders nützlich, wenn er mit kombiniert wird [/GL (Optimierung des ganzen Programms)](../../build/reference/gl-whole-program-optimization.md).  
  
 Für einen Build können mehrere Stufen der Parallelität angegeben werden. Der msbuild.exe-Switch **maxcpucount** gibt die Anzahl der MSBuild-Prozesse, die parallel ausgeführt werden können. Die [/MP (erstellen mit mehreren Prozessen)](../../build/reference/mp-build-with-multiple-processes.md) compilerkennzeichen gibt die Anzahl der cl.exe-Prozesse, die die Quelldateien gleichzeitig zu kompilieren. Die **/cgthreads** Option gibt die Anzahl der Threads, die von jedem cl.exe-Prozess verwendet. Da der Prozessor nur so viele Threads gleichzeitig ausführen kann, wie Prozessorkerne vorhanden sind, ist es nicht sinnvoll, größere Werte für all diese Optionen gleichzeitig anzugeben. Das kann sogar kontraproduktiv sein. Weitere Informationen zum Erstellen von Projekten parallel finden Sie unter [Erstellen von mehreren Projekten](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **Konfigurationseigenschaften**, **C/C++-** Ordner.  
  
3.  Wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
4.  Ändern der **Zusatzoptionen** Eigenschaft einschließen **/cgthreads**`N`, wobei `N` ist ein Wert von 1 bis 8, und wählen Sie dann **OK**.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)