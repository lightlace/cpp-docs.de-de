---
title: -ALLOWBIND (DLL-Bindung verhindern) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.PreventDLLBinding
- /allowbind
dev_langs:
- C++
helpviewer_keywords:
- /ALLOWBIND linker option
- binding DLLs
- preventing DLL binding
- ALLOWBIND linker option
- -ALLOWBIND linker option
- DLLs [C++], preventing binding
ms.assetid: 30e37e24-12e4-407e-988a-39d357403598
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31968e27c46cb5ea220a4cfe19c36820c4cf8444
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369639"
---
# <a name="allowbind-prevent-dll-binding"></a>/ALLOWBIND (DLL-Bindung verhindern)
```  
/ALLOWBIND[:NO]  
```  
  
## <a name="remarks"></a>Hinweise  
 /ALLOWBIND:NO legt ein Bit im Header einer DLL fest, das Bind.exe darauf hinweist, dass das Image nicht gebunden werden darf. Möglicherweise möchten Sie nicht, dass eine DLL gebunden wird, wenn sie digital signiert wurde (die Bindung macht die Signatur ungültig).  
  
 Sie können eine vorhandene DLL zur ALLOWBIND-Funktionalität mit Bearbeiten der [/ALLOWBIND](../../build/reference/allowbind.md) Dienstprogramms EDITBIN-Option.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie **Konfigurationseigenschaften**, **Linker**, und wählen Sie **Befehlszeile**.  
  
3.  Geben Sie `/ALLOWBIND:NO` in **Zusatzoptionen**.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Optionen des Linkers](../../build/reference/linker-options.md)   
 [BindImage-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms679278.aspx)   
 [BindImageEx-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms679279.aspx)