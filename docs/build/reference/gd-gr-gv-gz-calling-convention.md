---
title: /Gd, /Gr, /Gv, /Gz (Aufrufkonvention)
ms.date: 09/05/2018
f1_keywords:
- /gr
- /Gv
- /gz
- /Gd
- VC.Project.VCCLCompilerTool.CallingConvention
helpviewer_keywords:
- -Gd compiler option [C++]
- -Gv compiler option [C++]
- /Gv compiler option [C++]
- -Gr compiler option [C++]
- Gd compiler option [C++]
- Gr compiler option [C++]
- /Gz compiler option [C++]
- -Gz compiler option [C++]
- /Gd compiler option [C++]
- Gz compiler option [C++]
- Gv compiler option [C++]
- /Gr compiler option [C++]
ms.assetid: fd3110cb-2d77-49f2-99cf-a03f9ead00a3
ms.openlocfilehash: 72d65ce7471ed047ab8347a45c58a6b8a9f39a7a
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450848"
---
# <a name="gd-gr-gv-gz-calling-convention"></a>/Gd, /Gr, /Gv, /Gz (Aufrufkonvention)

Mit diesen Optionen wird festgelegt, in welcher Reihenfolge die Funktionsargumente auf den Stapel verschoben werden, ob die aufrufende oder die aufgerufene Funktion die Argumente am Ende des Aufrufs aus dem Stapel entfernt, und welche Namensergänzungskonvention der Compiler zur Erkennung einzelner Funktionen verwendet.

## <a name="syntax"></a>Syntax

> **/Gd**<br/>
> **/Gr**<br/>
> **/Gv**<br/>
> **/Gz**<br/>

## <a name="remarks"></a>Hinweise

**/Gd**, die Standardeinstellung, gibt die [__cdecl](../../cpp/cdecl.md)-Aufrufkonvention für alle Funktionen an, mit Ausnahme von C++-Memberfunktionen und allen Funktionen, die als [__stdcall](../../cpp/stdcall.md), [__fastcall](../../cpp/fastcall.md) oder [__vectorcall](../../cpp/vectorcall.md) gekennzeichnet sind.

**/Gr** legt die `__fastcall`-Aufrufkonvention für alle Funktionen mit Ausnahme von C++-Memberfunktionen, als `main` benannten Funktionen und mit `__cdecl`, `__stdcall` oder `__vectorcall` gekennzeichneten Funktionen fest. Alle `__fastcall`-Funktionen müssen Prototypen haben. Diese Aufrufkonvention ist nur in Compilern verfügbar, die auf x86 abzielen, und wird von Compilern ignoriert, die auf andere Architekturen abzielen.

**/Gz** legt die `__stdcall`-Aufrufkonvention für alle Funktionen mit Ausnahme von C++-Memberfunktionen, als `main` benannten Funktionen und mit `__cdecl`, `__fastcall` oder `__vectorcall` gekennzeichneten Funktionen fest. Alle `__stdcall`-Funktionen müssen Prototypen haben. Diese Aufrufkonvention ist nur in Compilern verfügbar, die auf x86 abzielen, und wird von Compilern ignoriert, die auf andere Architekturen abzielen.

**/ GV** gibt an, die `__vectorcall` -Aufrufkonvention für alle Funktionen außer C++ Memberfunktionen, Funktionen, die mit dem Namen `main`, Funktionen mit einer `vararg` Liste variabler Argumente oder Funktionen, die mit einem widersprüchlichen markiert sind `__cdecl`, `__stdcall`, oder `__fastcall` Attribut. Diese Aufrufkonvention ist nur auf x86- und x64-Architekturen verfügbar, die „/arch:SSE2“ und höher unterstützen, und wird von Compilern ignoriert, die auf die ARM-Architektur abzielen.

Funktionen, die eine variable Anzahl von Argumenten akzeptieren, müssen mit `__cdecl` gekennzeichnet sein.

**/Gd**, **/Gr**, **/Gv** und **/Gz** sind nicht mit [/clr:safe](clr-common-language-runtime-compilation.md) oder **/clr:pure** kompatibel. Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet und werden in Visual Studio 2017 und höher nicht unterstützt.

> [!NOTE]
> Für x86-Prozessoren verwenden C++-Memberfunktionen standardmäßig [__thiscall](../../cpp/thiscall.md).

Für alle Prozessoren verwendet eine Memberfunktion, die explizit als `__cdecl`, `__fastcall`, `__vectorcall` oder `__stdcall` gekennzeichnet ist, die angegebene Aufrufkonvention, wenn diese nicht auf dieser Architektur ignoriert wird. Eine Memberfunktion, die eine variable Anzahl von Argumenten zulässt, verwendet immer die Aufrufkonvention `__cdecl`.

Diese Compileroptionen haben keine Auswirkungen auf die Namensergänzung von C++-Methoden und -Funktionen. Sofern sie nicht als `extern "C"` deklariert sind, kommt für C++-Methoden und -Funktionen ein anderes Schema für Namensergänzungen zur Anwendung. Weitere Informationen finden Sie unter [Ergänzte Namen](decorated-names.md).

Weitere Informationen zu Aufrufkonventionen finden Sie unter [Calling Conventions (Aufrufkonventionen)](../../cpp/calling-conventions.md).

## <a name="cdecl-specifics"></a>__cdecl-Besonderheiten

Auf x86-Prozessoren werden alle Funktionsargumente auf dem Stapel von rechts nach links übergeben. Auf ARM- und x64-Architekturen werden einige Argumente nach Register übergeben und der Rest wird auf dem Stapel von rechts nach links übergeben. Die Aufrufroutine ruft die Argumente vom Stapel auf.

Für C verwendet die `__cdecl`-Benennungskonvention den Funktionsnamen mit einem führenden Unterstrich (`_`); Groß-/Kleinbuchstaben werden nicht umgewandelt. Sofern sie nicht als `extern "C"` deklariert sind, kommt für C++-Funktionen ein anderes Schema für Namensergänzungen zur Anwendung. Weitere Informationen finden Sie unter [Ergänzte Namen](decorated-names.md).

## <a name="fastcall-specifics"></a>__fastcall-Besonderheiten

Einige der Argumente einer `__fastcall`-Funktion werden an Register übergeben (für x86-Prozessoren, ECX und EDX), der Rest wird von rechts nach links auf den Stapel verschoben. Die aufgerufene Routine nimmt diese Argumente vor ihrem Rücksprung vom Stapel auf. Normalerweise verringert **/Gr** die Ausführungszeit.

> [!NOTE]
> Seien Sie vorsichtig, wenn Sie die `__fastcall`-Aufrufkonvention für eine in Inlineassemblysprache geschriebene Funktion verwenden. Es kann zu Konflikten zwischen Ihrer Verwendung von Registern und deren Verwendung durch den Compiler kommen.

Für C verwendet die `__fastcall`-Benennungskonvention den Funktionsnamen, mit einem führenden at-Zeichen ( **\@** ), gefolgt von der Größe der Funktionsargumente in Byte. Groß-/Kleinbuchstaben werden nicht umgewandelt. Der Compiler verwendet für die Benennungskonvention diese Vorlage:

`@function_name@number`

Mit der Benennungskonvention `__fastcall` sollten Sie die standardmäßigen Includedateien verwenden. Andernfalls erhalten Sie nicht aufgelöste externe Verweise.

## <a name="stdcall-specifics"></a>__stdcall-Besonderheiten

Die Argumente einer `__stdcall`-Funktion werden von rechts nach links auf dem Stapel abgelegt, und die aufgerufene Funktion nimmt diese Argumente vor ihrer Rücksetzung vom Stapel.

Für C verwendet die `__stdcall`-Benennungskonvention den Funktionsnamen mit führendem Unterstrich ( **\_** ), gefolgt von einem at-Zeichen ( **\@** )und der Größe der Funktionsargumente in Byte. Groß-/Kleinbuchstaben werden nicht umgewandelt. Der Compiler verwendet für die Benennungskonvention diese Vorlage:

`_functionname@number`

## <a name="vectorcall-specifics"></a>__vectorcall-Besonderheiten

Die ganzzahligen Argumente einer `__vectorcall`-Funktion werden nach Wert übergeben, wobei bis zu zwei (auf x86) oder vier (x64) Ganzzahlregister und bis zu sechs XMM-Register für Gleitkomma- und Vektorwerte verwendet werden. Der Rest wird auf dem Stapel von rechts nach links übergeben. Die aufgerufene Funktion bereinigt den Stapel vor dem Zurückgeben. Vektor- und Gleitkomma-Rückgabewerte werden in XMM0 zurückgegeben.

Für C verwendet die `__vectorcall`-Benennungskonvention den Funktionsnamen, gefolgt von zwei at-Zeichen ( **\@\@** )und der Größe der Funktionsargumente in Byte. Groß-/Kleinbuchstaben werden nicht umgewandelt. Der Compiler verwendet für die Benennungskonvention diese Vorlage:

`functionname@@number`

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Wählen Sie die **C/C++**  > **Erweitert**-Eigenschaftenseite aus.

1. Ändern Sie die Eigenschaft **Aufrufkonvention**.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CallingConvention%2A>.

## <a name="see-also"></a>Siehe auch

- [MSVC-Compileroptionen](compiler-options.md)
- [Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
