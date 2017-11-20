---
title: -ALIGN (Abschnittsausrichtung) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.Alignment
- /align
dev_langs: C++
helpviewer_keywords:
- sections, specifying alignment
- ALIGN linker option
- /ALIGN linker option
- -ALIGN linker option
- section alignment
- sections
ms.assetid: f2f8ac24-e90e-4bea-8205-f2960a3b1740
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e620719d5a69c333a45664fba5967a740224d4d5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="align-section-alignment"></a>/ALIGN (Abschnittsausrichtung)
```  
/ALIGN[:number]  
```  
  
## <a name="remarks"></a>Hinweise  
 Dabei gilt:  
  
 `number`  
 Der Ausrichtungswert.  
  
## <a name="remarks"></a>Hinweise  
 Die/align-Option gibt die Ausrichtung eines Abschnitts innerhalb des linearen Adressraums des Programms. Die `number` Argument in Bytes und muss eine Potenz von zwei sein. Der Standardwert ist 4 KB (4096). Der Linker gibt eine Warnung aus, wenn die Ausrichtung einer ungültigen Abbild erzeugt.  
  
 Wenn Sie eine Anwendung z. B. ein Gerätetreiber schreiben, müssen Sie nicht die Ausrichtung zu ändern.  
  
 Es ist möglich, ändern Sie die Ausrichtung eines bestimmten Bereichs mit dem Ausrichtungsparameter, um die [/SECTION](../../build/reference/section-specify-section-attributes.md) Option.  
  
 Der Ausrichtungswert, die Sie angeben, darf nicht kleiner als die größte abschnittsausrichtung sein.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Option in der **Zusatzoptionen** Feld.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)