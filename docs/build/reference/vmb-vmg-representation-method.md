---
title: -Vmb, - Vmg (Darstellungsmethode) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5263b6c7ca227a10b34c32e0b0801eeddf07b9cd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377182"
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