---
title: -GX (Ausnahmebehandlung aktivieren) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /gx
dev_langs: C++
helpviewer_keywords:
- exception handling, enabling
- /GX compiler option [C++]
- -GX compiler option [C++]
- cl.exe compiler, exception handling
- enable exception handling compiler option [C++]
- GX compiler option [C++]
ms.assetid: 933b43ba-de77-4ff8-a48b-7074de90bc1c
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3013b4233621e63de0230e088dfc10ff65a5705d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="gx-enable-exception-handling"></a>/GX (Ausnahmebehandlung aktivieren)
Veraltet. Aktiviert synchrone Ausnahmebehandlung mit der Annahme, die Funktionen deklariert, indem `extern "C"` nie eine Ausnahme auslösen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/GX  
```  
  
## <a name="remarks"></a>Hinweise  
 **/ GX** ist veraltet. Verwenden Sie die entsprechende [/EHsc /](../../build/reference/eh-exception-handling-model.md) -option von Windows. Eine Liste der veralteten Compileroptionen, finden Sie unter der **veraltete und entfernte Compileroptionen** im Abschnitt [Compileroptionen nach Kategorien sortiert](../../build/reference/compiler-options-listed-by-category.md).  
  
 Standardmäßig **/EHsc /**, die der entsprechende **/GX**, ist gültig, wenn Sie mit der Visual Studio-Entwicklungsumgebung kompilieren. Wenn Sie die Befehlszeilentools verwenden, wird keine Ausnahmebehandlung angegeben. Dies ist die Entsprechung der **/GX-**.  
  
 Weitere Informationen finden Sie unter [C++-Ausnahmebehandlung](../../cpp/cpp-exception-handling.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie im Navigationsbereich **Konfigurationseigenschaften**, **C/C++-**, **Befehlszeile**.  
  
3.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [/ EH (Ausnahmebehandlungsmodell)](../../build/reference/eh-exception-handling-model.md)