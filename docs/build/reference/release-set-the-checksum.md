---
title: "/ RELEASE (Prüfsumme festlegen) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /release
- VC.Project.VCLinkerTool.SetChecksum
dev_langs: C++
helpviewer_keywords:
- -RELEASE linker option
- /RELEASE linker option
- checksum setting
- RELEASE linker option
ms.assetid: 93bcadf4-29ac-4824-914b-6997e3751d22
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5f561d96d46fadd24bc6dd7a4d473f3fcdc3bec7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="release-set-the-checksum"></a>/RELEASE (Prüfsumme festlegen)
```  
/RELEASE  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Option/Release wird die Prüfsumme im Header einer .exe-Datei.  
  
 Das Betriebssystem benötigt die Prüfsumme für Gerätetreiber. Legen Sie die Prüfsumme für Releaseversionen der Gerätetreiber zur Sicherstellung der Kompatibilität mit zukünftigen Betriebssystemen.  
  
 Die Option/Release wird festgelegt, wird standardmäßig bei der [/Subsystem: native](../../build/reference/subsystem-specify-subsystem.md) angegeben wird.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die **erweitert** Eigenschaftenseite.  
  
4.  Ändern der **Prüfsumme setzen** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SetChecksum%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)