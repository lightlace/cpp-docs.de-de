---
title: -SWAPRUN (Linkerausgabe in Auslagerungsdatei laden) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 522cd693da1b4e1a72d11119f622d862413b409b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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