---
title: -Qsafe_fp_loads | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 2b2ce52d-ba57-4bd3-a739-47a7f8bfaba9
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a9e572c8a4d353aaee4e82e8c7bdc3f719475c03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="qsafefploads"></a>/Qsafe_fp_loads
Erfordert ganzzahlige Verschiebungsanweisungen für Gleitkommawerte und deaktiviert bestimmte Gleitkomma-Ladeoptimierungen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Qsafe_fp_loads  
```  
  
## <a name="remarks"></a>Hinweise  
 **/ Qsafe_fp_loads** ist nur in Compilern verfügbar, die gezielt X86; es ist nicht in Compilern, die auf X64 oder ARM abzielen.  
  
 **/ Qsafe_fp_loads** erzwingt der Compiler, ganzzahlige verschiebungsanweisungen anstelle der Gleitkomma-verschiebungsanweisungen verwenden Sie zum Verschieben von Daten zwischen Arbeitsspeicher und MMX registriert. Diese Option deaktiviert auch Registerladeoptimierung für Gleitkommawerte, die in mehreren Kontrollpfaden geladen werden können, wenn der Wert (beispielsweise NaN) beim Laden eine Ausnahme verursacht.  
  
 Diese Option wird überschrieben, indem [/fp: außer](../../build/reference/fp-specify-floating-point-behavior.md). **/ Qsafe_fp_loads** gibt eine Teilmenge des Compilerverhaltens an, die angegebenen **/fp: außer**.  
  
 **/ Qsafe_fp_loads** ist inkompatibel mit ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md) und [/fp: fast](../../build/reference/fp-specify-floating-point-behavior.md). Weitere Informationen zu den floating Point-Compileroptionen finden Sie unter [/fp (Festlegen von Floating-Verhalten)](../../build/reference/fp-specify-floating-point-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **C/C++-** Ordner.  
  
3.  Wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [/ Q-Optionen (Operationen auf niedriger Ebene)](../../build/reference/q-options-low-level-operations.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)