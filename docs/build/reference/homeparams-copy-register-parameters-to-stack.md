---
title: -Homeparams (Registerparameter in den Stapel kopieren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /homeparams
dev_langs:
- C++
helpviewer_keywords:
- /homeparams compiler option [C++]
- -homeparams compiler option [C++]
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bfd6b8c77d972eb4606e7095bc5f733e7db16ea6
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42572361"
---
# <a name="homeparams-copy-register-parameters-to-stack"></a>/homeparams (Registerparameter in den Stapel kopieren)
Erzwingt, dass in Registern übergebene Parameter beim Funktionseinstieg in ihre Speicherorte auf dem Stapel geschrieben werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
/homeparams  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Compileroption steht nur für die X64-Compiler (systemeigene und cross-Compiler).  
  
 Wenn Parameter übergeben werden, in x X64 Kompilierung Aufrufkonventionen Stapelspeicher für Parameter erforderlich, auch für Parameter, die in Registern übergeben. Weitere Informationen finden Sie unter [Parameterübergabe](../../build/parameter-passing.md). Allerdings werden standardmäßig in einem Releasebuild die Registerparameter nicht in den Stapel, in den Bereich geschrieben werden, die bereits für die Parameter bereitgestellt wird. Dies erschwert es einem optimierten (Release) Build des Programms zu debuggen.  
  
 Verwenden Sie für einen Releasebuild **/homeparams in den** um sicherzustellen, dass Sie Ihre Anwendung debuggen können. **/ homeparams in den** einer verminderten Leistung, da eine Schleife, um die Registerparameter auf dem Stapel Laden erforderlich ist.  
  
 In einem Debugbuild wird der Stapel immer mit Parametern in Registern übergeben aufgefüllt.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)