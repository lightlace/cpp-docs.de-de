---
title: -Qimprecise_fwaits (Entfernen von Fwaits in Try-Blöcken) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Qimprecise_fwaits
dev_langs:
- C++
helpviewer_keywords:
- -Qimprecise_fwaits compiler option (C++)
- /Qimprecise_fwaits compiler option (C++)
ms.assetid: b1501f21-7e08-4fea-95e8-176ec03a635b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a688f4b9f8f3c9302bb6a49e4b0a94a0e0931b33
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378053"
---
# <a name="qimprecisefwaits-remove-fwaits-inside-try-blocks"></a>/Qimprecise_fwaits (Entfernen von fwaits in Try-Blöcken)
Entfernt die `fwait` -interne Befehle `try` blockiert, wenn Sie verwenden die [/fp: außer](../../build/reference/fp-specify-floating-point-behavior.md) -Compileroption.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Qimprecise_fwaits  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Option hat keine Auswirkung, wenn **/fp: außer** auch nicht angegeben. Bei Angabe der **/fp: außer** -Option der Compiler Fügt eine `fwait` -Befehl um jede Codezeile in einer `try` Block. Auf diese Weise kann der Compiler die bestimmte Zeile des Codes identifizieren, die eine Ausnahme erzeugt. **/ Qimprecise_fwaits** entfernt, die interne `fwait` Anweisungen, lassen nur die wartet, um die `try` Block. Dies verbessert die Leistung, aber der Compiler wird nur in der Lage, die Folgendes ein: `try` Block eine Ausnahme verursacht, nicht die Zeile.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [/ Q-Optionen (Operationen auf niedriger Ebene)](../../build/reference/q-options-low-level-operations.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)