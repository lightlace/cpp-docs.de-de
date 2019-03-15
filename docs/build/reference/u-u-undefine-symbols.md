---
title: /U, /u (Symboldefinitionen aufheben)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCCLWCECompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCCLCompilerTool.UndefineAllPreprocessorDefinitions
- /u
- VC.Project.VCCLWCECompilerTool.UndefineAllPreprocessorDefinitions
helpviewer_keywords:
- -U compiler option [C++]
- Undefine Symbols compiler option
- /U compiler option [C++]
- U compiler option [C++]
ms.assetid: 7bc0474f-6d1f-419b-807d-0d8816763b2a
ms.openlocfilehash: bfc03ebd5c900bf8bf81b4a50eed02111baf85ee
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822485"
---
# <a name="u-u-undefine-symbols"></a>/U, /u (Symboldefinitionen aufheben)

Die **/u** -Compileroption hebt die Definition der angegebenen Präprozessorsymbols. Die **/u** -Compileroption hebt die Definition der Microsoft-spezifischen Symbole, die der Compiler definiert.

## <a name="syntax"></a>Syntax

```
/U[ ]symbol
/u
```

## <a name="arguments"></a>Argumente

*symbol*<br/>
Das Präprozessorsymbol aufgehoben werden soll.

## <a name="remarks"></a>Hinweise

Weder die **/u** oder **/u** Option kann keine Symboldefinitionen erstellt mithilfe der **#define** Richtlinie.

Die **/u** Option kann ein Symbol, das mithilfe von zuvor definiert wurde. hebt die **/d** Option.

Standardmäßig definiert der Compiler die folgenden Microsoft-spezifische Symbole.

|Symbol|Funktion|
|------------|--------------|
|_CHAR_UNSIGNED|Standardzeichentyp ist vorzeichenlos. Definiert, wenn die [/j](j-default-char-type-is-unsigned.md) angegeben wird.|
|_CPPRTTI|Definiert für Code mit kompiliert die [/Gr](gr-enable-run-time-type-information.md) Option.|
|_CPPUNWIND|Definiert für Code mit kompiliert die [/EHsc](eh-exception-handling-model.md) Option.|
|_DLL|Definiert, wenn die [/MD](md-mt-ld-use-run-time-library.md) angegeben wird.|
|_M_IX86|Standardmäßig auf 600 für X86 definierte Ziele.|
|_MSC_VER|Weitere Informationen finden Sie unter [Predefined Macros](../../preprocessor/predefined-macros.md).|
|_WIN32|Für WIN32-Anwendungen definiert. Immer definiert.|
|_MT|Definiert, wenn die [/MD oder/MT](md-mt-ld-use-run-time-library.md) angegeben wird.|

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **erweitert** Eigenschaftenseite.

1. Ändern der **Präprozessordefinitionen** oder **alle Präprozessordefinitionen aufheben** Eigenschaften.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefineAllPreprocessorDefinitions%2A> oder <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefinePreprocessorDefinitions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)<br/>
[/J (Standardzeichentyp ist „unsigned“)](j-default-char-type-is-unsigned.md)<br/>
[/GR (Laufzeittypinfo aktivieren)](gr-enable-run-time-type-information.md)<br/>
[/EH (Ausnahmebehandlungsmodell)](eh-exception-handling-model.md)<br/>
[/MD, /MT, /LD (Laufzeitbibliothek verwenden)](md-mt-ld-use-run-time-library.md)
