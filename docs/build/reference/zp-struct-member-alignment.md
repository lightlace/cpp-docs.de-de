---
title: -Zp (Strukturmembers) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /zp
- VC.Project.VCCLCompilerTool.StructMemberAlignment
- VC.Project.VCCLWCECompilerTool.StructMemberAlignment
dev_langs:
- C++
helpviewer_keywords:
- Struct Member Alignment compiler option
- Zp compiler option
- /Zp compiler option [C++]
- -Zp compiler option [C++]
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d387e0ab020e96afb3e2975b5c8686b668cbc10
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="zp-struct-member-alignment"></a>/Zp (Ausrichten des Strukturmembers)
Steuert, wie die Member einer Struktur in den Speicher gepackt werden, und gibt an, die dieselbe Anordnung für alle Strukturen in einem Modul.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Zp[1|2|4|8|16]  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie diese Option angeben, wird jeder Strukturmember nach dem ersten entweder die Größe des Membertyps gespeichert oder `n`-Byte-Grenzen (wobei `n` ist 1, 2, 4, 8 oder 16), welcher Wert kleiner ist.  
  
 Die verfügbaren Werte werden in der folgenden Tabelle beschrieben.  
  
 1  
 Packs Strukturen auf 1-Byte-Grenzen. Identisch mit **/Zp**.  
  
 2  
 Packs Strukturen auf 2-Byte-Grenzen.  
  
 4  
 Packs Strukturen an 4-Byte-Grenzen.  
  
 8  
 Packs Strukturen an 8-Byte-Grenzen (Standard).  
  
 16  
 Packs Strukturen an 16-Byte-Grenzen.  
  
 Sie sollten diese Option nicht verwenden, es sei denn, Sie über bestimmte ausrichtungsanforderungen verfügen.  
  
 Sie können auch [Pack](../../preprocessor/pack.md) Ausrichten von Strukturen. Weitere Informationen zur Ausrichtung finden Sie unter:  
  
-   [align](../../cpp/align-cpp.md)  
  
-   [__alignof-Operator](../../cpp/alignof-operator.md)  
  
-   [__unaligned](../../cpp/unaligned.md)  
  
-   [Beispiele für die Strukturausrichtung](../../build/examples-of-structure-alignment.md) (X64 bestimmte)  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die **Codegenerierung** Eigenschaftenseite.  
  
4.  Ändern der **Ausrichten des Strukturmembers** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)