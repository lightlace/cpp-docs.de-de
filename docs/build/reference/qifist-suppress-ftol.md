---
title: -QIfist (_ftol unterdrücken) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /qifist
dev_langs:
- C++
helpviewer_keywords:
- QIfist compiler option [C++]
- -QIfist compiler option [C++]
- /QIfist compiler option [C++]
ms.assetid: 1afd32a5-f658-4b66-85f4-e0ce4cb955bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b693f78b6fbd9a11dbe98ec2eacc3d781ffd7ebf
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42572062"
---
# <a name="qifist-suppress-ftol"></a>/QIfist (_ftol unterdrücken)
Veraltet. Unterdrückt den Aufruf der `_ftol` -Hilfsfunktion, wenn eine Konvertierung von einem Gleitkommatyp zu einem ganzzahligen Typ erforderlich ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
/QIfist  
```  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  **/ QIfist** steht nur in Compilern X86; diese Compileroption ist nicht in Compilern für X64 oder ARM abzielen.  
  
 Durch die `_ftol`-Funktion wird nicht nur ein Gleitkommatyp in einen ganzzahligen Typ konvertiert, sondern ist auch gewährleistet, dass die Gleitkommaeinheit (Floating-Point Unit, FPU) gegen 0 (null) rundet (abschneidet), indem die Bits 10 und 11 des Steuerworts entsprechend festgelegt werden. Dadurch wird garantiert, dass die Konvertierung eines Gleitkommatyps in einen ganzzahligen Typ wie im ANSI C-Standard durchgeführt wird, dass also der Teil nach dem Komma verworfen wird. Bei Verwendung **/QIfist**, diese nicht mehr sichergestellt. Das Rundungsverhalten entspricht einem der vier im Intel-Referenzmaterial dokumentierten Modi:  
  
-   Runden auf die nächste Maschinenzahl (auf eine gerade Zahl bei gleichem Abstand)  
  
-   Runden in Richtung minus unendlich  
  
-   Runden in Richtung plus unendlich  
  
-   Runden in Richtung Null (0)  
  
 Sie können die [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) C Run-Time-Funktion, um das Rundungsverhalten der FPU ändern. Die Standardeinstellung der FPU ist "Runden auf die nächste Maschinenzahl". Mithilfe von **/QIfist** kann die Leistung Ihrer Anwendung, aber nicht ohne das Risiko erhöht. Die Teile des Codes, die Rundungsmodi, bevor der vertrauenden Seite, auf Code mit erstellt sind, sollten gründlich getestet **/QIfist** in produktionsumgebungen.  
  
 [/ arch (x86)](../../build/reference/arch-x86.md) und **/QIfist** kann nicht in derselben Kompiliereinheit verwendet werden.  
  
> [!NOTE]
>  **/ QIfist** ist nicht wirksam standardmäßig, da die gerundeten bits auch das Gleitkomma auf Gleitkomma beeinflussen Punkt runden (Dies geschieht, nachdem jeder Berechnung), wenn Sie die Flags für die Rundung von C-Format (gegen Null) festlegen, die gleitkommaberechnungen Berechnungen können unterschiedlich sein. **/ QIfist** sollte nicht verwendet werden, wenn der Code auf das erwartete Verhalten des Bruchteils der Gleitkommazahl aufbaut. Wenn Sie nicht sicher sind, verwenden Sie keine **/QIfist**.  
  
 Die **/QIfist** Option ist ab Visual Studio 2005 veraltet. Für den Compiler wurde die Geschwindigkeit der Konvertierung von Gleitkommatyp in ganzzahligen Typ deutlich erhöht. Eine Liste der Ersetzte Compileroptionen, finden Sie unter **veraltete und entfernte Compileroptionen** in [Compiler Options Listed by Category](../../build/reference/compiler-options-listed-by-category.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [/ Q-Optionen (Operationen auf niedriger Ebene)](../../build/reference/q-options-low-level-operations.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)