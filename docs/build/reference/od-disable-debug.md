---
title: -Od (deaktivieren (Debuggen)) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /od
dev_langs: C++
helpviewer_keywords:
- no optimizations
- fast compiling
- /Od compiler option [C++]
- disable optimizations
- Od compiler option [C++]
- -Od compiler option [C++]
- disable (debug) compiler option [C++]
ms.assetid: b1ac31b7-e086-4eeb-be5e-488f7513f5f5
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c1d26742d4922dac176f198037ad1cce29e722d0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="od-disable-debug"></a>/Od (Deaktivieren (Debuggen))
Deaktiviert alle Optimierungen im Programm und beschleunigt die Kompilierung.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Od  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Option ist die Standardeinstellung. Da **/Od** Verschieben von Code unterdrückt es vereinfacht das Debuggen. Weitere Informationen zu Compileroptionen für das Debuggen, finden Sie unter ["/ Z7", / Zi, / Zi (Debuginformationsformat)](../../build/reference/z7-zi-zi-debug-information-format.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die **Optimierung** Eigenschaftenseite.  
  
4.  Ändern der **Optimierung** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [/ O-Optionen (Code optimieren)](../../build/reference/o-options-optimize-code.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [/Z7, /Zi, /ZI (Debuginformationsformat)](../../build/reference/z7-zi-zi-debug-information-format.md)