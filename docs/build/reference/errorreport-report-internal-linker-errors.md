---
title: -ERRORREPORT (internen Linkerfehlern) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /ERRORREPORT
- VC.Project.VCLinkerTool.ErrorReporting
dev_langs: C++
helpviewer_keywords:
- /ERRORREPORT linker option
- ERRORREPORT linker option
- -ERRORREPORT linker option
ms.assetid: f5fab595-a2f1-4eb0-ab5c-1c0fbd3d8c28
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e6242457bb4da3e19700f5018b2a484bfa05630b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="errorreport-report-internal-linker-errors"></a>/ERRORREPORT (Weiterleiten von internen Linkerfehlern)
```  
/errorReport:[ none | prompt | queue | send ]  
```  
  
## <a name="remarks"></a>Hinweise  
 Ermöglicht es Ihnen, Informationen über interne Compilerfehler (ICE) direkt an Microsoft zu senden.  
  
 Die Option **/errorreport: Send** Fehlerinformationen automatisch an Microsoft, aber Erfolg zu senden versucht, hängt von registrierungseinstellungen. Weitere Informationen dazu, wie Sie die entsprechenden Werte in der Registrierung festlegen, finden Sie unter [Aktivieren der automatischen Fehlerberichterstattung in Visual Studio 2008-Befehlszeilentools](http://go.microsoft.com/fwlink/?LinkID=184695) auf der MSDN-Website.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Konfigurationseigenschaften** Ordner.  
  
3.  Klicken Sie auf die **Linker** Ordner.  
  
4.  Klicken Sie auf die **erweitert** Eigenschaftenseite.  
  
5.  Ändern der **-Fehlerberichterstattung**Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ErrorReporting%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [/ errorreport (Bericht interne Compilerfehler)](../../build/reference/errorreport-report-internal-compiler-errors.md)   
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)