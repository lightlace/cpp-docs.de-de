---
title: /Os, /Ot (Kompakten Code bevorzugen, Schnellen Code bevorzugen)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.FavorSizeOrSpeed
- /os
- VC.Project.VCCLCompilerTool.FavorSizeOrSpeed
helpviewer_keywords:
- favor fast code compiler option [C++]
- /Os compiler option [C++]
- Ot compiler option [C++]
- /Ot compiler option [C++]
- small machine code
- -Ot compiler option [C++]
- fast code
- favor small code compiler option [C++]
- Os compiler option [C++]
- -Os compiler option [C++]
ms.assetid: 9a340806-fa15-4308-892c-355d83cac0f2
ms.openlocfilehash: d4e8d062685a543c428f0c86a22c17c8faf017ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320174"
---
# <a name="os-ot-favor-small-code-favor-fast-code"></a>/Os, /Ot (Kompakten Code bevorzugen, Schnellen Code bevorzugen)

Minimiert oder maximiert die Größe von exe- und DLL.

## <a name="syntax"></a>Syntax

```
/Os
/Ot
```

## <a name="remarks"></a>Hinweise

**/ OS** (kompakten Code bevorzugen) minimieren die Größe von exe- und DLL, indem Sie die Anweisung an den Compiler, Größe gegenüber Geschwindigkeit zu bevorzugen. Der Compiler kann viele C- und C++-Konstrukte auf mit ähnlichen Sequenzen von Computercode reduzieren. Gelegentlich abgewogen Größe und Geschwindigkeit. Die **/OS** und **/Ot** Optionen können Sie eine Präferenz gegenüber der anderen angeben:

**/ Ot** (bevorzugen, schnellen Code bevorzugen) maximiert die Geschwindigkeit von exe- und DLL, indem Sie die Anweisung an den Compiler, Geschwindigkeit gegenüber der Größe zu bevorzugen. (Dies ist die Standardeinstellung.) Der Compiler kann viele C- und C++-Konstrukte auf mit ähnlichen Sequenzen von Computercode reduzieren. In einigen Fällen abgewogen Größe und Geschwindigkeit. Die Option/Ot wird impliziert, durch die Geschwindigkeit maximieren (["/ O2"](o1-o2-minimize-size-maximize-speed.md)) Option. Die **"/ O2"** Option kombiniert mehrere Optionen für die sehr schnellen Code zu erzeugen.

Bei Verwendung von **/OS** oder **/Ot**, dann müssen Sie auch angeben ["/ Og"](og-global-optimizations.md) um den Code optimieren.

> [!NOTE]
>  Informationen, die profilerstellung gesammelt werden, überschreiben Optimierungen, die andernfalls gültig wäre, wenn Sie angeben, **tatsächlich**, **/OS**, oder **/Ot**. Weitere Informationen [Profile-Guided Optimizations](../profile-guided-optimizations.md).

**X86 bestimmte**

Der folgende Beispielcode veranschaulicht den Unterschied zwischen den kompakten Code bevorzugen (**/OS**) Optionen und schnellen Code bevorzugen (**/Ot**) Option:

> [!NOTE]
>  Im folgenden wird das erwartete Verhalten beschrieben, bei Verwendung **/OS** oder **/Ot**. Allerdings Compilerverhalten von Version zu Version möglicherweise verschiedene Optimierungen für den folgenden Code.

```
/* differ.c
  This program implements a multiplication operator
  Compile with /Os to implement multiply explicitly as multiply.
  Compile with /Ot to implement as a series of shift and LEA instructions.
*/
int differ(int x)
{
    return x * 71;
}
```

Wie im Fragment von Computercode unten gezeigt wird, wenn DIFFER.c kompiliert wird für die Größe (**/OS**), implementiert der Compiler die multiply-Ausdruck in der return-Anweisung explizit als ein multiplizieren, um eine kurze, aber langsamere Codesequenz zu erstellen:

```
mov    eax, DWORD PTR _x$[ebp]
imul   eax, 71                  ; 00000047H
```

Klicken Sie alternativ, wenn DIFFER.c für Geschwindigkeit kompiliert wird (**/Ot**), implementiert der Compiler die multiply-Ausdruck in der return-Anweisung als eine Reihe von UMSCHALT und `LEA` Anweisungen, um eine schnelle, aber mehr Code zu erzeugen:

```
mov    eax, DWORD PTR _x$[ebp]
mov    ecx, eax
shl    eax, 3
lea    eax, DWORD PTR [eax+eax*8]
sub    eax, ecx
```

**END X86 bestimmte**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **Optimierung** Eigenschaftenseite.

1. Ändern der **Größe oder Geschwindigkeit bevorzugen** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed%2A>.

## <a name="see-also"></a>Siehe auch

[/O-Optionen (Code optimieren)](o-options-optimize-code.md)<br/>
[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
