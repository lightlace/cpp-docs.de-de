---
title: "-TSAWARE (Terminalserverfähige Anwendung erstellen) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /tsaware
- VC.Project.VCLinkerTool.TerminalServerAware
dev_langs: C++
helpviewer_keywords:
- Terminal Server
- /TSAWARE linker option
- Terminal Server, Terminal Server-aware applications
- -TSAWARE linker option
- TSAWARE linker option
ms.assetid: fe1c1846-de5b-4839-b562-93fbfe36cd29
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4c6fb783f717f730945f8d34c8fe2a03f5e1f6d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tsaware-create-terminal-server-aware-application"></a>/TSAWARE (Terminalserverfähige Anwendung erstellen)
```  
/TSAWARE[:NO]  
```  
  
## <a name="remarks"></a>Hinweise  
 E-Option setzt ein Flag im Feld IMAGE_OPTIONAL_HEADER DllCharacteristics in das Programmabbild optional-Header. Wenn dieses Flag festgelegt ist, wird der Terminalserver keine bestimmten Änderungen an der Anwendung vornehmen.  
  
 Wenn eine Anwendung nicht Terminalserver beachten (auch bekannt als eine ältere Anwendung) ist, macht Terminalserver bestimmte Änderungen an die ältere Anwendung ordnungsgemäß in einer mehrbenutzerumgebung funktionieren. Terminal Server wird beispielsweise einen virtuellen Windows-Ordner erstellen, so, dass jeder Benutzer einen Ordner "Windows" anstelle von Windows-Verzeichnis des Systems erste erhält. Dies ermöglicht Benutzern den Zugriff auf ihre eigenen INI-Dateien. Darüber hinaus erhöht eine Terminal Server einige Anpassungen an der Registrierung für eine Legacyversion einer Anwendung. Diese Änderungen verlangsamen das Laden von die ältere Anwendung auf dem Terminalserver.  
  
 Wenn eine Anwendung Terminal Server bekannt ist, weder INI-Dateien abhängig ist, noch müssen Schreiben in die **HKEY_CURRENT_USER** Registrierung während des Setups.  
  
 Wenn Sie/TSAWARE und Ihre Anwendung weiterhin INI-Dateien verwendet, werden die Dateien von allen Benutzern des Systems freigegeben werden. Wenn dies zulässig ist, können Sie weiterhin Ihre Anwendung mit/TSAWARE verknüpfen; Andernfalls müssen Sie/TSAWARE: NO verwenden.  
  
 E-Option ist standardmäßig für Windows 2000 und höher für Windows- und konsolenanwendungen aktiviert. Finden Sie unter [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) und [/Version](../../build/reference/version-version-information.md) Informationen.  
  
 / TSAWARE gilt nicht für Treiber, VxDs oder DLLs.  
  
 Wenn eine Anwendung mit/TSAWARE, DUMPBIN verknüpft wurde [/Headers](../../build/reference/headers.md) zeigen Informationen zu diesem Zweck.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die **System** Eigenschaftenseite.  
  
4.  Ändern der **Terminalserver** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TerminalServerAware%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Optionen des Linkers](../../build/reference/linker-options.md)   
 [Das Speichern von benutzerspezifischen Informationen](http://msdn.microsoft.com/library/aa383452)   
 [Ältere Anwendungen in einer Terminaldienste-Umgebung](https://msdn.microsoft.com/en-us/library/aa382957.aspx)