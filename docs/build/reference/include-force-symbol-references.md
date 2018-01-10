---
title: -INCLUDE (Symbolverweise erzwingen) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /include
- VC.Project.VCLinkerTool.ForceSymbolReferences
dev_langs: C++
helpviewer_keywords:
- INCLUDE linker option
- force symbol references linker option
- symbol references linker force
- /INCLUDE linker option
- symbols, add to symbol table
- -INCLUDE linker option
ms.assetid: 4a039677-360a-480f-bd0b-448e239b449c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8caf060d278e7ac2c92c38ad58e9c4c55eab632c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="include-force-symbol-references"></a>/INCLUDE (Symbolverweise erzwingen)
```  
/INCLUDE:symbol  
```  
  
## <a name="remarks"></a>Hinweise  
 Dabei gilt:  
  
 `symbol`  
 Gibt ein Symbol der Symboltabelle hinzugefügt werden.  
  
## <a name="remarks"></a>Hinweise  
 Die Option/INCLUDE weist den Linker ein angegebenen Symbols zur Symboltabelle hinzugefügt.  
  
 Um mehrere Symbole anzugeben, geben Sie ein Komma (,), ein Semikolon (;) oder ein Leerzeichen zwischen den Symbolnamen. Geben Sie in der Befehlszeile/include:`symbol` einmal für jedes Symbol.  
  
 Der Linker löst `symbol` durch Hinzufügen des Objekts, das die Symboldefinition an das Programm enthält. Diese Funktion ist nützlich, wenn Sie z. B. ein Bibliotheksobjekt, die andernfalls nicht zu dem Programm verknüpft werden.  
  
 Das Entfernen dieses Symbols durch Angeben eines Symbols mit dieser Option überschreibt [/OPT: REF](../../build/reference/opt-optimizations.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die **Eingabe** Eigenschaftenseite.  
  
4.  Ändern der **Symbolverweise erzwingen** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ForceSymbolReferences%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)