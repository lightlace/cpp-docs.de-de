---
title: -WINMDDELAYSIGN (eine Winmd teilweise Signieren) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.WINMDDelaySign
dev_langs:
- C++
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5c50480fae1f4f3e7421236615d059a642d1074f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375557"
---
# <a name="winmddelaysign-partially-sign-a-winmd"></a>/WINMDDELAYSIGN (eine winmd teilweise signieren)
Ermöglicht das teilweise Signieren einer Windows Runtime-Metadatendatei (.winmd) verlegen Sie den öffentlichen Schlüssel in der Datei.  
  
```  
/WINMDDELAYSIGN[:NO]  
```  
  
## <a name="remarks"></a>Hinweise  
 Ähnelt der [/delaysign /](../../build/reference/delaysign-partially-sign-an-assembly.md) Linkeroption, die auf die winmd-Datei angewendet wird. Verwendung **/WINMDDELAYSIGN** , wenn Sie nur den öffentlichen Schlüssel in der winmd-Datei aufnehmen möchten. Standardmäßig fungiert der Linker als **/WINMDDELAYSIGN:NO** angegeben wurden; d. h. die Winmd-Datei ist nicht signieren.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **Linker** Ordner.  
  
3.  Wählen Sie die **Windows-Metadaten** Eigenschaftenseite.  
  
4.  In der **Windows Metadaten verzögerte Signierung** Dropdown-Liste Wählen Sie die gewünschte Option.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)