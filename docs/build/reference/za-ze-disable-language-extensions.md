---
title: -Za, - Ze (Spracherweiterungen deaktivieren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.DisableLanguageExtensions
- /za
- /ze
- VC.Project.VCCLCompilerTool.DisableLanguageExtensions
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d239b6153a2fc725c2add3eddb5fbaace406469
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712815"
---
# <a name="za-ze-disable-language-extensions"></a>/Za, /Ze (Spracherweiterungen deaktivieren)

Die **/Za** Compileroption gibt einen Fehler für Sprachkonstrukte, die nicht mit ANSI-C89 oder ISO C ++ 11 kompatibel sind. Die **/Ze** -Compileroption verwenden, die standardmäßig aktiviert ist, ermöglicht Microsoft-Erweiterungen.

## <a name="syntax"></a>Syntax

```
/Za
/Ze
```

## <a name="remarks"></a>Hinweise

> [!NOTE]
>  Die **/Ze** Option ist veraltet, da das Verhalten standardmäßig aktiviert ist. Es wird empfohlen, die [/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md) Compileroptionen sprachspezifischen Erweiterungsfunktionen steuern. Eine Liste der Ersetzte Compileroptionen, finden Sie unter den **veraltete und entfernte Compileroptionen** im Abschnitt [Compiler Options Listed by Category](../../build/reference/compiler-options-listed-by-category.md).

Visual C++-Compiler bietet eine Reihe von Funktionen über die angegebenen in das ANSI-C89, ISO C99 oder ISO C++-Standards. Diese Funktionen werden zusammenfassend als Microsoft-Erweiterungen für C und C++ bezeichnet. Diese Erweiterungen sind standardmäßig verfügbar und nicht verfügbar, wenn die **/Za** angegeben wird. Weitere Informationen zu spezifischen Erweiterungen finden Sie unter [Microsoft Extensions für C und C++](../../build/reference/microsoft-extensions-to-c-and-cpp.md).

Es wird empfohlen, dass Sie spracherweiterungen werden, indem deaktiviert die **/Za** option, wenn Sie Ihr Programm in andere Umgebungen zu portieren möchten. Bei der **/Za** angegeben ist, behandelt der Compiler-Schlüsselwörter als einfache Bezeichner erweiterte Microsoft, die anderen Microsoft-Erweiterungen deaktiviert und definiert automatisch die `__STDC__` vordefiniertes Makro für die C-Programmen.

Andere Compileroptionen verwendet mit **/Za** kann beeinflussen, wie der Compiler stellt sicher, Einhaltung von Standards.

Möglichkeiten zum Angeben von Einstellungen für das bestimmte standardkonforme Verhalten, finden Sie unter den [/Zc](../../build/reference/zc-conformance.md) -Compileroption.

Weitere Informationen über Konformitätsprobleme mit Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie im Navigationsbereich **Konfigurationseigenschaften**, **C/C++-**, **Sprache**.

1. Ändern der **Spracherweiterungen deaktivieren** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableLanguageExtensions%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)
