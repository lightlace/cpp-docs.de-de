---
title: -SWAPRUN (Linkerausgabe in Auslagerungsdatei laden) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.SwapRunFromNet
- /swaprun
- VC.Project.VCLinkerTool.SwapRunFromCD
dev_langs:
- C++
helpviewer_keywords:
- -SWAPRUN linker option
- files [C++], LINK
- LINK tool [C++], output
- linker [C++], copying output to swap file
- swap file for linker output
- output files, linker
- /SWAPRUN linker option
- SWAPRUN linker option
ms.assetid: 4a1e7f46-4399-4161-8dfc-d6a71beaf683
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a3b6829a20e80ab8548460205169e1cd258694e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="swaprun-load-linker-output-to-swap-file"></a>/SWAPRUN (Linkerausgabe in Auslagerungsdatei laden)
```  
/SWAPRUN:{NET|CD}  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Option/SWAPRUN weist dem Betriebssystem auf die erste Kopie den Linker-Ausgabe in eine Auslagerungsdatei, und führen Sie das Image von dort aus. Dies ist ein Windows NT 4.0 (oder höher)-Funktion.  
  
 Wenn NET angegeben wird, das Betriebssystem zuerst das binäre Abbild aus dem Netzwerk in eine Auslagerungsdatei zu kopieren und von dort aus zu laden. Diese Option eignet sich zum Ausführen von Anwendungen über das Netzwerk. Wenn CD angegeben wird, wird das Betriebssystem das Abbild auf einem Wechseldatenträger in eine Auslagerungsdatei kopieren und dann zu laden.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die **System** Eigenschaftenseite.  
  
4.  Ändern Sie eine der folgenden Eigenschaften:  
  
    -   **Wechseln zum Ausführen von CD**  
  
    -   **Wechseln zum Ausführen vom Netzwerk**  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe die Eigenschaften <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromCD%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromNet%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)