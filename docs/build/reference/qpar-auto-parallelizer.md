---
title: -Qpar (automatische Parallelisierung) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableParallelCodeGeneration
dev_langs:
- C++
ms.assetid: 33ecf49d-c0d5-4f34-bce3-84ff03f38918
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 430bf1ebc79008d97435ecbcb3b15cf19dda5f8d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375687"
---
# <a name="qpar-auto-parallelizer"></a>/Qpar (Automatische Parallelisierung)
Ermöglicht die [Auto-Parallelisierer](../../parallel/auto-parallelization-and-auto-vectorization.md) Funktion des Compilers, Schleifen im Code automatisch zu parallelisieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Qpar  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Compiler automatisch Schleifen im Code parallelisiert, byteweise in mehrere Prozessorkerne Berechnung. Nur, wenn der Compiler bestimmt, dass es dazu rechtliche und diese Parallelisierung würde die Leistung verbessern, ist eine Schleife parallelisiert.  
  
 Die `#pragma loop()` Direktiven sind verfügbar, in denen den Optimierer bestimmte Schleifen zu parallelisieren. Weitere Informationen finden Sie unter [Schleife](../../preprocessor/loop.md).  
  
 Informationen zum Aktivieren der ausgehende Nachrichten für den Auto-parallelisierer finden Sie unter [/qpar-Report (Auto-Parallelisierer Reporting Stufe)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md).  
  
### <a name="to-set-the-qpar-compiler-option-in-visual-studio"></a>So legen Sie die /Qpar-Compileroption in Visual Studio fest  
  
1.  Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften**aus.  
  
2.  In der **Eigenschaftenseiten** Dialogfeld unter **C/C++-** Option **Befehlszeile**.  
  
3.  In der **Zusatzoptionen** geben `/Qpar`.  
  
### <a name="to-set-the-qpar-compiler-option-programmatically"></a>So legen Sie die /Qpar-Compileroption programmgesteuert fest  
  
-   Verwenden Sie hierzu das Codebeispiel unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [/ Q-Optionen (Operationen auf niedriger Ebene)](../../build/reference/q-options-low-level-operations.md)   
 [/ Qpar-Report-(Auto-Parallelizer-Berichtsebene)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [#pragma loop()](../../preprocessor/loop.md)   
 [Parallele Programmierung in systemeigenem Code](http://go.microsoft.com/fwlink/p/?linkid=263662)