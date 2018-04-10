---
title: -Vmb, - Vmg (Darstellungsmethode) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- /vmb
- /vmg
dev_langs:
- C++
helpviewer_keywords:
- vmb compiler option [C++]
- -vmg compiler option [C++]
- vmg compiler option [C++]
- -vmb compiler option [C++]
- /vmb compiler option [C++]
- representation method compiler options [C++]
- /vmg compiler option [C++]
ms.assetid: ecdb391c-7dab-40b1-916b-673d10889fd4
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4a9d64f8b1035f731adef79356d24eeb3e4f7ee3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="vmb-vmg-representation-method"></a>/vmb, /vmg (Darstellungsmethode)
Wählen Sie die Methode, die der Compiler verwendet, die Zeiger auf Member der Klasse darstellt.  
  
 Verwendung **/vmb** , wenn Sie immer eine Klasse definieren, bevor Sie einen Zeiger auf einen Member der Klasse deklarieren.  
  
 Verwendung **/vmg** auf einen Zeiger auf einen Member einer Klasse deklarieren, bevor Sie die Klasse definiert. Diese Anforderung kann auftreten, wenn Sie Elemente in zwei verschiedenen Klassen definieren, die aufeinander verweisen. Für solche gegenseitig verweisenden Klassen muss eine Klasse verwiesen werden, bevor sie definiert ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
/vmb  
/vmg  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können auch [Pointers_to_members](../../preprocessor/pointers-to-members.md) oder [Vererbungsschlüsselwörter](../../cpp/inheritance-keywords.md) in Ihrem Code an eine zeigerdarstellung.  
  
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