---
title: -Arch (ARM) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 4f1406ff-f174-487c-a126-8ab06cf447c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2a411d0c7d07fb7392baaaa4fb8a8377fcb36598
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369863"
---
# <a name="arch-arm"></a>/arch (ARM)
Gibt die Architektur für die Codegenerierung auf ARM an. Siehe auch [/arch (x86)](../../build/reference/arch-x86.md) und [/arch (x64)](../../build/reference/arch-x64.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
/arch:[ARMv7VE|VFPv4]  
```  
  
## <a name="arguments"></a>Argumente  
 **/ arch: armv7ve**  
 Ermöglicht die Verwendung von Anweisungen für ARMv7VE-Virtualisierungserweiterungen.  
  
 **/ arch: vfpv4**  
 Ermöglicht die Verwendung von ARM-VFPv4-Anweisungen. Wenn diese Option nicht angegeben wird, ist VFPv3 die Standardeinstellung.  
  
## <a name="remarks"></a>Hinweise  
 Die `_M_ARM_FP` Makro (für ARM) gibt an, welche, sofern vorhanden, **/arch** -Compileroption verwendet wurde. Weitere Informationen finden Sie unter [Predefined Macros](../../preprocessor/predefined-macros.md).  
  
 Bei Verwendung von ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md) kompiliert werden, **/arch** hat keine Auswirkungen auf die codegenerierung für verwaltete Funktionen. **/ arch** nur wirkt sich auf Generation für systemeigene Funktionen Codes.  
  
### <a name="to-set-the-archarmv7ve-or-archvfpv4-compiler-option-in-visual-studio"></a>Zum Festlegen der /arch:ARMv7VE oder /arch:VFPv4-Compileroption in Visual Studio  
  
1.  Öffnen der **Eigenschaftenseiten** im Dialogfeld für das Projekt. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **C/C++-** Ordner.  
  
3.  Wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
4.  In der **Zusatzoptionen** fügen `/arch:ARMv7VE` oder `/arch:VFPv4`.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [/ arch (minimale CPU-Architektur)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)