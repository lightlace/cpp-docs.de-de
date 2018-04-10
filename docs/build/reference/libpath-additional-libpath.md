---
title: -LIBPATH (Libpath-Pfad) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- /libpath
- VC.Project.VCLinkerTool.AdditionalLibraryDirectories
dev_langs:
- C++
helpviewer_keywords:
- LIBPATH linker option
- /LIBPATH linker option
- Additional Libpath linker option
- environment library path override
- -LIBPATH linker option
- library path linker option
ms.assetid: 7240af0b-9a3d-4d53-8169-2a92cd6958ba
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 452158c2767ec4f0bf30a88df17b7c01496e24e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="libpath-additional-libpath"></a>/LIBPATH (Libpath-Pfad hinzufügen)
```  
/LIBPATH:dir  
```  
  
## <a name="remarks"></a>Hinweise  
 Dabei gilt:  
  
 `dir`  
 Gibt einen Pfad an, dass der Linker durchsucht wird, bevor er den in der Umgebungsvariablen LIB angegebenen Pfad durchsucht.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie die/LIBPATH-Option, um den Bibliothekspfad der Umgebung zu überschreiben. Der Linker wird durchsucht zuerst im Pfad angegeben wird, indem Sie diese Option aus, und suchen Sie im Pfad, in der LIB-Umgebungsvariablen angegeben. Sie können nur ein Verzeichnis für jede einzelne/LIBPATH-Option angeben, die Sie eingeben. Wenn Sie mehrere Verzeichnisse angeben möchten, müssen Sie mehrere/LIBPATH-Optionen angeben. Der Linker sucht die angegebenen Verzeichnisse klicken Sie dann in der Reihenfolge.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die **allgemeine** Eigenschaftenseite.  
  
4.  Ändern der **Zusätzliche Bibliotheksverzeichnisse** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalLibraryDirectories%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)