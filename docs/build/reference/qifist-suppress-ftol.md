---
title: /QIfist (_ftol unterdrücken)
ms.date: 11/04/2016
f1_keywords:
- /qifist
helpviewer_keywords:
- QIfist compiler option [C++]
- -QIfist compiler option [C++]
- /QIfist compiler option [C++]
ms.assetid: 1afd32a5-f658-4b66-85f4-e0ce4cb955bd
ms.openlocfilehash: 7af88c91793688d23cf35177ae7a5250b04832a8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319277"
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

- Runden auf die nächste Maschinenzahl (auf eine gerade Zahl bei gleichem Abstand)

- Runden in Richtung minus unendlich

- Runden in Richtung plus unendlich

- Runden in Richtung Null (0)

Sie können die [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) C Run-Time-Funktion, um das Rundungsverhalten der FPU ändern. Die Standardeinstellung der FPU ist "Runden auf die nächste Maschinenzahl". Mithilfe von **/QIfist** kann die Leistung Ihrer Anwendung, aber nicht ohne das Risiko erhöht. Die Teile des Codes, die Rundungsmodi, bevor der vertrauenden Seite, auf Code mit erstellt sind, sollten gründlich getestet **/QIfist** in produktionsumgebungen.

[/ arch (x86)](arch-x86.md) und **/QIfist** kann nicht in derselben Kompiliereinheit verwendet werden.

> [!NOTE]
>  **/ QIfist** ist nicht wirksam standardmäßig, da die gerundeten bits auch das Gleitkomma auf Gleitkomma beeinflussen Punkt runden (Dies geschieht, nachdem jeder Berechnung), wenn Sie die Flags für die Rundung von C-Format (gegen Null) festlegen, die gleitkommaberechnungen Berechnungen können unterschiedlich sein. **/ QIfist** sollte nicht verwendet werden, wenn der Code auf das erwartete Verhalten des Bruchteils der Gleitkommazahl aufbaut. Wenn Sie nicht sicher sind, verwenden Sie keine **/QIfist**.

Die **/QIfist** Option ist ab Visual Studio 2005 veraltet. Für den Compiler wurde die Geschwindigkeit der Konvertierung von Gleitkommatyp in ganzzahligen Typ deutlich erhöht. Eine Liste der Ersetzte Compileroptionen, finden Sie unter **veraltete und entfernte Compileroptionen** in [Compiler Options Listed by Category](compiler-options-listed-by-category.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[/Q-Optionen (Vorgänge auf niedriger Ebene)](q-options-low-level-operations.md)<br/>
[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
