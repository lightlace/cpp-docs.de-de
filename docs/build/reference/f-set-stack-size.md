---
title: -F (Stapelgröße festlegen) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5b464a4fb28eb83ef0570416d0cb18fd8f965e0a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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