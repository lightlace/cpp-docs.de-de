---
title: -MANIFESTFILE (Benennen der Manifestdatei) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.ManifestFile
dev_langs: C++
helpviewer_keywords:
- MANIFESTFILE linker option
- -MANIFESTFILE linker option
- /MANIFESTFILE linker option
ms.assetid: befa5ab2-a9cf-4c9b-969a-e7b4a930f08d
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 77b0f83d928970f56ed24487762fb4c40965b49e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="manifestfile-name-manifest-file"></a>/MANIFESTFILE (Benennen der Manifestdatei)
```  
/MANIFESTFILE:filename  
```  
  
## <a name="remarks"></a>Hinweise  
 / MANIFESTFILE können Sie den Standardnamen der Manifestdatei zu ändern.  Die Standardnamen der Manifestdatei ist der Dateiname und der Endung .manifest.  
  
 / MANIFESTFILE haben keine Auswirkungen, wenn Sie nicht auch mit verknüpfen [/MANIFEST](../../build/reference/manifest-create-side-by-side-assembly-manifest.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten.  
  
3.  Erweitern Sie die **Linker** Knoten.  
  
4.  Wählen Sie die **Manifestdatei** Eigenschaftenseite.  
  
5.  Ändern der **Manifestdatei** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ManifestFile%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)