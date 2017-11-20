---
title: -CGTHREADS (Compilerthreads) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- /CGTHREADS linker option
- -CGTHREADS linker option
- CGTHREADS linker option
ms.assetid: 4b52cfdb-3702-470b-9580-fabeb1417488
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9faa67386412d32ff0a40ef8c3a9776c332bbdde
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cgthreads-compiler-threads"></a>/CGTHREADS (Compilerthreads)
Legt die Anzahl von cl.exe-Threads zur Verwendung für die Optimierung und Codegenerierung fest, wenn die Link-Zeitcodegenerierung angegeben ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
/CGTHREADS:[1-8]  
```  
  
## <a name="arguments"></a>Argumente  
 number  
 Die maximale Anzahl von Threads zur Verwendung für cl.exe, im Bereich von 1 bis 8.  
  
## <a name="remarks"></a>Hinweise  
 Die **/cgthreads** Option gibt die maximale Anzahl von Threads die cl.exe parallel für die Optimierung und codegenerierung codegenerierungsphase der Kompilierung, wenn die Link zeitcodegenerierung ([/LTCG](../../build/reference/ltcg-link-time-code-generation.md)) ist angegeben. Standardmäßig verwendet cl.exe vier Threads, als ob **/CGTHREADS:4** angegeben wurden. Wenn mehr Prozessorkerne verfügbar sind, kann ein höherer `number`-Wert die Builderstellung beschleunigen.  
  
 Für einen Build können mehrere Stufen der Parallelität angegeben werden. Der msbuild.exe-Switch **maxcpucount** gibt die Anzahl der MSBuild-Prozesse, die parallel ausgeführt werden können. Die [/MP (erstellen mit mehreren Prozessen)](../../build/reference/mp-build-with-multiple-processes.md) compilerkennzeichen gibt die Anzahl der cl.exe-Prozesse, die die Quelldateien gleichzeitig zu kompilieren. Die [/cgthreads](../../build/reference/cgthreads-code-generation-threads.md) -Compileroption gibt die Anzahl der Threads, die von jedem cl.exe-Prozess verwendet. Da der Prozessor nur so viele Threads gleichzeitig ausführen kann, wie Prozessorkerne vorhanden sind, ist es nicht sinnvoll, größere Werte für all diese Optionen gleichzeitig anzugeben. Das kann sogar kontraproduktiv sein. Weitere Informationen zum Erstellen von Projekten parallel finden Sie unter [Erstellen von mehreren Projekten](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **Konfigurationseigenschaften**, **Linker** Ordner.  
  
3.  Wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
4.  Ändern der **Zusatzoptionen** Eigenschaft einschließen **/cgthreads:**`number`, wobei `number` ist ein Wert von 1 bis 8, und wählen Sie dann **OK**.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Optionen des Linkers](../../build/reference/linker-options.md)   
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)