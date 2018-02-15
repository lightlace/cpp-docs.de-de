---
title: -WINMD (Windows-Metadaten generieren) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadata
dev_langs:
- C++
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7517ec459677659067e80930ee48caccf84d52f3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="winmd-generate-windows-metadata"></a>/WINMD (Windows-Metadaten generieren)
Aktiviert die Generierung einer Windows Runtime-Metadatendatei (.winmd).  
  
```  
/WINMD[:{NO|ONLY}]  
```  
  
## <a name="remarks"></a>Hinweise  
 /WINMD  
 Die Standardeinstellung für universelle Windows-Plattform-apps. Der Linker generiert die binäre ausführbare Datei und der winmd-Metadaten-Datei.  
  
 /WINMD:NO  
 Der Linker generiert die binäre ausführbare Datei, aber nicht in eine winmd-Datei.  
  
 /WINMD:ONLY  
 Der Linker generiert die winmd-Datei, aber nicht die binären ausführbaren Datei.  
  
 Standardmäßig den Namen der Ausgabedatei hat das Format `binaryname`winmd. Um einen anderen Dateinamen anzugeben, verwenden die [/WINMDFILE](../../build/reference/winmdfile-specify-winmd-file.md) Option.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **Linker** Ordner.  
  
3.  Wählen Sie die **Windows-Metadaten** Eigenschaftenseite.  
  
4.  In der **Windows-Metadaten generieren** Dropdown-Liste Wählen Sie die gewünschte Option.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)