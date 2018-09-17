---
title: -SWAPRUN (Linkerausgabe in Auslagerungsdatei laden) | Microsoft-Dokumentation
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
ms.openlocfilehash: 1867eb55f9ebcaba2d29f7b9b4b2f44a68164390
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717495"
---
# <a name="swaprun-load-linker-output-to-swap-file"></a>/SWAPRUN (Linkerausgabe in Auslagerungsdatei laden)

```
/SWAPRUN:{NET|CD}
```

## <a name="remarks"></a>Hinweise

Die/SWAPRUN-Option weist dem Betriebssystem erste Kopie den Linker-Ausgabe in eine Auslagerungsdatei, und führen Sie das Image von dort aus. Dies ist eine Windows NT 4.0 (oder höher)-Funktion.

Wenn NET angegeben wird, wird das Betriebssystem zuerst das binärimage vom Netzwerk in eine Auslagerungsdatei und von dort aus zu laden. Diese Option ist nützlich für die Ausführung von Anwendungen über das Netzwerk. Wenn CD angegeben wird, wird das Betriebssystem kopieren Sie das Abbild auf einem Wechseldatenträger auf eine Seitendatei und lädt es dann.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **System** Eigenschaftenseite.

1. Ändern Sie eine der folgenden Eigenschaften:

   - **Wechseln zum Ausführen von CD**

   - **Wechseln zum Ausführen vom Netzwerk**

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe die Eigenschaften <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromCD%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromNet%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)