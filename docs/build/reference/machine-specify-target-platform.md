---
title: -MACHINE (Zielplattform angeben) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.TargetMachine
- /machine
dev_langs: C++
helpviewer_keywords:
- mapfiles, creating linker
- target platform
- -MACHINE linker option
- /MACHINE linker option
- MACHINE linker option
ms.assetid: 8d41bf4b-7e53-4ab9-9085-d852b08d31c2
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: edc3f4dc590ed5a8a763a4289fc5e15d8529e313
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="machine-specify-target-platform"></a>/MACHINE (Zielplattform angeben)
```  
/MACHINE:{ARM|EBC|X64|X86}  
```  
  
## <a name="remarks"></a>Hinweise  
 Die /MACHINE-Option gibt die Zielplattform für das Programm an.  
  
 Normalerweise müssen Sie die /MACHINE-Option nicht angeben. LINK leitet den Computertyp aus den OBJ-Dateien ab. Unter bestimmten Umständen kann nicht allerdings LINK ermitteln, die Computertyp und gibt eine [Linkertools Fehler LNK1113](../../error-messages/tool-errors/linker-tools-error-lnk1113.md). Geben Sie "/MACHINE" an, wenn ein solcher Fehler auftritt.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die **erweitert** Eigenschaftenseite.  
  
4.  Ändern der **Zielcomputer** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TargetMachine%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)