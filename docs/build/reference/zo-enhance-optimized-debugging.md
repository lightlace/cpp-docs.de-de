---
title: -Zo (optimiertes Debuggen verbessern) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- -Zo
- /Zo
dev_langs:
- C++
helpviewer_keywords:
- Zo compiler option [C++]
- /Zo compiler option [C++]
- -Zo compiler option [C++]
ms.assetid: eea8d89a-7fe0-4fe1-86b2-7689bbebbd7f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 326bd1c6c435dec97c309014dfc81ca444cc5eb6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="zo-enhance-optimized-debugging"></a>/Zo (erweitertes optimiertes Debugging)
Generieren Sie erweiterte Debuginformationen für optimierten Code in Nicht-Debugbuilds.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
/Zo[-]  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **/zo** -Compilerschalter generiert erweiterte Debuginformationen für optimierten Code. Bei der Optimierung können Register für lokale Variablen verwendet, Code neu angeordnet, Schleifen vektorisiert und Inline-Funktionsaufrufe verwendet werden. Diese Optimierungen können die Beziehung zwischen dem Quellcode und dem kompilierten Objektcode verbergen. Die **/zo** -Schalter weist den Compiler an, zusätzliche Debuginformationen für lokale Variablen und Inlinefunktionen zu generieren. Verwenden, um die Variablen in der **"Auto"**, **"lokal"**, und **Überwachen** Windows, wenn Sie schrittweise durch optimierten Code in Visual Studio-Debugger. Darüber hinaus können Stapelüberwachungen Inlinefunktionen im WinDBG-Debugger anzeigen. Debug-Builds, die Optimierungen deaktiviert haben ([/Od](../../build/reference/od-disable-debug.md)) ist nicht erforderlich für die zusätzlichen Debuginformationen generiert, wenn **/zo** angegeben ist. Verwenden der **/zo** Schalter, um Releasekonfigurationen mit aktivierter Optimierung zu debuggen. Weitere Informationen zu optimierungsschaltern finden Sie unter [/o-Optionen (Code optimieren)](../../build/reference/o-options-optimize-code.md). Die **/zo** Option ist standardmäßig in Visual Studio bei der Angabe von Debuginformationen mit **/Zi** oder **"/ Z7"**. Geben Sie **/Zo-** diese Compileroption explizit zu deaktivieren.  
  
 Die **/zo** Switch ist seit Visual Studio 2013 Update 3 verfügbar und ersetzt den zuvor nicht dokumentierten **/d2Zi+** wechseln.  
  
### <a name="to-set-the-zo-compiler-option-in-visual-studio"></a>So legen Sie die /Zo-Compileroption in Visual Studio fest  
  
1.  Öffnen der **Eigenschaftenseiten** im Dialogfeld für das Projekt. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **Konfigurationseigenschaften**, **C/C++-** Ordner.  
  
3.  Wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
4.  Ändern der **Zusatzoptionen** Eigenschaft einschließen `/Zo` und wählen Sie dann **OK**.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [/ O-Optionen (Code optimieren)](../../build/reference/o-options-optimize-code.md)   
 [/ Z7, / Zi, / Zi (Debuginformationsformat)](../../build/reference/z7-zi-zi-debug-information-format.md)   
 [Bearbeiten und Fortfahren](/visualstudio/debugger/edit-and-continue)