---
title: "-Qimprecise_fwaits (Entfernen von Fwaits in Try-Blöcken) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /Qimprecise_fwaits
dev_langs: C++
helpviewer_keywords:
- -Qimprecise_fwaits compiler option (C++)
- /Qimprecise_fwaits compiler option (C++)
ms.assetid: b1501f21-7e08-4fea-95e8-176ec03a635b
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9aa09590e1ede80107a085c03528b4c9089885bb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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