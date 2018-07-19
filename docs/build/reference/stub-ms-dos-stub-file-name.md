---
title: -STUB (MS-DOS-Stub-Dateiname) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /stub
- VC.Project.VCLinkerTool.DosStub
dev_langs:
- C++
helpviewer_keywords:
- Win32 [C++], attaching MS-DOS stub program
- STUB linker option
- MS-DOS stub file name linker option
- /STUB linker option
- Windows API [C++], attaching MS-DOS stub program
- -STUB linker option
ms.assetid: 65221ffe-4f9a-4a14-ac69-3cfb79b40b5f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4302040f7d18dcffc07ddd054c34b62c22e400d2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379015"
---
# <a name="stub-ms-dos-stub-file-name"></a>/STUB (Name der MS-DOS-Stubdatei)
```  
/STUB:filename  
```  
  
## <a name="remarks"></a>Hinweise  
 Dabei gilt:  
  
 *filename*  
 Eine MS-DOS-Anwendung.  
  
## <a name="remarks"></a>Hinweise  
 Die Option/Stub Fügt ein MS-DOS-Stubprogramm an ein Win32-Programm.  
  
 Ein Stub-Programms wird aufgerufen, wenn die Datei im MS-DOS-ausgeführt wird. Dabei wird in der Regel eine entsprechende Meldung angezeigt. Allerdings kann jede gültige MS-DOS-Anwendung ein Stub-Programms.  
  
 Geben Sie einen *Filename* für die Stub-Programms nach einem Doppelpunkt (:) in der Befehlszeile angegeben. Der Linker überprüft *Filename* und eine Fehlermeldung ausgegeben, wenn die Datei nicht ausführbar ist. Das Programm muss eine .exe-Datei sein. eine Datei ".com" ist ungültig für ein Stub-Programms.  
  
 Wenn diese Option nicht verwendet wird, fügt der Linker eine Standard-Stub-Programms, der die folgende Meldung ausgibt:  
  
```  
This program cannot be run in MS-DOS mode.  
```  
  
 Wenn Sie einen virtuellen Gerätetreiber erstellen *Filename* ermöglicht dem Benutzer, einen Dateinamen angeben, die eine Anweisung-Struktur (definiert in WINNT. H), die in der VXD, anstatt das Standardheader verwendet werden.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Option in der **Zusatzoptionen** Feld.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)