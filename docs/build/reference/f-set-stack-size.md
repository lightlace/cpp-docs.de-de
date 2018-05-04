---
title: -F (Stapelgröße festlegen) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /f
dev_langs:
- C++
helpviewer_keywords:
- set stack size compiler option
- F compiler option [C++]
- -F compiler option [C++]
- /F compiler option [C++]
- stack, setting size
ms.assetid: 17320b6f-8305-445b-9ec2-75833f4b29e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed0ad03d18493cc5618f9aad2a16b07e4a01717f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="f-set-stack-size"></a>/F (Stapelgröße festlegen)
Legt die Stapelgröße der Anwendung in Bytes fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
/F number  
```  
  
## <a name="arguments"></a>Argumente  
 `number`  
 Die Stapelgröße in Bytes.  
  
## <a name="remarks"></a>Hinweise  
 Ohne diese Option wird standardmäßig die Größe des Stapels auf 1 MB. Die `number` Argument Decimal oder C-Notation werden kann. Das Argument reichen von 1 bis die maximale Stapelgröße, die vom Linker akzeptiert. Der Linker rundet den angegebenen Wert in der nächsten 4 Bytes. Der Abstand zwischen den **/f** und `number` ist optional.  
  
 Sie müssen möglicherweise die Größe des Stapels zu erhöhen, wenn das Programm Stapelüberlauf Nachrichten abruft.  
  
 Sie können auch die Größe des Stapels festgelegt:  
  
-   Mithilfe der **/STACK** (Linkeroption). Weitere Informationen finden Sie unter [/STACK](../../build/reference/stack.md).  
  
-   Verwenden von EDITBIN für die .exe-Datei. Weitere Informationen finden Sie unter [EDITBIN-Referenz](../../build/reference/editbin-reference.md).  
  
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