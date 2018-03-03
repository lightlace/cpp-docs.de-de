---
title: -U -u (Symboldefinitionen aufheben) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCCLWCECompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCCLCompilerTool.UndefineAllPreprocessorDefinitions
- /u
- VC.Project.VCCLWCECompilerTool.UndefineAllPreprocessorDefinitions
dev_langs:
- C++
helpviewer_keywords:
- -U compiler option [C++]
- Undefine Symbols compiler option
- /U compiler option [C++]
- U compiler option [C++]
ms.assetid: 7bc0474f-6d1f-419b-807d-0d8816763b2a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 18fdaf0c2cb980f1ed19fdfc0577769a9985cf85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="u-u-undefine-symbols"></a>/U, /u (Symboldefinitionen aufheben)
Die **/u** -Compileroption hebt die Definition der angegebenen-Präprozessorsymbol verwendet. Die **/u** -Compileroption hebt die Definition der Microsoft-spezifische Symbole, die der Compiler definiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
/U[ ]symbol  
/u  
```  
  
## <a name="arguments"></a>Argumente  
 `symbol`  
 Das Präprozessorsymbol um aufzuheben.  
  
## <a name="remarks"></a>Hinweise  
 Weder die **/u** oder **/u** Option kann keine Symboldefinitionen erstellt mithilfe der **#define** Richtlinie.  
  
 Die **/u** Option kann keine Symboldefinitionen den zuvor mithilfe definierten der **/d** Option.  
  
 Standardmäßig definiert der Compiler die folgenden Microsoft-spezifische Symbole.  
  
|Symbol|Funktion|  
|------------|--------------|  
|_CHAR_UNSIGNED|Standardzeichentyp ist nicht signiert. Definiert, wenn die ["/ j"](../../build/reference/j-default-char-type-is-unsigned.md) angegeben wird.|  
|_CPPRTTI|Definiert, um kompilierten Code mit der [/Gr](../../build/reference/gr-enable-run-time-type-information.md) Option.|  
|_CPPUNWIND|Definiert, um kompilierten Code mit der [/EHsc /](../../build/reference/eh-exception-handling-model.md) Option.|  
|_DLL|Definiert, wenn die [/MD](../../build/reference/md-mt-ld-use-run-time-library.md) angegeben wird.|  
|_M_IX86|Standardmäßig auf 600 für X86 definierten Ziele.|  
|_MSC_VER|Weitere Informationen finden Sie unter [Predefined Macros](../../preprocessor/predefined-macros.md).|  
|_WIN32|Für WIN32-Anwendungen definiert. Immer definiert.|  
|_MT|Definiert, wenn die [/MD oder/MT](../../build/reference/md-mt-ld-use-run-time-library.md) angegeben wird.|  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die **erweitert** Eigenschaftenseite.  
  
4.  Ändern der **Präprozessordefinitionen** oder **alle Präprozessordefinitionen** Eigenschaften.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefineAllPreprocessorDefinitions%2A> oder <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefinePreprocessorDefinitions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [/ J (standardmäßig Typ unsigned Char)](../../build/reference/j-default-char-type-is-unsigned.md)   
 [/ GR (Laufzeit-Typeninformation aktivieren)](../../build/reference/gr-enable-run-time-type-information.md)   
 [/ EH (Ausnahmebehandlungsmodell)](../../build/reference/eh-exception-handling-model.md)   
 [/ MD, / MT, / ld (Laufzeitbibliothek verwenden)](../../build/reference/md-mt-ld-use-run-time-library.md)