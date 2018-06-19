---
title: -Homeparams (Registerparameter in den Stapel kopieren) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /homeparams
dev_langs:
- C++
helpviewer_keywords:
- /homeparams compiler option [C++]
- -homeparams compiler option [C++]
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ffc9b37ebdcbb380186c7840f5ebd956708a2dc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374397"
---
# <a name="homeparams-copy-register-parameters-to-stack"></a>/homeparams (Registerparameter in den Stapel kopieren)
Erzwingt, dass in Registern übergebene Parameter beim Funktionseinstieg in ihre Speicherorte auf dem Stapel geschrieben werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
/homeparams  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Compileroption gilt nur für die [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] -Compiler (systemeigene und Cross-Compiler).  
  
 Wenn Parameter übergeben werden, eine [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] Kompilierung Aufrufkonventionen Stapelspeicher für Parameter erforderlich, dies gilt auch für Parameter, die in Registern übergeben. Weitere Informationen finden Sie unter [Parameterübergabe](../../build/parameter-passing.md). Allerdings werden standardmäßig in einem Releasebuild die Registerparameter nicht in den Stapel, in der räumlichen Ausdehnung geschrieben werden, die bereits für die Parameter bereitgestellt wird. Dies erschwert es einen optimierten (Version)-Build des Programms zu debuggen.  
  
 Verwenden Sie für einen Releasebuild **/homeparams** um sicherzustellen, dass die Anwendung zu debuggen. **/ homeparams** einer verminderten Leistung, da es eine Schleife beim Laden der Registerparameter auf den Stapel erforderlich sind.  
  
 In einem Debugbuild wird der Stapel immer mit in Registern übergebene Parameter aufgefüllt.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)