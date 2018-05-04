---
title: -TLBID (Angeben der Ressourcen-ID für typelib festlegen) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /tlbid
- VC.Project.VCLinkerTool.TypeLibraryResourceID
dev_langs:
- C++
helpviewer_keywords:
- tlb files, specifying resource ID
- -TLBID linker option
- .tlb files, specifying resource ID
- /TLBID linker option
- TLBID linker option
- type libraries, specifying resource ID
ms.assetid: 434b28a2-4656-4d52-ac82-8b18bf486fb2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: acea8de3f656da54a0697dc5b980dd4913054a00
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="tlbid-specify-resource-id-for-typelib"></a>/TLBID (Ressourcen-ID für TypeLib festlegen)
```  
/TLBID:id  
```  
  
## <a name="remarks"></a>Hinweise  
 Dabei gilt:  
  
 `id`  
 Ein vom Benutzer angegebener Wert für eine vom Linker erstellte Typbibliothek. Es überschreibt die Standard-Ressourcen-ID von 1.  
  
## <a name="remarks"></a>Hinweise  
 Beim Kompilieren eines Programms, das Attribute verwendet, erstellt der Linker eine Typbibliothek. Der Linker weist eine Ressourcen-ID 1 in der Typbibliothek.  
  
 Wenn diese Ressourcen-ID mit einer der vorhandenen Ressourcen in Konflikt steht, können Sie eine andere ID mit/TLBID angeben. Der Bereich von Werten, die Sie übergeben können `id` liegt zwischen 1 und 65535.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die **eingebettete IDL** Eigenschaftenseite.  
  
4.  Ändern der **Ressourcen-ID für TypeLib** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryResourceID%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)