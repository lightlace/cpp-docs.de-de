---
title: -Oi (systeminterne Funktionen erstellen) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableIntrinsicFunctions
- /oi
- VC.Project.VCCLWCECompilerTool.EnableIntrinsicFunctions
dev_langs: C++
helpviewer_keywords:
- Oi compiler option [C++]
- intrinsic functions, generate
- /Oi compiler option [C++]
- -Oi compiler option [C++]
- generate intrinsic functions compiler option [C++]
ms.assetid: fa4a3bf6-0ed8-481b-91c0-add7636132b4
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d0a24830dbc67466e52f3f3c488dda7ac5b4778d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="oi-generate-intrinsic-functions"></a>/Oi (Intrinsische Funktionen erstellen)
Eine Funktion mit systeminternen oder sonstige spezielle Formen von der Funktion aufruft, mit denen Ihre Anwendung ersetzt werden schneller ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Oi[-]  
```  
  
## <a name="remarks"></a>Hinweise  
 Programme, die systeminterne Funktionen verwenden sind schneller, da sie keine der Mehraufwand der Funktionsaufrufe, jedoch können aufgrund des zusätzlich erstellten Codes größer sein.  
  
 Finden Sie unter [systeminterne](../../preprocessor/intrinsic.md) für Weitere Informationen, die auf dem Funktionen systeminterne Formen haben.  
  
 **/ Oi** ist nur eine Anforderung an den Compiler einige Funktionsaufrufe mit systeminternen Funktionen; ersetzt der Compiler möglicherweise rufen Sie die Funktion (und nicht durch eine systeminterne Funktion den Funktionsaufruf ersetzen), wenn sie eine bessere Leistung führt.  
  
 **X86 bestimmte**  
  
 Systeminternen Gleitkommafunktionen nicht spezielle Prüfungen auf Eingabewerte daher Arbeit in eingeschränkten Bereichen der Eingabe und anderen Ausnahmebehandlung und Grenze Bedingungen als die Bibliotheksroutinen mit dem gleichen Namen haben. Mithilfe der echten systeminternen Forms impliziert, Verlust von IEEE-Ausnahmebehandlung, und dem Verlust des `_matherr` und `errno` Funktionalität; letztere impliziert den Verlust der ANSI-Konformität. Allerdings die systeminternen Formen können erheblich beschleunigen floating-point-Intensive Programme sowie die für viele Programme, die Konformitätsprobleme geringem praktische Wert.  
  
 Sie können die [Za](../../build/reference/za-ze-disable-language-extensions.md) Compileroption, um die Generierung von echten systeminternen Gleitkommaoptionen zu überschreiben. In diesem Fall werden die Funktionen als Bibliotheksroutinen erzeugt, die Argumente direkt an den Gleitkommachip übergeben, statt sie auf dem Programmstapel abzulegen.  
  
 **END X86 bestimmte**  
  
 Verwenden Sie Sie auch [systeminterne](../../preprocessor/intrinsic.md) systeminterne Funktionen erstellen oder [-Funktion (C++)](../../preprocessor/function-c-cpp.md) um einen Funktionsaufruf explizit zu erzwingen.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die **Optimierung** Eigenschaftenseite.  
  
4.  Ändern der **systeminterne Funktionen aktivieren** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableIntrinsicFunctions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [/ O-Optionen (Code optimieren)](../../build/reference/o-options-optimize-code.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Intrinsische Compilerfunktionen](../../intrinsics/compiler-intrinsics.md)