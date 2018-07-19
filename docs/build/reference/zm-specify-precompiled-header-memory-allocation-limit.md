---
title: -Zm (Begrenzung der Speicherzuweisung für vorkompilierten Header festlegen) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /zm
dev_langs:
- C++
helpviewer_keywords:
- PCH files, memory allocation limit
- Zm compiler option [C++]
- /Zm compiler option [C++]
- precompiled header files, memory allocation limit
- Specify Precompiled Header Memory Allocation Limit compiler option
- cl.exe compiler, memory allocation limit
- .pch files, memory allocation limit
- memory allocation, Memory Allocation Limit compiler option
- -Zm compiler option [C++]
ms.assetid: 94c77d5e-6672-46a7-92e0-3f69e277727d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 379d3d6673e673522334d685a47220bcfa2523ec
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380900"
---
# <a name="zm-specify-precompiled-header-memory-allocation-limit"></a>/Zm (Begrenzung der Speicherzuweisung für vorkompilierten Header festlegen)
Bestimmt den Arbeitsspeicher, den der Compiler für die Erstellung von vorkompilierten Headern belegt.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Zmfactor  
```  
  
## <a name="arguments"></a>Argumente  
 `factor`  
 Ein Skalierungsfaktor zur Bestimmung des Arbeitsspeichers, den der Compiler für die Erstellung vorkompilierter Header verwendet.  
  
 Das Argument `factor` ist ein Prozentsatz der Standardgröße eines vom Compiler definierten Arbeitspuffers. Standardmäßig liegt der Wert des Arguments `factor` bei 100 (Prozent), Sie können diesen Wert aber erhöhen oder verringern.  
  
## <a name="remarks"></a>Hinweise  
 In früheren Versionen von Visual C++ verwendete der Compiler eine Reihe von eigenständigen Heaps, die jeweils über eine feste Begrenzung verfügten. Derzeit werden die Heaps bei Bedarf vom Compiler dynamisch bis zu einem Grenzwert für die Heapgesamtgröße vergrößert; nur zum Erstellen vorkompilierter Header ist ein Puffer mit fester Größe erforderlich. Folglich die **/Zm** Compileroption ist selten notwendig.  
  
 Wenn der Compiler Heaps Speicherplatz nicht ausreicht und das [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) Fehlermeldung bei Verwendung der **/Zm** -Compileroption, Sie haben möglicherweise zu viel Arbeitsspeicher reserviert. Entfernen Sie die **/Zm** Option. Wenn der Compiler gibt die [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) -Fehlermeldung angezeigt wird, eine zugehörige [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) Nachricht gibt an, die `factor` Argument beim erneuten Kompilierung zu verwendende der **/Zm** Compileroption.  
  
 In der folgenden Tabelle wird dargestellt, inwiefern sich das Argument `factor` bei einer angenommenen Größe des Standardpuffers für vorkompilierte Header von 75 MB auf die maximale Speicherbelegung auswirkt.  
  
|Wert von `factor`|Maximale Speicherbelegung|  
|-----------------------|-----------------------------|  
|10|7.5 MB|  
|100|75 MB|  
|300|150 MB|  
|1000|750 MB|  
|2000|1.500 MB|  
  
## <a name="other-ways-to-set-the-memory-allocation-limit"></a>Weitere Möglichkeiten zur Festlegung der maximalen Speicherbelegung  
  
#### <a name="to-set-the-zm-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie die Compileroption "/Zm" in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie im Navigationsbereich **Konfigurationseigenschaften**, **C/C++-**, **Befehlszeile**.  
  
3.  Geben Sie die **/Zm** -Compileroption in der **Zusatzoptionen** Feld.  
  
#### <a name="to-set-the-zm-compiler-option-programmatically"></a>So legen Sie die Compileroption "/Zm" programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)