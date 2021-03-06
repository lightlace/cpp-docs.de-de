---
title: /J (Standardmäßig "unsigned char")
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.DefaultCharIsUnsigned
- VC.Project.VCCLWCECompilerTool.DefaultCharIsUnsigned
- /j
helpviewer_keywords:
- defaults, char type
- char data type
- -J compiler option [C++]
- /J compiler option [C++]
- J compiler option [C++]
- default char type is unsigned
ms.assetid: 50973667-6638-491e-9c41-bff73acae19f
ms.openlocfilehash: ed296d339949814dbd796bb5d8e23a406be71c69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62269400"
---
# <a name="j-default-char-type-is-unsigned"></a>/J (Standardmäßig "unsigned char")

Ändert den Standard `char` Typ aus `signed char` zu `unsigned char`, und die `char` Typ ist 0 (null) erweitert, wenn sie auf Erweitert ist ein `int` Typ.

## <a name="syntax"></a>Syntax

```
/J
```

## <a name="remarks"></a>Hinweise

Wenn eine `char` Wert wird als explizit deklariert `signed`, **/j** Option keine Auswirkung darauf, und der Wert ist signaturerweitert, wenn sie auf Erweitert, wird ein `int` Typ.

Die **/j** Option definiert `_CHAR_UNSIGNED`, das verwendet wird, mit `#ifndef` in die LIMITS.h-Datei, um den Bereich der standardmäßigen definieren `char` Typ.

ANSI C- und C++ erfordern keine konkrete Implementierung der `char` Typ. Diese Option ist nützlich, wenn Sie mit Zeichendaten arbeiten, die letztendlich in einer anderen Sprache als Englisch übersetzt wird.

> [!NOTE]
>  Wenn Sie diese Compileroption mit ATL-/MFC verwenden, kann ein Fehler generiert. Auch wenn dieser Fehler durch die Definition deaktiviert werden konnte `_ATL_ALLOW_CHAR_UNSIGNED`, diese problemumgehung wird nicht unterstützt und funktioniert möglicherweise nicht immer.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften**aus.

1. Im Projekt **Eigenschaftenseiten** im Dialogfeld im linken Bereich unter **Konfigurationseigenschaften**, erweitern Sie **C/C++-** und wählen Sie dann **Befehlszeile**.

1. In der **zusätzliche Optionen** Bereich, geben Sie die **/j** -Compileroption.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DefaultCharIsUnsigned%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)<br/>
[Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio](../working-with-project-properties.md)
