---
title: + C (Kommentare bei der Vorverarbeitung beibehalten) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.KeepComments
- /c
- VC.Project.VCCLWCECompilerTool.KeepComments
dev_langs: C++
helpviewer_keywords:
- comments, not stripping during preprocessing
- preserve comments during preprocessing
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 944567ca-16bc-4728-befe-d414a7787f26
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f9aaa15e4d256ed296094e707472cfdd05cf917f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="c-preserve-comments-during-preprocessing"></a>/C (Kommentare bei der Vorverarbeitung beibehalten)
Behält Kommentare beim Präprozessorlauf bei  
  
## <a name="syntax"></a>Syntax  
  
```  
/C  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Compileroption erfordert die **/e**, **/p**, oder **/EP** Option.  
  
 Im folgenden Codebeispiel wird die Quelle Codekommentars angezeigt.  
  
```  
// C_compiler_option.cpp  
// compile with: /E /C /c  
int i;   // a variable  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe.  
  
```  
#line 1 "C_compiler_option.cpp"  
int i;   // a variable  
```  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die **Präprozessor** Eigenschaftenseite.  
  
4.  Ändern der **Kommentare beibehalten** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.KeepComments%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [/ E (Vorverarbeitung an "stdout")](../../build/reference/e-preprocess-to-stdout.md)   
 [/ P (vorverarbeitung in eine Datei)](../../build/reference/p-preprocess-to-a-file.md)   
 [/ EP (Vorverarbeitung an "stdout" ohne #line-Direktiven)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)