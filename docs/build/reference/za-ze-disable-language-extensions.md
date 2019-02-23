---
title: /Za, /Ze (Spracherweiterungen deaktivieren)
ms.date: 02/19/2019
f1_keywords:
- VC.Project.VCCLWCECompilerTool.DisableLanguageExtensions
- /za
- /ze
- VC.Project.VCCLCompilerTool.DisableLanguageExtensions
helpviewer_keywords:
- -Za compiler option [C++]
- Za compiler option [C++]
- language extensions, disabling in compiler
- -Ze compiler option [C++]
- language extensions
- enable language extensions
- /Za compiler option [C++]
- /Ze compiler option [C++]
- Disable Language Extensions compiler option
- Ze compiler option [C++]
ms.assetid: 65e49258-7161-4289-a176-7c5c0656b1a2
ms.openlocfilehash: d24affdf92222ac50ffe72b3a1606d3f7030de60
ms.sourcegitcommit: e540706f4e2675e7f597cfc5b4f8dde648b007bb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/22/2019
ms.locfileid: "56676473"
---
# <a name="za-ze-disable-language-extensions"></a>/Za, /Ze (Spracherweiterungen deaktivieren)

Die **/Za** Compiler-Option deaktiviert, und gibt die Fehler für Microsoft-Erweiterungen für C, die nicht mit ANSI C89/ISO C90 kompatibel sind. Die veraltete **/Ze** -Compileroption ermöglicht das Microsoft-Erweiterungen. Standardmäßig sind Microsoft-Erweiterungen aktiviert.

## <a name="syntax"></a>Syntax

> **/Za**<br/>
> **/Ze**

## <a name="remarks"></a>Hinweise

> [!NOTE]
> Die Verwendung von **/Za** Wenn Code kompiliert wird, wie C++ wird nicht empfohlen. Die **/Ze** Option ist veraltet, da das Verhalten standardmäßig aktiviert ist. Eine Liste der Ersetzte Compileroptionen, finden Sie unter [veraltete und entfernte Compileroptionen](compiler-options-listed-by-category.md#deprecated-and-removed-compiler-options).

Microsoft C/C++-Compiler unterstützt die Kompilierung von C-Code gibt es zwei Möglichkeiten:

- Der Compiler Kompilierungsmodus C wird standardmäßig verwendet, wenn eine Quelldatei enthält einen *.c* -Erweiterung, oder wenn die [/TC](tc-tp-tc-tp-specify-source-file-type.md) oder [/TC](tc-tp-tc-tp-specify-source-file-type.md) angegeben wird. Der C-Compiler ist ein C89/C90-Compiler, der in der Standardeinstellung Microsoft-Erweiterungen der Programmiersprache C kann. Weitere Informationen zu spezifischen Erweiterungen finden Sie unter [Microsoft Extensions für C und C++](microsoft-extensions-to-c-and-cpp.md). Wenn beide C++-Kompilierung und die **/Za** Option angegeben ist, der C-Compiler entspricht genau dem Standard C89/C90. Der Compiler behandelt Schlüsselwörter als einfache Bezeichner erweiterte Microsoft, die anderen Microsoft-Erweiterungen deaktiviert und definiert automatisch die [ \_ \_STDC\_ \_ ](../../preprocessor/predefined-macros.md) vordefinierte Makro für die C-Programmen.

- Der Compiler kann C-Code in C++-Kompilierung-Modus kompilieren. Dieses Verhalten ist die Standardeinstellung für Quelldateien, die keinem *.c* -Erweiterung, und wann die [/TP](tc-tp-tc-tp-specify-source-file-type.md) oder [/TP](tc-tp-tc-tp-specify-source-file-type.md) angegeben wird. Im Modus für C++-Kompilierung unterstützt der Compiler die Teile der ISO C99- und C11-Standards, die in der C++-standard integriert haben. Fast alle C-Code ist auch gültige C++-Code. Eine kleine Anzahl von C-Schlüsselwörter und Codekonstrukte werden nicht gültige C++-Code oder in C++ anders interpretiert werden. Der Compiler verhält sich entsprechend dem C++-standard in diesen Fällen. Im Modus für C++-Kompilierung die **/Za** Option kann unerwartetes Verhalten verursachen und wird nicht empfohlen.

Andere Compileroptionen können beeinflussen, wie der Compiler stellt sicher, Einhaltung von Standards. Möglichkeiten zum Angeben von bestimmter standard C und C++-verhaltenseinstellungen, finden Sie unter den [/Zc](zc-conformance.md) -Compileroption. Zusätzliche C++-Standardkonformität-Einstellungen finden Sie unter den [/ PERMISSIVE--](permissive-standards-conformance.md) und [/Std](std-specify-language-standard-version.md) Compileroptionen.

Weitere Informationen über Konformitätsprobleme mit Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie im Navigationsbereich **Konfigurationseigenschaften** > **C/C++-** > **Sprache**.

1. Ändern der **Spracherweiterungen deaktivieren** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableLanguageExtensions%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](compiler-options.md)<br/>
[Festlegen von Compileroptionen](setting-compiler-options.md)<br/>
[/Zc (Übereinstimmung)](zc-conformance.md)<br/>
[/permissive- (Übereinstimmung mit Standards)](permissive-standards-conformance.md)<br/>
[/std (Standardversion für die Sprache festlegen)](std-specify-language-standard-version.md)<br/>
