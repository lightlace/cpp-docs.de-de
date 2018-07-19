---
title: -WINMDKEYCONTAINER (Schlüsselcontainer angeben) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKEYCONTAINER
dev_langs:
- C++
ms.assetid: c2fc44dc-7cb5-42b9-897f-1b124928f2f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36e4f74eb249c2687716fedb43ccf0a37e35f7b7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376610"
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