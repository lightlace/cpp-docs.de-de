---
title: -X (ignorieren Includepfaden) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /x
- VC.Project.VCCLCompilerTool.OVERWRITEStandardIncludePath
- VC.Project.VCCLWCECompilerTool.OVERWRITEStandardIncludePath
dev_langs:
- C++
helpviewer_keywords:
- /X compiler option [C++]
- include files, ignore standard path
- -X compiler option [C++]
- include directories, ignore standard
- X compiler option
- Ignore Standard Include Paths compiler option
ms.assetid: 16bdf2cc-c8dc-46e4-bdcc-f3caeba5e1ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5d246c43a1f234426b33ac640b3e1bb706d2f72
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376467"
---
# <a name="x-ignore-standard-include-paths"></a>/X (Standardincludepfade ignorieren)
Verhindert, dass den Compiler nach Includedateien in in der PATH und INCLUDE-Umgebungsvariablen angegebenen Verzeichnisse durchsucht.  
  
## <a name="syntax"></a>Syntax  
  
```  
/X  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können diese Option mit der [/i (Zusätzliche Includeverzeichnisse)](../../build/reference/i-additional-include-directories.md) (**/i**`directory`) Option.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die **Präprozessor** Eigenschaftenseite.  
  
4.  Ändern der **Standardincludepfad ignorieren** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.IgnoreStandardIncludePath%2A>.  
  
## <a name="example"></a>Beispiel  
 In den folgenden Befehl `/X` teilt dem Compiler, um die Umgebungsvariablen PATH und INCLUDE angegebenen Speicherorten zu ignorieren und `/I` gibt das Verzeichnis, in dem Suchen nach Includedateien:  
  
```  
CL /X /I \ALT\INCLUDE MAIN.C  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)