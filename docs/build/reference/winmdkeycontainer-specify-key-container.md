---
title: "-WINMDKEYCONTAINER (Schlüsselcontainer angeben) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKEYCONTAINER
dev_langs:
- C++
ms.assetid: c2fc44dc-7cb5-42b9-897f-1b124928f2f7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cfb71a932180a41784b9e0894220982a170e6bf2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="winmdkeycontainer-specify-key-container"></a>/WINMDKEYCONTAINER (Schlüsselcontainer angeben)
Gibt einen Schlüsselcontainer zum Signieren einer Windows-Metadatendatei (winmd) an.  
  
```  
/WINMDKEYCONTAINER:name  
```  
  
## <a name="remarks"></a>Hinweise  
 Ähnelt der [/keycontainer](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md) Linkeroption, die in einer Datei (.winmd) angewendet wird.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **Linker** Ordner.  
  
3.  Wählen Sie die **Windows-Metadaten** Eigenschaftenseite.  
  
4.  In der **Schlüsselcontainer für Windows-Metadaten** Geben Sie den Speicherort.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)